### 생성 날짜: 2024-02-22T22:09
### 주제: redis의 key는 왜 O(1)일까?
---
### 본문:

redis에 저장된 key의 type을 확인하는 type 명령어는 O(1)의 속도를 보장한다.
어떻게 O(1)을 보장할 수 있을까? 답을 알기 위해서는 RedisObject의 구조를 이해하고 있어야한다.

```
struct redisObject {  
	unsigned type:4;  
	unsigned encoding:4;  
	unsigned lru:LRU_BITS; /* LRU time (relative to global lru_clock) or  
	* LFU data (least significant 8 bits frequency  
	* and most significant 16 bits access time). */  
	int refcount;  
	void *ptr;  
};
```

위 코드는 server.h에 정의되어 있는 redisObject로 모든 Redis의 값은 redisObject로 만들어진다.
- type: redis에 저장된 객체의 데이터형을 나타낸다.
- encoding: redis 객체에 저장된 데이터의 인코딩 타입을 나타낸다.
- lru: 데이터 생성 시간 또는 변경 된 시간이 저장된다.
- refCount: 데이터가 참조된 횟수 정보를 저장한다.
- *ptr: 실제 데이터가 저장된 주수를 가리키는 포인터이다.

이 중에서 type 정보 있기 때문에 type 명령어가 O(1)의 속도를 보장하는 것이다.

어떤 타입이 존재하는지 알기 위해서는 redismodule.h를 살펴보면 된다.
```
/* Key types. */  
#define REDISMODULE_KEYTYPE_EMPTY 0  
#define REDISMODULE_KEYTYPE_STRING 1  
#define REDISMODULE_KEYTYPE_LIST 2  
#define REDISMODULE_KEYTYPE_HASH 3  
#define REDISMODULE_KEYTYPE_SET 4  
#define REDISMODULE_KEYTYPE_ZSET 5  
#define REDISMODULE_KEYTYPE_MODULE 6  
#define REDISMODULE_KEYTYPE_STREAM 7
```

2024-02-22 기준 총 8개의 데이터 타입이 정의되어 있다.

---
### 참고문헌
- 
---
### 연결문서
- 

