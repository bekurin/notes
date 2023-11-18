### 생성 날짜: 2023-11-18T17:57
### 주제: JPA를 사용할 때 init scope가 적용되지 않는 이유
---
### 본문:
kotlin + spring boot를 사용하여 프로젝트를 구성했고, kotlin의 Init을 사용하여 도메인 규칙을 적용했습니다.

하지만 어떤 이유에서인지 데이터베이스에 도메인 규칙을 위반하는 데이터를 넣고, 조회를 시도하니 조회가 정상적으로 이뤄졌습니다.
- not null 필드에 null

조금 조사를 해보니 결국 Kotlin 코드는 java로 컴파일되어서 실행되게 되는데.
이 과정에서 kotlin에서는 사용하지 않는 아무런 파라미터를 가지지 않는 default constructor가 생기게 됩니다.

만약 아래와 같은 코드가 있다고 할 때
```
@Entity  
class Person(  
	name: String,  
	age: Int  
) : PrimaryKeyEntity() {  
	init {  
		if (age < 1) {  
			throw IllegalArgumentException("나이는 1살 이상이어야합니다.")  
		}  
	}  
	  
	var name: String = name  
	protected set  
	  
	var age: Int = age  
	protected set  
}
```

java로 컴파일을 하면 아래와 같은 코드가 생성됩니다.
```
@Entity  
...
public class Person extends PrimaryKeyEntity {  
	@NotNull  
	private String name;  
	private int age;  
	  
	@NotNull  
	public String getName() {  
		return this.name;  
	}  
	  
	protected void setName(@NotNull String var1) {  
		Intrinsics.checkNotNullParameter(var1, "<set-?>");  
		this.name = var1;  
	}  
	  
	public int getAge() {  
		return this.age;  
	}  
	  
	protected void setAge(int var1) {  
		this.age = var1;  
	}  
	  
	public Person(@NotNull String name, int age) {  
		Intrinsics.checkNotNullParameter(name, "name");  
		super();  
		if (age < 1) {  
			throw (Throwable)(new IllegalArgumentException("나이는 1살 이상이어야합니다."));  
		} else {  
			this.name = name;  
			this.age = age;  
		}  
	}  
	  
	public Person() {  
	}  
}
```

JPA에서 데이터를 조회할 때는 우선 기본 생성자를 사용하여 객체를 생성하기 때문에 이름이나 나이에 값이 없어도 나이에 음수 값이 들어가도 조회가 정상적으로 수행될 수 있었던 것이었습니다.

---
### 참고문헌
- 
---
### 연결문서
- 

