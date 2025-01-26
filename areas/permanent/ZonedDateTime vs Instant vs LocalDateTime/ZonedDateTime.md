### 본문
ZonedDateTime은 날짜, 시간, 시간대를 모두 포함하는 클래스로 특정 시간대에 사용되는 시간을 표현할 때 사용됩니다.

```
// example
val localDateTime = LocalDateTime.now()  
println("Asia/Seoul")) = ${localDateTime.atZone(ZoneId.of("Asia/Seoul"))}")  
println("Europe/Paris")) = ${localDateTime.atZone(ZoneId.of("Europe/Paris"))}")


// result
Asia/Seoul = 2023-09-22T21:33:17.019041+09:00[Asia/Seoul]
Europe/Paris = 2023-09-22T21:33:17.019041+02:00[Europe/Paris]
```
---
### 참고문헌
- https://docs.oracle.com/javase/8/docs/api/java/time/ZonedDateTime.html
---
### 연결문서
- 
---