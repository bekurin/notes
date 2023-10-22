### 생성 날짜: 2023-10-22T17:38
### 주제: connection timeout은 client만 구분할 수 있다
---
### 본문:
```
팀장: spring boot를 사용하여 서버 개발을 하던 도중 처리를 위해 너무 긴 컴퓨터 연산을 필요로 하는 http 요청에 대해서 connection을 끊어버렸으면 좋겠다는 지시를 받게 된다.
```

connection timeout을 측정하는 시간은 3 way handshake가 이뤄지는 시간을 말합니다.

그렇다는 것은 connection timeout 시간 측정을 위해서는 tcp 연결을 시동하는 syn 신호를 보내는 client만이 정확한 시간을 측정할 수 있습니다.

---
### 참고문헌
- 
---
### 연결문서
- 