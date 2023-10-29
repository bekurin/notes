### 생성 날짜: 2023-10-23T21:05
### 주제: redis 랭킹보드 구현
---
### 본문:

```
zadd ranking-board 1000 userId:1000
zadd ranking-board 999 userId:1001
zadd ranking-board 998 userId:1002
zadd ranking-board 1010 userId:1003
zadd ranking-board 1110 userId:1004
```

zadd는 key, score, value를 입력 받아 score에 따라 key에 value를 저장한다.

```
zcard ranking-board
(integer) 5
```

zcard는 key를 입력받아 해당 key에 저장된 모든 value의 개수를 출력한다.

```
# start, stop 인덱스는 모두 포함을 검색된다.
zrange ranking-board 0 -1 
zrange ranking-board 0 1
```

![[zrange-command.png]]

zrange는 key와 start, stop 인덱스를 입력받아 
start <= 인덱스 <= stop에 포함되는 모든 value 값을 출력한다.


```
zrangebyscore ranking-board 0 1000
```
![[zrangebyscore-command.png]]
zrangebyscore key와 value의 최대값, 최소값을 입력 받아 
최솟값 <= value <= 최대값 에 포함되는 모든 value를 출력한다.

```
zrank ranking-board userId:1000
```
![[zrank-command.png]]

zrank는 key와 value를 입력 받아 해당 key에서 입력 받은 value는 몇번째에 저장되어 있는지 출력한다. 이때 출력값은 순위가 아닌 인덱스인 것을 유의해야한다.

---
### 참고문헌

---
### 연결문서
- [[zadd]]
- [[zcard]]
- [[zrange]]
- [[zrangebyscore]]
- [[zrank]]
