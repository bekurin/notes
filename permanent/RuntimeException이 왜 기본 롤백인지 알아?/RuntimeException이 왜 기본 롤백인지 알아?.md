### 생성 날짜: 2023-12-19T21:53
### 주제: RuntimeException이 왜 기본 롤백인지 알아?
---
### 본문:
RuntimeException과 Error가 spring boot에서 org.springframework.boot:spring-boot-starter-data-jpa를 사용할 때 기본 롤백 설정인 것을 어렵지 않게 알 수 있습니다.

spring boot에서 RuntimeException과 Error가 왜 기본 롤백으로 설정되어 있는지 Transaction 어노테이션의 noRollbackFor, RollbackFor 옵션을 넣어주는 것이 어떻게 롤백 여부를 결정할 수 있는 것인지 알아보도록 하겠습니다.

아래와 같은 순서로 글을 작성해 보겠습니다.

-   RuntimeException, Error가 왜 기본 롤백인지
-   rollbackFor, noRollbackFor 값을 설정하면 어떻게 롤백 여부를 결정하는가?
-   RollbackRuleAttribute, NoRollbackRuleAttribute는 무엇인가?

## RuntimeException, Error가 왜 기본 롤백인가?

이유는 간단합니다. DefaultTransactionAttribute에 정의된 rollbackOn 함수의 반환 결과에 따라 롤백을 할지 말지를 결정하게 되는데요.

[##_Image|kage@bo3wDU/btsCr8mxucZ/fxY4Ir8xrulBsNGcBkJD7k/img.png|CDM|1.3|{"originWidth":567,"originHeight":114,"style":"alignCenter","caption":"DefaultTransactionAttribute rollbackOn 함수 구현"}_##]

rollbackOn의 반환 결과가 true인 경우 롤백을 하고, false인 경우 롤백을 하지 않습니다. noRollbackFor, rollbackFor를 정의하지 않은 경우 기본 롤백 정책이 선택되게 되는데. 위의 코드를 보고 알 수 있지만 기본 롤백 설정은 RuntimeException 또는 Error인 경우에 롤백이 되도록 설정되어 있기 때문에 RuntimeException, Error가 기본적으로 롤백을 시도하게 됩니다.

## rollbackFor, noRollbackFor 값을 설정하면 어떻게 롤백 여부를 결정하는가?

rollbackFor, noRollbackFor가 설정되게 되면 RuleBasedTransactionAttribute 클래스에 정의된 rollbackOn 함수가 실행되게 됩니다. 구현은 아래와 같습니다.

[##_Image|kage@cQnjTj/btsCpyTO5TI/BDB5lIMBDYLK9OkULeypr1/img.png|CDM|1.3|{"originWidth":587,"originHeight":462,"style":"alignCenter","caption":"RuleBasedTransactionAttribute rollbackOn 함수 구현"}_##]

rollbackRules를 순환하면서 현재 예외가 Transcational annotation의 파라미터로 설정된 rollbackFor, noRollbackFor에 해당하는 예외인지 확인합니다.

하나라도 포함되면 그 값은 winner에 저장되게 되고, winner의 인스턴스 타입이 NoRollbackRuleAttribute라면 false를 반환하고, 인스턴스 타입이 NoRollbackRuleAttribute이 아니라면 true를 반환하여 롤백을 진행합니다.

## RollbackRuleAttribute, NoRollbackRuleAttribute는 무엇인가?

RollbackRuleAttribute는 Transactional annotataion에 rollbackFor 파라미터에 설정된 값을 말합니다. 반대로 NoRollbackRuleAttribute는 noRollbackFor에 설정된 예외 타입으로 TxAdviceDefinitionParser의 parseAttributeSource 함수 호출 시에 값이 설정됩니다. 설정 코드는 아래와 같습니다.

[##_Image|kage@sRmqC/btsCrYEv12j/7gJF69yEZ0iSA63wxLr6Z0/img.png|CDM|1.3|{"originWidth":701,"originHeight":259,"style":"alignCenter","caption":"TxAdviceDefinitionParser parseAttributeSource 함수 구현"}_##]

롤백 여부를 구분하는 rollbackOn 함수에서 사용하는 rollbackRules가 위 함수에서 초기화됩니다.

## 마무리

RuntimeException과 Error가 default 롤백인지 확인하는 것과 동시에 Transcational annotation의 rollbackFor, noRollbackFor에 값 설정 시에 어떻게 초기화를 하고, 어디에서 사용되는지 확인했습니다.

---
### 참고문헌
- 
---
### 연결문서
- 

