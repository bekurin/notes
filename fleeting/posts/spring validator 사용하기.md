## 3. spring validator 사용하기
REST API 형식을 사용한다고 가정

spring-validator의 검증은 객체 생성 후에 일어나게 된다. 이 말인 즉,  객체를 입력 받는다면 우선, 그 객체가 생성되어야한다는 것으로 객체의 필드 typemismatch 예외가 발생한다면 객체 검증을 진행하지 않는다는 뜻이다.

PathVariable: url의 뒤 부분에 파라미터를 추가하는 것으로 아래와 같은 형식을 띄고 있다.
ex. http://localhost:8080/parms=test



RequestParams

RequestBody

