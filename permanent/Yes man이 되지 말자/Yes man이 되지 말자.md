### 생성 날짜: 2024-01-08T20:35
### 주제: Yes man이 되지 말자
---
### 본문:
지난 1년 간 백엔드 직무를 맡으면서 수많은 요구사항을 구현했지만 모든 요구사항을 구현 중에 사용자의 필요성을 고려한 것은 아니어도 어떻게 하면 사용성을 개선하고, 조금 더 편하게 기능을 사용할 수 있을지 고민을 많이 했습니다.

이렇게 일을 하면서 요구사항 구현이 확정된 상태에서 사용성을 고민하는 것은 습관이 되었는데. 최근 몇가지 문의 사항을 구현하다 보면서 돌아보니 정말 필요한 기능인지 고민하는 습관이 잘 들지 않았다는 생각이 들었습니다.

진행 중인 프로젝트 등 외부 요인을 모두 제거한 이상적인 요구사항 분석 및 구현은 아래와 같습니다.

(외부 요인을 최대한으로 제거했기 때문에 실무와 맞지 않는 상황이 있을 수 있습니다)

1.  기능 구현 문의가 들어온다.
2.  정말 필요한 기능인지 분석한다. (다른 팀의 협업은 필요 없는지도 같이 분석한다)
3.  수기 대응 비용과 개발 비용을 추측하여 비교한다.
4.  수기 대응 비용이 비싸다면 기능을 구현하는 것으로 결정되고, 6번으로 이동한다.
5.  개발 비용이 비싸다면 수기 대응을 당분간 지속하고, 문의를 종료한다.
6.  유지보수가 가능하고, 사용성이 좋은 기능으로 구현한다... (이하 생략)

2번~5번의 의사 결정은 마치 여러 항목을 두고, 저울질을 하는 것과 비슷한데요. 결정이 잘못 이뤄지면 개발팀과 수기 대응하는 팀 모두 주어진 시간을 효율적으로 사용하지 못합니다.

![[개발_수기_저울.png]]

문의 사항을 구현하기 위해서는 머릿속으로 몇 초만에 비용을 계산할 수 있는 일은 거의 없습니다. 개발 비용과 수기 대응 비용에 포함되는 항목은 아래와 같습니다.

-   개발 비용
    -   프로젝트 도메인 지식
    -   레거시 코드 분석
    -   코드 수정으로 영향도 분석
    -   다른 팀과 협업이 필요한지 결정
-   수기 대응 비용
    -   고객에게 전화 또는 문자로 안내
    -   데이터 정합성을 위한 검증
    -   반복작업 수행

물론 각 팀의 팀장이 있기 때문에 이를 결정을 하겠지만 이렇게 생각하고, 구현이 결정된 사항을 모두 ok라고 외쳐버리면 속된 말로 코드 싸는 기계가 되는 것 같습니다.

![[코싸기.png]]

비용을 계산하여 일을 할 것인지 말것인지를 결정하는 것은 팀장의 중요한 역량 중 하나라고 생각하지만 팀원으로써 합리적이라면 의견을 전달하는 것도 하나의 중요한 역할이라는 생각이 듭니다.

---
### 참고문헌
- 
---
### 연결문서
- 

