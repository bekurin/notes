### 생성 날짜: 2024-01-04T21:06
### 주제: git branch 전략
---
### 본문:
git, gihub, gitlab, trunk based development 브랜치 전략에 대해 간략하게 소개하도록 하겠습니다. 각 전략의 장/단점을 파악하여 프로젝트 성격에 맞게 적용해 보면 좋을 것 같습니다.

## Git Flow

**설명**: Git Flow는 Vincent Driessen이 제안한 모델로, 기능 개발, 릴리스 준비, 유지보수, 핫픽스 등을 관리하기 위해 여러 종류의 브랜치를 사용합니다. 주요 브랜치는 `master`, `develop`, `feature`, `release`, `hotfix`입니다.

-   `master`: 안정적인 릴리스 버전을 관리합니다.
-   `develop`: 다음 릴리스를 위한 개발 작업이 진행됩니다.
-   `feature`: 새로운 기능 개발을 위한 브랜치입니다.
-   `release`: 릴리스 준비를 위한 브랜치입니다.
-   `hotfix`: 긴급한 버그 수정을 위한 브랜치입니다.

**장점**:

-   명확한 구조로 인해 큰 프로젝트에서 효과적입니다.
-   릴리스와 유지보수가 체계적으로 관리됩니다.

**단점**:

-   복잡하고 브랜치 관리가 많아집니다.
-   소규모 또는 빠른 개발 사이클에는 비효율적일 수 있습니다.

다음은 주요 브랜치 흐름과 시각화된 자료입니다.

[##_Image|kage@becHZf/btsC4rZ3GKj/dUJC4r8AocRkGNE3Imm5ek/img.jpg|CDM|1.3|{"originWidth":800,"originHeight":574,"style":"alignCenter","width":600,"height":431,"caption":"출처:&amp;nbsp;https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow"}_##]

-   `feature` 브랜치들은 `develop`에서 분기합니다.
-   `develop` 브랜치는 개발의 중심입니다.
-   `release` 브랜치는 `develop`에서 분기하여 준비 후 `master`로 병합됩니다.
-   `hotfix` 브랜치는 `master`에서 직접 분기하여 긴급 수정 후 다시 `master`로 병합됩니다.

## GitHub Flow

**설명**: GitHub에서 사용하는 간소화된 브랜치 전략입니다. `master` 브랜치 하나에 집중하며, 새로운 기능이나 수정 사항은 `feature branch`를 생성하여 작업한 후 `master`에 병합합니다.

**장점**:

-   단순하고 이해하기 쉽습니다.
-   지속적인 배포와 통합에 적합합니다.

**단점**:

-   복잡한 릴리스 관리에는 적합하지 않을 수 있습니다.
-   큰 규모의 프로젝트에서는 관리가 어려울 수 있습니다.

다음은 주요 브랜치 흐름과 간략하게 시각화한 자료입니다.

```
[feature]--->\
[feature]---->[master]<----[feature]
[feature]--->/
```

-   모든 `feature` 브랜치는 `master`에서 분기합니다.
-   `feature` 브랜치는 개발 후 `master`로 병합됩니다.
-   `master` 브랜치는 항상 배포 가능한 상태를 유지합니다.

## GitLab Flow

**설명**: GitLab Flow는 Git Flow와 GitHub Flow의 장점을 결합한 전략입니다. `master` 브랜치에는 항상 배포 가능한 코드를 유지하고, 환경별 브랜치(예: `production`, `staging`)를 사용하여 배포 관리를 합니다.

**장점**:

-   배포와 환경 관리에 유연합니다.
-   지속적인 통합 및 배포(CI/CD)에 적합합니다.

**단점**:

-   환경별 브랜치 관리가 필요합니다.
-   Git Flow보다는 간단하지만 여전히 복잡할 수 있습니다.

다음은 주요 브랜치 흐름과 간략하게 시각화한 자료입니다.

```
[feature branch 1]--->\
[feature branch 2]---->\       /--->[production]
[feature branch 3]----->[master]--->[staging]
                        /       \--->[testing]
[feature branch 4]---->/
[feature branch 5]--->/
```

-   `feature` 브랜치들은 `master`에서 분기합니다.
-   `master` 브랜치는 중앙 집중식 개발 브랜치입니다.
-   `master`에서 환경별 브랜치로 (예: `production`, `staging`) 코드가 이동합니다.

## Trunk Based Development

**설명**: 모든 개발자가 `trunk` 또는 `master` 브랜치에서 짧은 주기로 작업하고, 빈번하게 병합하는 전략입니다. 기능 토글(feature toggle)을 사용하여 미완성 기능을 관리합니다.

**장점**:

-   빠른 통합과 지속적인 배포에 유리합니다.
-   병합 충돌을 최소화합니다.

**단점**:

-   기능 토글 관리가 필요합니다.
-   팀원 간 긴밀한 협업과 의사소통이 필요합니다.

다음은 주요 브랜치 흐름과 간략하게 시각화한 자료입니다.

```
[feature]--->\
[feature]---->[trunk/master]---->[release]
[feature]--->/
```

-   모든 `feature` 브랜치는 `trunk` 또는 `master`에서 짧은 주기로 분기하고 병합됩니다.
-   `trunk` 또는 `master` 브랜치는 항상 최신 상태를 유지합니다.
-   `release` 브랜치는 정기적으로 `trunk`에서 분기하여 배포 준비를 합니다.

## 마무리

현재 일하고 있는 회사에서는 git flow를 사용하고 있습니다. 하지만 각 feature 브랜치마다 테스트를 위한 배포가 가능하다면 빠른 주기로 배포된 사항을 확인할 수 있는 trunk based development 전략을 사용해보고 싶다는 생각이 듭니다.

---
### 참고문헌
- 
---
### 연결문서
- 

