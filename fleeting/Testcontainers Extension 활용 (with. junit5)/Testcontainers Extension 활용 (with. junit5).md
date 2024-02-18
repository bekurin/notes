### 생성 날짜: 2024-02-05T21:13
### 주제: Testcontainers Extension 활용 (with. junit5)
---
### 본문:
- Testcontainers 사용 시에 Extension 화하여 사용할 수 있음
	- Extension 시 주의 사항 컨테이너가 시작 검증이 없으면 컨테이너가 여러번 실행됨
- SpringBootTest 어노테이션 위에 TestContiners 어노테이션을 선언하면 Containers 어노테이션이 있는 값들을 자동으로 관리해줌
- System.setProperty 함수를 사용하여 port, host 정보를 입력한다.
- 데이터베이스, 레디스, kafka 등 일반적인 솔루션을 사용한다면 라이브러리를 import 하는 것이 조금 더 효율적일 수 있음

---
### 참고문헌
- 
---
### 연결문서
- 

