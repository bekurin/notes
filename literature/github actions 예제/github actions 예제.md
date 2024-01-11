### 생성 날짜: 2024-01-11T20:59
### 주제: github actions 예제
---
### 본문:
github actions 컴포넌트 소개
- workflow:
	- 하나 이상의 작업을 실행하도록 구성 가능한 자동화 프로세스로 작업의 집합이다.
	- .github/workflows 하위에 파일이 있어야 정상 동작 (이름이 틀리는 경우 동작하지 않음)
	- 하나의 액션에 여러 workflow를 등록할 수 있다.
- event
	- 워크플로우를 실행할 수 있는 깃헙에서 발생될 수 있는 이벤트
	- push, pull, merge, pull-request 생성 등 여러 이벤트가 있다.
		- [깃헙 액션 이벤트](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows)
- runner
	- job을 실행하는 서버로 각 러너는 1개의 job을 실행한다.
- job
	- runner에서 실행되는 step의 집합
	- 기본적으로 job은 병렬로 실행된다.
		- 최대 몇개까지 병렬로 실행되는지 궁금하다. -> 깃헙 계정에 따라 다르다.
		- 무료 계정의 경우 20개의 job을 한번에 실행 가능
- step
	- job에 정의된 개별 명령으로 절차지향적으로 실행되면 앞 step이 실행하면 job이 실패되고, workflow가 실패한다. 실패한 step 다음 step은 실행하지 않음
- action
	- 모듈화된 action으로 사용자 정의 action, 공식 action 등이 있다.

---
### 참고문헌
- https://docs.github.com/ko/actions
---
### 연결문서
- 

