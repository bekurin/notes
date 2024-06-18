### 본문
| title           | description                                       |
| --------------- | ------------------------------------------------- |
| Available since | 2.0.0                                             |
| Time complexity | O(n) n은 구독을 취소해야하는 클라이언트의 수이다. |
| ACL categories  | `@pubsub`, `@slow`                            |

명령어 문법
```
PUNSUBSCRIBE [pattern [pattern ...]]
```

주어진 패턴에 해당하는 클라이언트의 구독을 취소한다.
패턴이 주어지지 않는다면 모든 구독을 취소하게 된다.

패턴을 주어지지 않는 경우 의도치 않게 모든 구독을 취소할 수 있게 되기 때문에 조심해야한다.

---
### 참고문헌
- https://redis.io/commands/punsubscribe/
---
### 연결문서
- [[redis pub-sub 구현]]
---
