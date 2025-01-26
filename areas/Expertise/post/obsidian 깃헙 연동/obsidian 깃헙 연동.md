### 생성 날짜: 2023-09-19T21:45
### 주제: obsidian Github 연동
---
### 본문
icloud, github, obsidian을 연동해서 윈도우, 맥 생태계에서 사용할 수 있도록 한다.
(pc에 github, obsidian이 설치되어 있다고 가정한다)

1. github repository 생성 (private / public optional)
2. finder에서 icloud 폴더로 이동
3. obsidian valut 생성
4. 터미널에서 valut 디렉토리 이동
5. 아래 명령어 입력
```
git init
git remote add origin <https path>
```

git cli, git desktop을 사용하여 git을 사용할 수 있는 환경에서는 자유롭게 동기화하여 사용할 수 있고, icloud 폴더에서 코드를 관리하기 때문에 맥 생태계라면 어디에서든 동기화된 상태에서 사용할 수 있다.

### 팁1
만약 터미널에서 파일 이름이 유니코드([[unicode]])로 보인다면 아래 명령어를 실행시켜주면 된다.

```
// 한글 이름이 unicode로 출력되는 경우 실행
git config --global core.quotepath false
```

### 팁2
icloud Directory를 매번 명령어를 사용하면서 이동하는 것이 불편하다.
![[icloud-directory.png]]

편한 이동을 위해 root 디렉토리에 위치한 ./zshrc 파일에서 alias를 수정해주면 된다.
![[alias.png]]

---
### 참고문헌
- 
---
### 연결문서
- [[unicode]]