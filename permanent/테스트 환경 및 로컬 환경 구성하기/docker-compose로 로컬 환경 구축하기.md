### 생성 날짜: 2023-09-29T23:03
### 주제: docker-compose로 로컬 환경 구성하기
spring boot 3.1.0을 사용하면 Testcontainers에서 사용하는 Docker-compose 파일을 자동으로 사용할 수 있다. local, dev 프로필을 분리하여 관리하면 보다 간편하게 사용할 수 있음

---
### 본문: spring boot 3.1 docker-compose support 사용하기

프로젝트는 협업을 하기 위한 playground이기 때문에 별다른 설정없이 간편하게 실행해볼 수 있어야합니다. 이에 더해 테스트 환경은 운영/개발 환경에서 사용하는 것과 동일하게 설정해줄 필요가 있습니다.

spring boot를 사용할 때 위에 설명한 2가지를 만족할 수 있는 방법에 대해서 기술하겠습니다.

테스트 환경과 로컬 환경을 구성하기 위해 사용되는 기술은 아래와 같습니다.
- [[docker]]
- [[docker-compose]]
- [[mysql workbench]]

testcontainers를 설정할 때 GernericContainer, MysqlContainer, RedisContainer와 같이 코드레벨에서 구현할 수 있는 방법도 있지만 docker-compose를 사용하여 테스트 환경을 구성하는 방법을 위주로 설명하겠습니다.

docker-compose 작성
```
version: '3.8'

services:
  db:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_HOST: '%'
      MYSQL_DATABASE: 'core'
      MYSQL_ROOT_USER: 'root'
      MYSQL_ALLOW_EMPTY_PASSWORD: 'yes'
      TZ: Asia/Seoul
    ports:
      - "3306:3306"
    command:
      - --character-set-server=utf8mb4
      - --collation-server=utf8mb4_unicode_ci
```

## docker-compose 명령어

### docker-compose 실행

```
docker-compose up -d
```
### mysql workbench 연결
workbench Test connection 메뉴를 사용하여 정상적으로 데이터베이스에 연결되는지 확인한다.

### 저장 API 호출 후 mysql workbench 확인
로컬환경에서 정상적으로 동작하는지 확인하기 위해 API를 호출하여 잘 저장되는지 확인한다.

### docker-compose 종료

```
docker-compose down
```

## 테스트 환경 구축
통합 테스트 환경을 구축하고, application.yml 파일을 정의해준다.
통합 테스트를 실행하여 docker container가 정상적으로 로드되는지 확인하고, 테스트가 통과하는지 확인한다.

### github actions에서 정상적으로 동작하는지 확인
github actions runner images에 이미 docker daemon이 설치되어 있다. 따라서 ./gradlew build 와 같은 명령어들이 정상적으로 동작한다.

---
### 참고문헌
- 
---
### 연결문서
- [[docker desktop]]
- [[docker]]
- [[testcontainers]]
- [[mysql workbench]]
