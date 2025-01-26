### 본문
| title           | description                                       |
| --------------- | ------------------------------------------------- |
| Available since | 7.0.0                                             |
| Time complexity | O(N) N은 구독하고자 하는 샤딩 채널의 수이다. |
| ACL categories  | `@pubsub`, `@slow`                            |

redis 클러스터를 통해 구성된 샤드 채널들에 구독을 실행할 수 있다.
(샤드를 정확하게 사용해봐야 어떤 의미인지 이해할 수 있을 것 같다.)

---
### 참고문헌
- https://redis.io/commands/ssubscribe/
---
### 연결문서
- [[redis pub-sub 구현]]
---

