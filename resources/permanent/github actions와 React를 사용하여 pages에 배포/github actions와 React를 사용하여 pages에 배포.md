### 생성 날짜: 2024-01-01T21:35
### 주제: github actions와 React를 사용하여 pages에 배포
---
### 본문:
github actions, react, pages를 사용하여 cicd 파이프라인을 구축하기 위해서는 아래 항목을 수행해야 합니다.

-   <본인 깃헙 username>.github.io 리포지토리 생성
-   react, typescript 프로젝트 생성
-   github actions 작성

node 설치는 생략하고 진행하도록 하겠습니다. ([node download](https://nodejs.org/en/download "node download"))

## <본인 깃헙 username>.github.io 리포지토리 생성

[##_Image|kage@cIOtaN/btsB5BJO5NL/Nzg3SPHaprJrDTKkaL7hW0/img.png|CDM|1.3|{"originWidth":1134,"originHeight":590,"style":"alignCenter","width":700,"height":364,"caption":"리포지토리 생성 버튼 클릭","filename":"Screenshot 2023-12-15 at 10.56.59 PM.png"}_##]

빨간 박스로 표시된 New 버튼을 눌러줍니다.

[##_Image|kage@bbTj00/btsB7hX5K5y/sXaosqLf80POA7JSVWOtA1/img.png|CDM|1.3|{"originWidth":745,"originHeight":944,"style":"alignCenter","width":600,"height":760,"caption":"리포지토리 생성","filename":"Screenshot 2023-12-15 at 10.58.02 PM.png"}_##]

위 캡처에 표시된 순서대로 입력을 해줍니다. 이때 Repository name에 본인의 username이 들어갈 수 있도록 유의합니다.

[##_Image|kage@dPbu5M/btsB4UXeTWE/ZT9KK9d7EaNUzLa96ujxd1/img.png|CDM|1.3|{"originWidth":811,"originHeight":529,"style":"alignCenter","width":600,"height":391,"caption":"클론을 위한 url 복사","filename":"Screenshot 2023-12-15 at 11.00.41 PM.png"}_##]

로컬 PC에 github project를 복사하기 위해 Https URL을 복사해 줍니다.

```
git clone <방금 복사한 url>
```

위 명령어를 로컬 디렉터리에 입력하면 생성한 github 프로젝트와 로컬 PC가 연결됩니다.

## react, typescript 프로젝트 생성

아래 명령어를 사용하여 react, typescript 프로젝트를 생성해 줍니다.

```
npx create-react-app <project name> --template typescript
```

## github actions 작성

무조건 root 디렉터리에서. github/workflows 하위에 github actions을 생성해야 합니다.

다음은 workflow의 설정입니다.

```
name: cicd

on:
  push:
    branches:
      - main
  workflow_dispatch:
```

-   name: workflow의 이름입니다.
-   on: workflow가 어떤 이벤트에 반응하여 실행될지 정의합니다.
    -   push.branches.main: main 브랜치가 push 될 때마다 workflow를 실행합니다.
    -   workflow\_dispatch: workflow를 수동으로 실행할 수 있게 해 줍니다. 수동 실행 시에는 branch 또는 tag를 사용할 수 있습니다.

다음은 ci 작업입니다.

```
  ci:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4
    - name: Set up Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '20'
    - name: Cache node_modules
      id: cache
      uses: actions/cache@v3
      with:
        path: '**/node_modules'
        key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
        restore-keys: |
          ${{ runner.os }}-node-
    - name: Install Dependencies
      run: npm install
    - name: Build
      run: npm run build
    - name: Upload artifact
      uses: actions/upload-pages-artifact@v2
      with:
        path: './build'
```

ci는 아래 순서로 동작합니다.

1.  github repository 정보를 보기 위한 Checkout
2.  node 버전 설정
3.  캐시 된 node\_modules가 있는지 확인하고 있다면 가져옴
4.  필요한 라이브러리를 설치
5.  프로젝트 빌드
6.  github actions 빌드된 파일을 업로드

중요한 액션은 필요한 라이브러리 설치 및 프로젝트 빌드/업로드입니다. 추후 테스트 코드를 작성한다면 빌드 단계에서 테스트 코드를 실행시킬 수 있습니다.

```
  cd:
    needs: [ci]
    permissions:
      pages: write
      id-token: write
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
    - name: Deploy to GitHub Pages
      id: deployment
      uses: actions/deploy-pages@v3
```

cd는 아래 순서로 동작합니다.

1.  ci 액션이 끝났는지 확인한다.
2.  deploy-page 액션을 실행한다.

비교적 간단하게 cd 액션이 끝나게 되는데 이것은 github actions가 deploy-pages 액션을 모듈화 하여 자세한 구현 내용을 감췄기 때문입니다. 자세한 사항에 대해 알고 싶다면 아래 링크를 확인해 주세요.

-   deploy-pages: [https://github.com/actions/deploy-pages](https://github.com/actions/deploy-pages)

ci cd 배포 파이프라인을 위한 github actions 코드를 모두 작성했으니 action을 실행시켜 보겠습니다.

```
git add .
git commit -m "feat: init project"
git push origin main
```

맨 처음에 main 브랜치에 push 이벤트 발생 시 자동으로 실행하도록 설정했기 때문에 main 브랜치에 commit을 push 하면 자동으로 액션이 실행됩니다.

[##_Image|kage@xBeQv/btsB6gk6eGi/qfDES1mNCW3eHPScMMnXa1/img.png|CDM|1.3|{"originWidth":830,"originHeight":894,"style":"alignCenter","width":600,"height":646,"caption":"수많은 실패의 흔적"}_##]

사실 완성된 cicd.yml 파일을 보여주고 있지만 완성하기 위해서 수많은 실패를 겪었습니다.

[##_Image|kage@JKuaZ/btsB6OojEu5/l4oAeeGInS9DtieHYdgKMK/img.png|CDM|1.3|{"originWidth":557,"originHeight":538,"style":"alignCenter","width":600,"height":580,"caption":"배포 성공"}_##]

cicd 파이프라인 코드는 버전 업을 해서 속도가 빨라지는 거 아닌 이상 잘되는 액션을 수정할 일이 잘 없습니다.

### 전체 코드 확인
\- [https://github.com/bekurin/bekurin.github.io/blob/main/.github/workflows/cicd.yml](https://github.com/bekurin/bekurin.github.io/blob/main/.github/workflows/cicd.yml)

---
### 참고문헌
- 
---
### 연결문서
- 

