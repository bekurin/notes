### 본문
stash 명령어는 현재 변경 사항을 원하는 브랜치에 반영하고 싶은 경우에 사용할 수 있습니다.

예를 들어 develop, feature/something 2개의 브랜치가 있을 때 deelop 브랜치의 변경 사항을 feature/something에 반영하고 싶은 경우

```
# develop 브랜치에서 아래 명령어 실행
git stash
```

위 명령어를 실행하면 변경 사항이 임시 저장소에 저장되고

```
# feature/something 브랜치에서 아래 명령어 실행
git stash apply
```

위 명령어를 실행하면 임시 저장소의 변경 사항이 현재 브랜치에 반영됩니다.

---
### 참고문헌
- https://git-scm.com/docs/git-stash
---
### 연결문서
- 
---