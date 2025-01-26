### 생성 날짜: 2023-10-05T21:29
### 주제: redis Geospatial을 사용하여 근처 정류장 검색
---
### 본문: 
redis에서는 많은 자료형을 제공해주는데 이 중에서 [[Geospatial]]을 사용하면 위, 경도, 반경을 사용하여 이에 포함되는 값을 검색할 수 있습니다.

사용할 수 있는 명령어는 아래와 같습니다.
- [[geoadd]]: 키, 경도, 위도, 이름을 파라미터로 받아 값을 생성합니다.
- [[geosearch]]: 키, 검색 타입, 반경, 경도, 위도를 파라미터로 받아 해당하는 값을 반환합니다.
두 명령어의 실행 시간은 모두 O(n) 보다 작습니다.

![[geosearch-result.png]]

---
### 참고문헌
- https://redis.io/docs/data-types/geospatial/
---
### 연결문서
- [[Geospatial]]
- [[geoadd]]
- [[geosearch]]

