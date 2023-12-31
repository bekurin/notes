생성일시: 2023-11-21T21:37
### 인용문
> 셋 데이터를 사용하여 집합 연산을 알아보기 위해서 트워터의 팔로잉 구조를 예로 들어보자. 팔로잉 구조는 단방향 친구 맺기로 볼 수 있다.
### 생각
![[followeing-structure.png]]

위 그림과 같이 userA, userB, userC가 각각 서로 팔로잉과 팔로우를 하고 있을 때 어떻게 표현할 수 있을까?

표현하기에 앞서 팔로잉 구조의 요구사항을 생각해보면 다음과 같은 항목들이 나온다.
1. 팔로우는 중복될 수 없다.
2. 팔로잉은 중복될 수 없다.
3. 본인의 팔로우와 팔로잉 목록을 알 수 있다.
4. 서로 팔로잉하는 사람을 알 수 있다.

1번, 2번 요구사항을 위해서는 배열이나 해쉬를 사용하는 것보다 애초에 중복을 허용하지 않는 집합을 사용하면 간단하게 해결할 수 있다.

3번은 첨부한 사진과 같이 다음 2개의 키를 만들어주는 것으로 해결할 수 있다. 
- `<userId>:follow` -> 내가 팔로우하는 사용자 목록
- `<userId>:follower`-> 나를 팔로잉하는 사용자 목록

4번은 교집합 연산을 통해 해결할 수 있다. 명령어는 다음과 같다.
```
sinter <userId>:follow <userId>:follower
```
첨부한 이미지의 userA를 예로 들면 교집합 연산을 통해 userA와 userC는 서로 팔로잉, 팔로우를 하는 관계인 것을 알 수 있다.

### 마무리
집합으로 팔로우, 팔로잉 관계를 표현할 수 있지만 1가지 유의할 점은 집합의 교집합 연산은 비용이 많이 든다는 것이다.

레디스 교집합 연산: O(N * M) N은 교집합을 실행할 2개의 집합 중 크기가 더 작은 집합 수 M은 교집합 연산을 실행할 집합 수