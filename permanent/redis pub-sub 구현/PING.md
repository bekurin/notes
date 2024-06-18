### 본문
| title           | description            |
| --------------- | ---------------------- |
| Available since | 1.0.0                  |
| Time complexity | O(1)                   |
| ACL categories  | `@fast`, `@connection` | 

아무런 파라미터 없이 ping 명령어를 입력하면 pong을 반환하고, message에 값을 넣어주면 해당 값 그대로 결과를 반환한다.

ping 명령어를 사용하는 이유는 아래와 같다.
1. redis 서버가 살아있는지 확인하기 위해
2. 서버 기능 점검 (문제가 발생하는 경우 에러가 반환된다)
3. 지연 시간을 측정하기 위해

---
### 참고문헌
- https://redis.io/commands/ping/
---
### 연결문서
- [[redis pub-sub 구현]]
---
