### 생성 날짜: 2024-06-03T19:11
### 주제: preview 환경 구축
---
### 본문:
argoCD, gitops를 사용하여 간편하게 preview 환경을 구축할 수 있도록 합니다.

![[preview-environment.png]]
위와 같이 총 4단계로 구현이 된다.

동일한 application set과 application set controller가 동일한 namespace에 존재해야한다. argocd v2.6 이상 부터는 기본 namespace에 application set controller가 존재하는 것으로 파악된다. 

이 말은 즉, 기본 namespace에 위 작업을 하는 것이 아니라면 수동으로 application set controller를 설치해줘야한다.

1. 개발자가 PR을 생성한다.
2. CI를 돌리면서 docker image repository에 image를 upload를 한다.
3. CI가 끝나면 preview 라벨을 PR에 붙인다.
4. argoCD applicationSet에서 preview 라벨이 붙은 PR을 모니터링하고, 신규로 생성될 때마다 docker image에 기반하여 preview 환경을 구축한다.
5. PR이 closed 되거나 deleted가 되면 자동으로 preview 환경을 삭제한다.


---
### 참고문헌
- https://www.youtube.com/watch?v=LkBBPnG9QO0
- https://medium.com/@jerome.decoster/create-temporary-environment-from-pull-request-with-argocd-applicationset-1cef9803223a
- https://dev.to/camptocamp-ops/using-argocd-pull-request-generator-to-review-application-modifications-236e
---
### 연결문서
- 

