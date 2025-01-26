### 본문
LocalDateTime은 날짜와 시간을 포함하는 클래스로 시간대가 포함되지 않기 때문에 특정 지역의 시간대와 무관하게 사용됩니다. 
(기본적으로 실행되는 서버의 시간대의 시간을 출력해줍니다)

```
//example time-zone: Asia/Seoul
val localDateTime = LocalDateTime.now()  
println("localDateTime = $localDateTime")  
println("Asia/Seoul = ${localDateTime.atZone(ZoneId.of("Asia/Seoul"))}")

localDateTime = 2023-09-22T21:35:56.907087
Asia/Seoul = 2023-09-22T21:35:56.907087+09:00[Asia/Seoul]
```
---
### 참고문헌
- https://docs.oracle.com/javase/8/docs/api/java/time/LocalDateTime.html 
---
### 연결문서
- 
---