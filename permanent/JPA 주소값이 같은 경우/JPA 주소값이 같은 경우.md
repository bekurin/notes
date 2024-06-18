### 생성 날짜: 2023-11-20T19:59
### 주제: JPA 주소값이 같은 경우
---
### 본문:
```
JPA 사용시에 == 결과가 항상 false인 것도 true인 것도 아니다.
```

equals를 override 해주지 않는다면 일반적으로 객체의 주소값이 같은지 비교하게 됩니다.
아래와 같은 연산을 한다고 하면 결과가 어떻게 될 것 같은지 상상해보겠습니다.

```
val placeA = Place("이름", "주소", Coordinate(36.0, 127.0))
val placeB = Place("이름", "주소", Coordinate(36.0, 127.0))

assertThat(placeA == placeB).isTrue
```

위와 같이 테스트를 작성하면 결과는 실패입니다. placeA, placeB를 새롭게 생성해주기 때문에 당연하게도 서로 다른 주소값을 가지게 되기 때문입니다.

그렇다면 아래와 같은 코드는 어떻게 동작할까요?
```
val placeA = Place("이름", "주소", Coordinate(36.0, 127.0))
entityManager.persist(placeA)

val findPlaceA = entityManager.find(Place::class.java, placeA.id)
assertThat(placeA == findPlaceA).isTrue
```
위 테스트는 성공하게 됩니다. 어찌보면 당연하다 생각할 수 있는데요. entityManager를 사용하여 저장한 placeA와 entityManager를 사용하여 검색한 placeA와 같은 ID를 가진 findPlaceA를 검색하여 비교하기 때문입니다.

하지만 만약 placeA가 저장되지 않았다면 find 함수의 결과로 새로운 place 객체를 생성하도록 동작했을 것이기 때문에 일종의 캐싱 기능이 있어야 테스트 통과가 말이 되게 됩니다.
(JPA에서 사용하는 일종의 캐싱 개념이 바로 영속성 컨텍스트입니다.)

위 테스트는 코드 1줄만 추가하면 실패합니다. 아래 코드로 보겠습니다.
```
val placeA = Place("이름", "주소", Coordinate(36.0, 127.0))
entityManager.persist(placeA)
entityManager.detach(placeA)

val findPlaceA = entityManager.find(Place::class.java, placeA.id)
assertThat(placeA == findPlaceA).isTrue
```
detach 함수를 사용하여 영속성 컨텍스트에서 관리되고 있던 placeA를 더 이상 관리되지 않도록 변경해줍니다.

그렇게 되면 영속성 컨텍스트에 placeA가 관리되지 않기 때문에 find 함수에서는 새로운 주소값을 가진 placeA를 반환하게 되고, 반환된 placeA의 값이 새롭게 영속성 컨텍스트로 관리되게 됩니다.


++
datasource는 결국 하나의 thread에서 하나의 데이터베이스 connection으로 동작하게 될 것이다. (트랜잭션을 관리해야하기 때문에)

예를 들어 아래와 같이 데이터가 저장되어 있다고 한다면

| name   | age | status |
| ------ | --- | ------ |
| 홍길동 | 25  | 완료   |
| 아무개 | 27  | 완료   |
| 김모씨 | 36  | 완료   |

김모씨를 조회하여 나이를 36으로 변경한다고 하면

| name   | age | status |
 | ------ | --- | ------ |
 | 홍길동 | 25  | 완료   |
 | 아무개 | 27  | 완료   |
 | 김모씨 | 36  | 임시   |

조회할 때 영속성으로 관리되고 있던 김모씨는 객체 값 변경 후에도 영속성으로 관리될까? 라는 고민이 들었다.

실험을 해봐야 겠지만 그렇다고 한다면 영속성 컨텍스트 관리되지 않는다는 의미는 결국 트랜잭션이 종료되었다는 의미로 해석해도 되는 것인지 궁금하다.

---
### 참고문헌
- 
---
### 연결문서
- 

