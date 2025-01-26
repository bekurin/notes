### 본문
| title           | description                                       |
| --------------- | ------------------------------------------------- |
| Available since | 7.0.0                                             |
| Time complexity | O(N) N은 구독 취소하고자 하는 샤딩 채널의 수이다. |
| ACL categories  | `@pubsub`, `@slow`                            |

#### 문법
```
SUNSUBSCRIBE [shardchannel [shardchannel ...]]
```

주어진 샤드 채널들의 구독을 취소할 수 있다. 아무런 값이 주어지지 않는다면 모든 구독을 취소한다.
(샤드를 사용해보고 내용을 추가해야한다.)

---
### 참고문헌
- https://redis.io/commands/sunsubscribe/
---
### 연결문서
- [[redis pub-sub 구현]]
---