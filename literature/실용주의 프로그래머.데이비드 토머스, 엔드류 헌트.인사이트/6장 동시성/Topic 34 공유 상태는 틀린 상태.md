race condition에 놓인 공유 자원에 접근을 할 때 조회 조차 하지 못하게 해야 틀린 상태가 되지 않도록 할 수 있다.

> 세마포어는 단순히 한 번에 한 사람나이 가질 수 있는 무언가다. p.251

팟이 여러 개라면 세마포어를 적용한다고 해도 제어하기 어렵다.

분산락, 트랜잭션 관리 레벨 + 비관적/낙관적 락을 사용해보도록 하자.
