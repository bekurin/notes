### 생성 날짜: 2023-12-19T21:53
### 주제: RuntimeException이 왜 기본 롤백인지 알아?
---
### 본문:
`RuleBasedTransactionAttribute`를 살펴보면 rollbackOn이라는 함수가 있고, `DefaultTransactionAttribute` 클래스를 상속하고 있다.

DefaultTransactionAttribute가 롤백 여부를 결정하는 rollbackOn을 구현하는 함수를 최초로 구현하게 되는데 구현은 다음과 같다.

```
public boolean rollbackOn(Throwable ex) {  
	return ex instanceof RuntimeException || ex instanceof Error; 
}
```
RuntimeException과 Error instance type을 가진 경우 rollbackOn이 true를 반환하고, true인 경우 롤백을 진행하기 때문에 RuntimeException이 발생하면 기본적으로 롤백을 진행하는 것으로 이해하는 것이다.

그렇다면 Transactional annotation을 사용하여 RuntimeException인 경우에도 noRollbackFor 파라미터를 사용하여 롤백을 진행하지 않을 수도 있는데. 이는 RuleBasedTransactionAttribute의 rollbackOn 함수 구현을 봐야한다.

구현은 다음과 같다.

```
public boolean rollbackOn(Throwable ex) {  
	RollbackRuleAttribute winner = null;  
	int deepest = Integer.MAX_VALUE;  
	if (this.rollbackRules != null) {  
		Iterator var4 = this.rollbackRules.iterator();  
		while(var4.hasNext()) {  
			RollbackRuleAttribute rule = (RollbackRuleAttribute)var4.next();  
			int depth = rule.getDepth(ex);  
			if (depth >= 0 && depth < deepest) {  
				deepest = depth;  
				winner = rule;  
			}  
		}  
	}  
  
	if (winner == null) {  
		return super.rollbackOn(ex);  
	} else {  
		return !(winner instanceof NoRollbackRuleAttribute);  
	}  
}
```

rollbackRules는 RuleBasedTransactionAttribute 초기화 시에 설정되는 값으로 각 규칙은 `RollbackRuleAttribute` 또는 `NoRollbackRuleAttribute` 객체이다.
- `NoRollbackRuleAttribute` 은 `RollbackRuleAttribute`을 상속한다.

RuleBasedTransactionAttribute의 rollbackOn은 다음과 같은 순서로 동작한다.
rollbackRules를 초기화 하면서 파라미터로 주어진 예외가 getDepth에 매칭이 되는지 확인한다.
getDepth에 매칭되는 예외가 하나라도 있다면 winner에 값이 채워지고 이때, winner가 NoRollbackRuleAttribute 인스턴스라면 롤백을 하지 않고, RollbackRuleAttribute 인스턴스라면 롤백을 진행한다.

그렇다면 rollbackRules는 어디서 초기화 되는 것인가?
TxAdviceDefinitionParser 클래스의 parseAttributeSource 함수 내부에서 설정을 해주게 되는데. 이 값은 Transactional annotation에 있는 rollbackFor, noRollbackFor에 저장된 값이 들어가게 된다.

---
### 참고문헌
- TxAdviceBeanDefinitionParser 도 살펴보자.
---
### 연결문서
- 

