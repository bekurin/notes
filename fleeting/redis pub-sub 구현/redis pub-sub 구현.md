### 생성 날짜: 2023-11-08T20:47
### 주제: redis pub-sub 구현
---
### 본문:

redis를 사용하여 pub/sub을 구현하는 경우 아래 명령어를 활용해 볼 수 있다.
-     
- PSUBSCRIBE
- PUNSUBSCRIBE
- QUIT
- RESET
- SSUBSCRIBE
- SUBSCRIBE
- SUNSUBSCRIBE
- UNSUBSCRIBE

redis pub/sub의 메시지 전송은 at-most-once를 활용하고 있고, 이는 적어도 많아야 한번 받을 수 있다는 뜻으로 메시지가 유실될 수 있다는 것을 의미합니다.

문서에서는 아래와 같이 설명을 하는데요.
(Once the message is sent by the Redis server, there's no chance of it being sent again)

redis로 pub/sub을 구현하기로 했다면 이벤트가 유실되어도 상관없는 데이터를 사용하는 것이 좋을 것 같다.
- 좋은 예: 실시간 위치 보기...
- 나쁜 예: 결제, 메시지 전송

![[pub-sub-image.png]]


---
### 참고문헌
- https://redis.io/docs/interact/pubsub/
---
### 연결문서
- [[PING]]
- [[PSUBSCRIBE]]
- [[PUNSUBSCRIBE]]
- [[QUIT]]
- [[RESET]]
- [[SSUBSCRIBE]]
- [[SUBSCRIBE]]
- [[SUNSUBSCRIBE]]
- [[UNSUBSCRIBE]]

