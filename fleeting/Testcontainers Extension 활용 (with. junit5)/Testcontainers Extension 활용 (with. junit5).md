### 생성 날짜: 2024-02-05T21:13
### 주제: Testcontainers Extension 활용 (with. junit5)
---
### 본문:

Testcontainers.junit.jupiter 의존성을 가져오면 TestContainers, Container 어노테이션을 사용할 수 있다.
- TestContainers: Container 어노테이션이 선언된 도커 컨테이너를 관리해준다.
	- SpringBootTest와 같은 레벨에 선언해두면 된다.
- Container: Testcontainers에서 관리가 필요한 컨테이너에 선언하면 된다.

모든 testcontainers를 static으로 선언해서 관리하는 것도 좋지만 junit을 사용하는만큼 extension으로 만들면 테스트 실행 시에 자동으로 관리될 수 있어 신경 쓸 것이 줄어든다.
- BeforeAllCallback만 선언하는 것으로도 충분하다.

하지만 모든 테스트 실행 전에 beforeAll 함수를 실행시키므로 컨테이너가 여러 번 내렸다가 실행 되지 않게 하기 위해서는 isRunning() 함수를 사용하면 된다.

```
override fun beforeAll(context: ExtensionContext?) {
        if (mysqlContainer.isRunning) {
            return
        }
        mysqlContainer.start()
    }
```

위 처럼 이미 실행 중이라면 아무것도 하지 않도록 return을 하게 되면 
- 테스트 실행 -> Testcontainers가 최초로 컨테이너를 로드해줌
- 테스트 중 -> 조건문에 걸려 컨테이너가 재시작 되지 않음[]()
- 테스트 종료 -> Testcontainers가 관리하고 있는 리소스 제거
와 같이 컨테이너 생명 주기가 관리되게 할 수 있다.

시스템 변수들은 매번 변경되게 되는데. 이때는 System.setProperty 함수를 사용하는 것으로 정보를 입력해줄 수 있다. 이렇게 하는 이유는 testcontainers가 컨테이너를 로드할 때 매번 랜덤 포트로 컨테이너가 실행되기 때문이다.

mysql, redis, mariadb, kafka 등 여러 솔류션에 대해서 적합한 컨테이너를 제공하고 있어 사용하는 것이 테스트 실행 시에 더 효율적일 수 있다. 아래 페이지에서 지원하는 솔루션을 확인할 수 있다.
- https://testcontainers.com/modules/

---
### 참고문헌
- 
---
### 연결문서
- 

