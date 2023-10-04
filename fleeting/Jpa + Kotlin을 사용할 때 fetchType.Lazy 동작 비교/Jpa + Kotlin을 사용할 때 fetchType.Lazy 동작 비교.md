### 생성 날짜: 2023-09-20T11:18
### 주제: Jpa + kotlin을 사용할 때 collection, sequence에서 FetchType.Lazy 동작 비교
---
### 본문:

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

