### 본문
| title           | description                                       |
| --------------- | ------------------------------------------------- |
| Available since | 2.0.0                                             |
| Time complexity | O(N) N은 구독하고자하는 클라이언트의 수이다. |
| ACL categories  | `@pubsub`, `@slow`                            |

#### 문법
```
SSUBSCRIBE shardchannel [shardchannel ...]
```

특정 채널로 클라이언트가 구독을 실행한다.

위 명령어를 실행 했을 때 RESP3를 사용하는 것이 아니라면 구독 관련 명령어를 제외하고, 다른 명령어를 사용할 수 없게 된다.

---
### 참고문헌
- https://redis.io/commands/subscribe/
---
### 연결문서
- [[redis pub-sub 구현]]
---
