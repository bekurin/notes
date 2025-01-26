참고문서
- https://redis.io/commands/zremrangebyscore/

| title           | description                                                                              |
| --------------- | ---------------------------------------------------------------------------------------- |
| Available since | 1.2.0                                                                                    |
| Time complexity | O(log(N)+M)이며, N은 정렬된 집합의 원소 개수이고 M은 연산에 의해 제거된 원소 개수입니다. |
| ACL categories  | `@write`, `@sortedset`, `@slow`                                                          ||                 |                                                                                          |
