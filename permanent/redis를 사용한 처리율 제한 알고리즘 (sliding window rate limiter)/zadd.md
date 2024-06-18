참고문서
- https://redis.io/commands/zadd/

| title           | description                                       |
| --------------- | ------------------------------------------------- |
| Available since | 1.2.0                                             |
| Time complexity | O(log(N))이며, N은 정렬된 집합의 원소 개수입니다. |
| ACL categories  | `@write`, `@sortedset`, `@fast`                   | 