### 본문
| title           | description                                       |
| --------------- | ------------------------------------------------- |
| Available since | 2.0.0                                             |
| Time complexity | O(N) N은 구독 취소 하고자하는 클라이언트의 수이다. |
| ACL categories  | `@pubsub`, `@slow`                            |
#### 문법
```
UNSUBSCRIBE [channel [channel ...]]
```

파라미터로 주어진 채널에 대해서 구독을 취소합니다.

만약 아무런 파라미터가 주어지지 않는다면 모든 채널에 대해서 구독을 취소합니다.
이런 경우 모든 구독이 취소된 채널에서 클라이언트에게 메시지를 전송합니다.

---
### 참고문헌
- https://redis.io/commands/unsubscribe/
---
### 연결문서
- [[redis pub-sub 구현]]
---