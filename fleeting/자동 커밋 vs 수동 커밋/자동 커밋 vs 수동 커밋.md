### 생성 날짜: 2023-12-05T21:15
### 주제: 자동 커밋 vs 수동 커밋
---
### 본문:

- 자동 커밋: 1줄 1줄마다 쿼리 실행 후에 자동으로 커밋을 호출한다.
- 수동 커밋: commit을 하기 전까지의 쿼리를 모두 기억해뒀다고 한번에 실행한다.

첫번째 궁금증 2개의 클라이언트가 존재하고, 각각 set autocommit false로 설정하여 auto increment가 설정된 같은 테이블에 insert 쿼리를 날리면 어떻게 될까?

결과는 insert 쿼리 실행할 때 마다 auto increment가 늘어난다. Rollback을 한다고 해서 원래대로 돌아오지 않음.

그렇다는 것은 pk는 각 클라이언트가 관리하는 것이 아니라 mysql 내부에서 메모리로 관리되고 있다.
innodb를 사용하는 경우, MyISAM을 사용하는 경우에는 파일에 읽고 쓴다.

---
### 참고문헌
- https://gywn.net/2013/02/mysql-innodb-auto-increment/
- https://dev.mysql.com/doc/refman/8.0/en/innodb-auto-increment-handling.html
---
### 연결문서
- 

