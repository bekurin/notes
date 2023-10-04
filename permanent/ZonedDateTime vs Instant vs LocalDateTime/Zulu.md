### 본문
UTC가 적용된 시간을 나타낼 때 사용하는 접미사입니다.

```
//example
val localDateTime = LocalDateTime.now()  
println("Asia/Seoul = ${localDateTime.atZone(ZoneId.of("Asia/Seoul"))}")  
println("UTC Time = ${localDateTime.atZone(ZoneId.of("Z"))}")

//result
Asia/Seoul = 2023-09-22T21:44:45.937625+09:00[Asia/Seoul]
UTC Time = 2023-09-22T21:44:45.937625Z
```

---
### 참고문헌
- https://datatracker.ietf.org/doc/html/rfc3339 
---
### 연결문서
- 
---