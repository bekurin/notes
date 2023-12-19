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
1. 롤백 규칙 초기화: rollbackRules는 RuleBasedTransactionAttribute 초기화 시에 설정되는 값으로 각 규칙은 `RollbackRuleAttribute` 또는 `NoRollbackRuleAttribute` 객체이다.
	- `NoRollbackRuleAttribute` 은 `RollbackRuleAttribute`을 상속한다.
2. 예외와 일치하는 depth 계산: getDepth 함수는 전달받은 `Throwable` 객체(예외)에 대해, 각 롤백 규칙과의 일치 여부를 검사한다. `getDepth` 함수는 예외 타입이 규칙과 일치하는지, 그리고 얼마나 "깊이" 일치하는지를 반환한다. 가장 깊은 예외(deepest match)를 찾는다.
3. 우선순위 결정: 예외 타입이 여러 규칙과 일치할 수 있기 때문에, 가장 후보가 될 수 있는 예외를 찾는다(`deepest` 변수 사용). `deepest`는 일치하는 규칙의 "깊이"를 나타내며, 더 낮은 값이 더 구체적인 일치를 의미한다.
4. 롤백 여부 결정: `winner` 변수에는 후보가 될 예외를 저장한다. 이 규칙이 `NoRollbackRuleAttribute` 객체라면, 메소드는 `false`를 반환하여 롤백을 하지 않도록 합니다. 그렇지 않으면 `super.rollbackOn(ex)`를 호출하여 기본 롤백 로직을 따른다.

---
### 참고문헌
- 
---
### 연결문서
- 

