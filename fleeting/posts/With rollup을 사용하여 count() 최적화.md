## 2. With rollup을 사용하여 count(*) 최적화*
저장된 데이터를 group by를 사용하여 개수를 세는 경우 group by로 그룹핑된 값의 총합을 얻고 싶은 경우가 있습니다.

보통 조회한 결과로 application 레벨에서 총합을 개산하거나 전체 개수를 조회하는 쿼리를 한번 더 실행시키는 것을 고려해볼 수 있습니다.

이때, roll up을 사용하면 한번의 쿼리로 총합의 개수까지 가져올 수 있습니다.

with rollup은 하나의 컬럼에만 사용할 수 있을 것으로 생각된다.
대기 탑승권을 조회하는데 마지막 컬럼에 with rollup을 적용하면 각 노선의 대기 탑승권의 총합을 가져올 수 있나?

### 예시 #1 - 쿼리 2번을 실행시켜 총합을 가져오는 경우

	select title, count(*) from titles 
		group by title;
	
	-> Table scan on <temporary>  (actual time=196..196 rows=7 loops=1)
	    -> Aggregate using temporary table  (actual time=196..196 rows=7 loops=1)
	        -> Covering index scan on titles using PRIMARY  (cost=44579 rows=442664) (actual time=0.112..83.5 rows=443308 loops=1)
	
	select count(*) from titles;
	-> Count rows in titles  (actual time=28.3..28.3 rows=1 loops=1)
	


### 예시 #2 - with rollup을 사용하여 한번에 총합을 가져오는 경우
	select title, count(*) from titles
			group by title with rollup;
	
	-> Group aggregate with rollup: count(0)  (cost=88846 rows=666) (actual time=213..259 rows=8 loops=1)
	    -> Sort: titles.title  (cost=44579 rows=442664) (actual time=211..225 rows=443308 loops=1)
	        -> Index scan on titles using PRIMARY  (cost=44579 rows=442664) (actual time=0.0721..88.3 rows=443308 loops=1)

![]()

