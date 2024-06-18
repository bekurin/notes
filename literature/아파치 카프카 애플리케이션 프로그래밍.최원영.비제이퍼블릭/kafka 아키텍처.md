### 생성 날짜: 2024-04-14T14:11
### 주제: kafka 아키텍처
---
### 본문:

## 카프카

![[kafka-architecture.png]]

kafka에는 Procuer, Broker, Consumer, Consumer Group이라는 큰 개념이 존재하고 각각은 위 처럼 통신을 진행하게 됩니다.

- Producer는 이벤트를 발행하는 주체로 리더 파티션과 통신하여 데이터를 적재합니다.
- Broker는 Producer로 부터 받은 데이터를 저장합니다. 또한, Topic에 생성된 여러 Partition이 문제 없이 동작할 수 있도록 관리합니다. (producer가 partition에 데이터를 보내지만 그것을 unified log 형태로 관리하는 것은 broker이다)
- Consumer는 특정 Partition과 연결되어 Procuer가 발행한 이벤트를 소비합니다.
- Consumer Group은 여러 Consumer를 관리하는 것으로 Consumer Group Id로 관리가 되고, 설정에 따라 Consumer Group Id가 다른 경우 이벤트를 처음부터 가져올 수 있습니다.


## 카프카 소스 커넥터

![[kafka-connector-architecture.png]]

소스 커넥터는 Producer를 손쉽게 확장할 수 있도록 도와주는 개념으로 kafka 실행 시에 사전에 구현된 jar 파일이 토픽으로 이벤트를 발행해줍니다.

모든 경우에 손쉽게 확장할 수는 없고, 주어진 상황을 잘 살펴봐야 하는데 대표적으로 파일 저장, 데이터베이스 CRUD가 있습니다.

특정 데이터베이스(mysql, mongoDB, redis 등)에 데이터가 저장될 때 이벤트를 발행하고 싶은 경우가 적절한 경우 입니다.

한번 만들어두면 특정 테이블 이벤트를 추가해야하는 경우 connector를 하나 더 실행해주면 끝이다.

커텍터는 주어진 인터페이스가 있고, 이를 구현하여 동작하도록 만들 수 있다. connector는 rest api 형태로 자원을 제어하기 때문에 스케일 아웃에도 용이하다.

---
### 참고문헌
- 
---
### 연결문서
- 

