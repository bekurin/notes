### 본문
Instant는 날짜, 시간, 시간대 정보가 모두 제거된 클래스로 특정 지역의 시간대를 사용할 수 없고, UTC 시간만 사용할 수 있습니다.

```
//example time-zone: Asia/Seoul
val instant = Instant.now()  
val localDateTime = LocalDateTime.now()  
println("instant = $instant")  
println("Asia/Seoul = ${localDateTime.atZone(ZoneId.of("Asia/Seoul"))}")

//result
instant = 2023-09-22T12:39:24.339340Z
Asia/Seoul = 2023-09-22T21:39:24.340143+09:00[Asia/Seoul]
```

서버의 시간대가 맞지 않고, 맨 뒤에 z 문자가 포함된 것을 확인할 수 있습니다. z는 [[Zulu]]의 약자입니다.

---
### 참고문헌
- https://docs.oracle.com/javase/8/docs/api/java/time/Instant.html
---
### 연결문서
- [[Zulu]]
---