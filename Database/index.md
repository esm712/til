## 인덱스가 중요한 이유

<code>SELECT \* FROM customer WHERE name = 'SeungMin';</code>

name에 인덱스가 걸려있지 않다면? 시간복잡도 : O(N)  
namd에 인덱스를 걸려있다면? 시간복잡도 : O(logN)

## 인덱스를 사용하는 이유(중요)

1. 조건을 만족하는 튜플들을 빠르게 조회하기 위하여
2. 빠르게 정렬(order by)하거나 그룹핑(group by)하기 위하여

## multicolumn index, composite index

두개 이상의 속성으로 구성된 인덱스

## B-tree 기반 인덱스 동작 방식

index 테이블에서 binary search를 진행한다.

## 쿼리가 어떤 인덱스를 쓰는지 확인하는 방법(MySQL 기준)

```
mysql> EXPLAIN
    -> SELECT * FROM customer WHERE name = 'SeungMin';
```

## 직접 인덱스를 고르는 방법(MySQL 기준)

Optimizer에게 인덱스 권장

```
mysql> SELECT * FROM customer
    -> USE INDEX (name)
    -> WHERE name = 'SeungMin';
```

Optimizer에게 인덱스 강제

```
mysql> SELECT * FROM customer
    -> FORCE INDEX (name)
    -> WHERE name = 'Seungmin';
```

## 인덱스를 막 만들어도 되는가?

**절대 NO!!**  
table에 값을 추가할때 index도 변경이 발생함  
추가적인 저장 공간을 차지함

## Covering index

- 조회하려는 속성들이 인덱스가 모두 커버하는 경우
- 조회 성능이 더 빠름
- 이유 : 인덱스 테이블에서 pointer를 통해서 조회의 과정을 거치지 않아도되기때문에

## Hash index

- hash table을 사용하여 index를 구현
- 시간복잡도 : O(1)
- rehashing에 대한 부담
- equality 비교 가능, range 비교 불가능
- multicolumn index의 경우 전체 attributes에 대한 조회 가능

## Full scan이 더 좋은 경우

- table에 데이터가 조금 있을 때
- 조회하려는 데이터가 테이블의 상당 부분을 차지할 때
