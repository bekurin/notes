### 생성 날짜: 2023-12-11T20:59
### 주제: spring aop를 사용하여 annotation 처리하기
---
### 본문:

커스텀 annotation 생성
```
@Target(AnnotationTarget.FUNCTION) 
@Retention(AnnotationRetention.RUNTIME)
annotation class Loggable
```

aspect 클래스 생성
```
@Aspect  
@Component  
class LoggingAspect {  
	private val logger = LoggerFactory.getLogger(this.javaClass)  
	  
	@Around("@annotation(Loggable)")  
	fun logMethodExecution(joinPoint: ProceedingJoinPoint): Any? {  
		val startTime = System.currentTimeMillis()  
		return try {  
			val result = joinPoint.proceed()  
			val endTime = System.currentTimeMillis()  
			logger.info("Method {} executed in {} ms", joinPoint.signature, endTime - startTime)  
			result  
		} catch (e: Exception) {  
			logger.error("Method {} failed: {}", joinPoint.signature, e.message) throw e  
		}  
	}  
}
```

위와 같이 구현하면 함수에 annotation만 달아두면 템플릿-메서드 패턴을 spring aop를 사용하여 손쉽게 구현할 수 있다.

---
### 참고문헌
- 
---
### 연결문서
- 

