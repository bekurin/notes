### 본문
| title           | description                              |
| --------------- | ---------------------------------------- |
| Available since | 2.0.0                                    | 
| Time complexity | O(n) n은 구독해야하는  pub/sub의 수이다. |
| ACL categories  | `@fast`, `@connection`                   |

명령어는 아래와 같다.
```
PSUBSCRIBE pattern [pattern ...]
```

주어진 패턴으로 서버 구독을 실행한다.

glob-style의 패턴을 지원한다.
- - `h?llo` subscribes to `hello`, `hallo` and `hxllo`
- `h*llo` subscribes to `hllo` and `heeeello`
- `h[ae]llo` subscribes to `hello` and `hallo,` but not `hillo`

escape 문자열을 사용할 수 있습니다.

클라이언트가 구독을 하면 SUBSCRIBE, SSUBSCRIBE, PSUBSCRIBE, UNSCRIBE, SUNSUBSCRIBE, SUNSUBSCRIBE, PUNSUBSCRIBE, PING, RESET 및 KIT 명령을 제외한 다른 명령을 실행할 수 없습니다. 

**RESP3를 사용하는 경우, 클라이언트가 가입 상태에 있는 동안 모든 명령을 실행할 수 있습니다.

---
### 참고문헌
- https://redis.io/commands/psubscribe/
---
### 연결문서
- [[redis pub-sub 구현]]
---
