Redis Sorted Set은 key, value, 우선순위를 입력하여 우선순위에 맞게 정렬된 집합을 가지는 자료형입니다. (집합이기 때문에 동일한 value를 가질 수는 없습니다)

추가적으로 만약 같은 우선순위를 가진 서로 다른 value가 있다면 사전식으로 정렬하여 저장합니다.

Sorted Set 자료형의 사용 사례를 아래와 같습니다.
- reader board: 대규모 온라인 게임에서 가장 높은 점수를 가진 플레이어 목록을 보여준다.
- rate limiter: 처리율 제한 알고리즘 미들웨어를 구축할 수 있습니다.

집합은 순서를 가지지 않지만 우선순위에 따라 정렬되고, 모든 value가 key를 가지므로 우선순위 큐와 해시와 비슷한 구조를 가집니다.

참고문서
- https://redis.io/docs/data-types/sorted-sets/
