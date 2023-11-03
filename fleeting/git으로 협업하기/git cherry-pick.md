### 생성 날짜: 2023-11-03T21:46
### 주제: git cherry-pick
---
### 본문:
특정 커밋을 임의의 브랜치에 붙이고 싶은 경우 사용하는 명령어이다.

#### 사용법
```
# 적용이 필요한 브랜치로 이동하여 아래 명령어 실행
git cherry-pick <commit hash>
```

cherry-pick은 특정 브랜치(develop 등)을 배포를 이유로 다른 팀에서 점유하고 있는 경우 필요한 커밋만 가져와서 main으로 향하는 PR을 만들 수 있다.

---
### 참고문헌
- https://git-scm.com/docs/git-cherry-pick
---
### 연결문서
- 

