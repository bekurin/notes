### 생성 날짜: 2023-11-26T09:43
### 주제: redis에서 key를 다시 작성하면 왜 ttl이 사라질까?
---
### 본문:

```
The timeout will only be cleared by commands that delete or overwrite the contents of the key, including DEL, SET, GETSET and all the *STORE commands.
```

redis 문서에서도 설명하듯이 ttl이 설정된 key에 del, set, getset 등 저장 관련 명령어를 수행하면 ttl이 사라진다고 합니다.

그렇다면 왜 사라지는 것일까요?
redis DB에 저장되는 객체인 redisDb의 구조를 보면 알 수 있습니다.

```
typedef struct redisDb {  
	dict **dict; /* The keyspace for this DB */  
	dict **expires; /* Timeout of keys with a timeout set */  
	...
	int id; /* Database ID */  
	long long avg_ttl; /* Average TTL, just for stats */  
	unsigned long expires_cursor; /* Cursor of the active expire cycle. */  
	...
	dbDictState sub_dict[2]; /* Metadata for main and expires dictionaries */  
} redisDb;
```

위 코드에서 볼 수 있듯이 redisDb에 키와 관련된 정보, 만료시간(ttl), 데이터베이스 ID(클러스터를 위한 데이터베이스 ID로 추정됩니다)

구조는 파악했고, ttl이 사라지는 이유를 추측해보면 
> 기존에 존재하는 키에 del,set,getset과 같은 명령어를 수행하면 redisDb 객체를 새롭게 만들어 깔아끼우기 때문에 ttl이 사라지는 것

이라고 추측해볼 수 있습니다.

코드로 한번 살펴볼까요?

```
void setKey(client *c, redisDb *db, robj *key, robj *val, int flags) { 
	int keyfound = 0;  
	  
	if (flags & SETKEY_ALREADY_EXIST)  
		keyfound = 1;  
	else if (flags & SETKEY_ADD_OR_UPDATE)  
		keyfound = -1;  
	else if (!(flags & SETKEY_DOESNT_EXIST))  
		keyfound = (lookupKeyWrite(db,key) != NULL);  
	  
	if (!keyfound) {  
		dbAdd(db,key,val);  
	} else if (keyfound<0) {  
		dbAddInternal(db,key,val,1);  
	} else {  
		dbSetValue(db,key,val,1,NULL);  
	}  
	incrRefCount(val);  
	if (!(flags & SETKEY_KEEPTTL)) removeExpire(db,key);  
	if (!(flags & SETKEY_NO_SIGNAL)) signalModifiedKey(c,db,key);  
}

static void dbAddInternal(redisDb *db, robj *key, robj *val, int update_if_existing) {  
	dictEntry *existing;  
	int slot = getKeySlot(key->ptr);  
	dict *d = db->dict[slot];  
	dictEntry *de = dictAddRaw(d, key->ptr, &existing);  
	if (update_if_existing && existing) {  
		dbSetValue(db, key, val, 1, existing);  
		return;  
	}  
	serverAssertWithInfo(NULL, key, de != NULL);  
	dictSetKey(d, de, sdsdup(key->ptr));  
	initObjectLRUOrLFU(val);  
	dictSetVal(d, de, val);  
	db->sub_dict[DB_MAIN].key_count++;  
	cumulativeKeyCountAdd(db, slot, 1, DB_MAIN);  
	signalKeyAsReady(db, key, val->type);  
	notifyKeyspaceEvent(NOTIFY_NEW,"new",key,db->id);  
}
```

키를 설정하는 코드를 가져왔습니다. 기존에 키가 있는 경우 SETKEY_ADD_OR_UPDATE 조건에 의해 keyfound가 -1이 되고, dbAddInternal 함수가 실행되게 됩니다.

별다른 설정없이 값을 설정하는 것을 알 수 있고, dbAddInternal 함수가 실행된 후에 removeExpire 함수가 실행되는 것을 볼 수 있는데요.

새로운 값을 수정한 후에 SETKEY_KEEPTTL 옵션이 설정되지 않았다면 ttl을 제거해주는 것을 알수 있습니다.

추가로 expires라고 써있는 곳에 ttl을 저장하는 것 같은데 dict는 어떤 구조인지 궁금하여 구조만 찾아봤습니다.

```
typedef struct dictEntry {  
	void *key;  
	void *val;  
	struct dictEntry *next;  
} dictEntry;

typedef struct dict {  
	dictEntry **table;  
	dictType *type;  
	unsigned long size;  
	unsigned long sizemask;  
	unsigned long used;  
	void *privdata;  
} dict;
```

dict는 위와 같은 구조를 가지고 있는데요. 아직까지 정확하게 파악하지는 못했지만
dictEntry 구조를 보면 익숙하게 key, value를 설정하고, 연결 리스트와 비슷하게 자신과 같은 타입을 참조하는 next 변수가 있습니다.
(뭔가 연결되어 저장되는 것 같죵?)

---
### 참고문헌
- https://redis.io/commands/expire/
- https://github.com/redis/redis/pull/6679/files
---
### 연결문서
- 
---
### 더 알아보고 싶은 것
- redis hashes, list 등 자료구조의 정확한 구조
