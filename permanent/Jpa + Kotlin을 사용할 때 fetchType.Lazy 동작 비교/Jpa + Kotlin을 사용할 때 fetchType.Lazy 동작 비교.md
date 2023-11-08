### 생성 날짜: 2023-09-20T11:18
### 주제: Jpa + kotlin을 사용할 때 collection, sequence에서 FetchType.Lazy 동작 비교
---
### 본문:

비교해봤다. 3,000,000개의 데이터를 적재하고, 읽어오는 과정을 반복했는데 collection과 sequence 사이에 유의미한 차이는 없었다.

```
// collection
entity.childs
	.map { /* doSomething */ }

// sequence
entity.childs.asSequence()
	.map { /* doSomething */ }
```


---
### 참고문헌
- 
---
### 연결문서
- [[Spring Data JPA]]
- [[JPA FetchType]]

