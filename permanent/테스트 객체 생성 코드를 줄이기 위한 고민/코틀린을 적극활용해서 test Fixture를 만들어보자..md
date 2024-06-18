### 생성 날짜: 2023-11-19T15:11
### 주제: 코틀린을 적극활용해서 test Fixture를 만들어보자.
---
### 본문:
```
class PlaceSubject {
    private var name: String = "이름"
    private var address: String = "주소"
    private var point: Point = Point(RandomNumber.createRandomLatitude(), RandomNumber.createRandomLongitude())

    fun of(point: Point, address: String, name: String): Place {
        return Place(point, address, name)
    }

    fun any(): Place {
        return Place(point, address, name)
    }

    fun setName(name: String): PlaceSubject {
        this.name = name
        return this
    }

    fun setAddress(address: String): PlaceSubject {
        this.address = address
        return this
    }

    fun setPoint(point: Point): PlaceSubject {
        this.point = point
        return this
    }

    fun build(): Place {
        return Place(point, address, name)
    }
}
```
이전에 위와 같이 코드를 작성한 적이 있었는데요.

조금 더 생각해보니 필드가 50개 이상 100개 이상이 되는 테이블이 존재할 때 Subject 클래스 크기가 1,000, 10,000줄 이상이 될 수 있겠다는 생각이 들었습니다.

이에 코틀린의 default parameter를 사용하는 방법 & test Fixture에 따라 객체를 생성해주는 함수를 구현하는 법을 고민했습니다.

코드는 아래와 같습니다.
```
class PlaceSubject {
	fun of(point: Point = Point(RandomNumber.createRandomLatitude(), RandomNumber.createRandomLongitude(), address: String = "주소", name: String = "이름"): Place {
        return Place(point, address, name)
    }

	fun createInvalidPoint(point: Point = Point(-1, -1)): Place {
		return Place(point, "주소", "이름")
	}

	fun createInvalidAddressAndName(address: String = "!@#주소", name: String = "%^$이름"): Place {
		val point = Point(RandomNumber.createRandomLatitude(), RandomNumber.createRandomLongitude()
		return Place(point, address, name)
	}
}
```

기본적으로 성공 케이스는 of 함수를 활용하여 Test Fixture를 생성하고, 실패 케이스에 대해서는 케이스에 맞는 함수를 구현하여 활용할 수 있도록 합니다.

이렇게 하는 이유는 일반적으로 성공 케이스에 비해 실패 케이스의 수가 더 많기 때문인데요.
```
# 실패 케이스
- AAA를 할 때 BBB 하는 경우 실패한다.
- AAA를 할 때 CCC 하는 경우 실패한다.
- AAA를 할 때 DDD 하는 경우 실패한다.
- AAA를 할 때 EEE 하는 경우 실패한다.
- AAA를 할 때 FFF 하는 경우 실패한다.
- AAA를 할 때 GGG 하는 경우 실패한다.

# 성공 케이스
- AAA를 할 때 HHH 하는 경우 성공한다.
```

따라서 실패 케이스에 대해서 재사용성을 더 고려해줘야 한다고 생각했습니다.

---
### 참고문헌
- 
---
### 연결문서
- 

