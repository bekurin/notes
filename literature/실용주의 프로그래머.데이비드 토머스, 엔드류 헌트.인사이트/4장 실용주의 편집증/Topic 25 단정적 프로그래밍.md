> 이 애플리케이션을 외국에서 사용하는 일은 절대 없을 텐데 뭐하러 국제화 하지? count는 음수가 될 수 없어. 로깅은 실패할 리 없어. p.162

뜨끔,,, 정말로 불가능한 일이라면 단정문을 통해 그런 일이 발생하지 않도록 코드 레벨에 녹여내자.

Q: 예외랑 단정문은 무슨 차이...??
-> spring boot에서 테스트 해보기.
#### 단정과 부정문
iterator 패턴을 사용 중이라면 단정문의 구현에 따라 운영 환경 동작이 상이하게 발생한다.

#### 단정 기능을 켜 둬라.
단정 기능은 디버깅 도구로 치부하면서 운영환경에서 제거하는 실수를 범하지 마라.
1. 테스트가 모든 버그를 찾을 수 없다.
2. 프로그램이 험난한 상황에서 실행되기 때문에 하드웨어 적인 문제가 발생할 수 있다.

