### 생성 날짜: 2024-02-20T20:45
### 주제: redis 공유 정수
---
### 본문:
redis에서는 공유 정수가 있습니다. 0~9999까지의 정수를 미리 생성하여 캐시를 하고, 해당 정수가 사용되는 경우 바로 반환을 하도록 구현되어 있습니다.
(숫자 이외에도 기본 성공/실패 응답, 공통 명령어 등을 캐시를 하고 있습니다.)

0~9999까지 캐시가 되어 있다는 것을 어떻게 확인할 수 있을까요??
redis 프로젝트의 server.h 파일을 보면 알 수 있습니다.
```
...
#define OBJ_SHARED_INTEGERS 10000
...

struct sharedObjectsStruct {  
...
*integers[OBJ_SHARED_INTEGERS],  
...
};
```

위에 정의한 것 처럼 OBJ_SHARED_INTEGER 수만큼 정수를 캐시하고, sharedObjectsStruct.intergers로 참조할 수 있도록 선언되어 있습니다.

server.c의 createSharedObjects 함수를 보면 실제로 캐시 데이터를 생성하는 구현을 볼 수 있습니다.

```
void createSharedObjects(void) {  
	...
	for (j = 0; j < OBJ_SHARED_INTEGERS; j++) {  
		shared.integers[j] =  
		makeObjectShared(createObject(OBJ_STRING,(void*)(long)j));  
		initObjectLRUOrLFU(shared.integers[j]);  
		shared.integers[j]->encoding = OBJ_ENCODING_INT;  
	}
	...
}
```

server.h에 정의한 OBJ_SHARED_INTEGER 만큼 순환을 하면서 공유 객체를 생성해주고 있습니다.

makeObjectShared 함수의 구현은 object.c에서 확인할 수 있고, 다음은 구현부 입니다.

```
robj *makeObjectShared(robj *o) {  
	serverAssert(o->refcount == 1);  
	o->refcount = OBJ_SHARED_REFCOUNT;  
	return o;  
}
```

serverAssert는 구현을 봐야겠지만 refCount가 1인지 확인하는 함수일 것으로 판단됩니다.

주석에서 써있지만 공유 객체의 refCount는 특별하게 OBJ_SHARED_REFCOUNT를 넣어주게 되고, incrRefCount/decrRefCount 명령어를 사용한다고 하더라도 값을 수정하지 않습니다.

```
#define OBJ_SHARED_REFCOUNT INT_MAX /* Global object never destroyed. */
```

OBJ_SHARED_REFCOUNT은 위와 같이 server.h에 정의되어 있고, 전역 객체로 삭제하지 않게 하기 위해 판단하는 값으로도 활용되는 것 같습니다.

활용 부분을 보려면 t_string.c 파일을 확인해야 합니다.
그 중에서도 incrDecrCommand 함수에서 자세한 사항을 확인할 수 있는데요.

```
void incrDecrCommand(client *c, long long incr) {  
	...
	if (o && o->refcount == 1 && o->encoding == OBJ_ENCODING_INT &&  
	(value < 0 || value >= OBJ_SHARED_INTEGERS) &&  
		value >= LONG_MIN && value <= LONG_MAX)  
	{  
		new = o;  
		o->ptr = (void*)((long)value);  
	} else {  
		new = createStringObjectFromLongLongForValue(value);  
		...
	}
	...
}
```

함수의 구현을 보면 if절의 조건을 만족하지 않는 경우가 공유 정수를 사용해볼 수 있는 경우입니다.

createStringObjectFromLongLongForValue 함수 구현을 따라가보면 아래와 같은데요.

```
robj *createStringObjectFromLongLongForValue(long long value) {  
	if (server.maxmemory == 0 || !(server.maxmemory_policy & MAXMEMORY_FLAG_NO_SHARED_INTEGERS)) {  
		return createStringObjectFromLongLongWithOptions(value, LL2STROBJ_AUTO);  
	} else {  
		return createStringObjectFromLongLongWithOptions(value, LL2STROBJ_NO_SHARED);  
	}  
}
```

maxmemory 정책이 허락하는 한 공유 객체를 사용하고, 정책이 허락하지 않는다면 새롭게 객체를 생성하게 됩니다.

추가로 주의깊게 살펴봐야하는 것은 0~9999 사이의 값이지만 LFU/LRU 정보가 필요한 경우에는 공유 객체를 반환하지 않습니다.
- LFU: Least Frequently Used -> 가장 빈번히 사용
- LRU: Least Recently Used -> 가장 오래전에 사용

추측하기로는 object.c의 구현되어 있는 initObjectLRUOrLFU 함수 때문인 것 같은데요.
```
void initObjectLRUOrLFU(robj *o) {  
	if (o->refcount == OBJ_SHARED_REFCOUNT)  
		return;  
	if (server.maxmemory_policy & MAXMEMORY_FLAG_LFU) {  
		o->lru = (LFUGetTimeInMinutes() << 8) | LFU_INIT_VAL;  
	} else {  
		o->lru = LRU_CLOCK();  
	}  
	return;  
}
```
공유 객체라면 LFU/LRU 값을 초기화 시켜주지 않기 때문에 redisObject에 저장된 lru 값을 사용하지 못하게 되기 때문이 아닌 가 생각이 듭니다.

마지막으로 createStringObjectFromLongLongWithOptions 구현을 살펴보면 아래와 같습니다.

```
robj *createStringObjectFromLongLongWithOptions(long long value, int flag) {  
	robj *o;  
	  
	if (value >= 0 && value < OBJ_SHARED_INTEGERS && flag == LL2STROBJ_AUTO) {  
		// 공유 정수 사용
		o = shared.integers[value];  
	} else {  
		// 새롭게 생성
		...
	}  
	return o;  
}
```

처음에 살펴본 sharedObjectsStruct(shared)의 integers를 참조하여 인덱스에 해당하는 값을 반환받게 됩니다.


---
### 참고문헌
- 
---
### 연결문서
- 

