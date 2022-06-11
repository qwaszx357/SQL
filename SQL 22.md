# SQL 22

관계명 데이터베이스를 제어하기 위한 언어이다.

## SQL 기본 및 활용 - SQL 기본

### 1. Group By - Having 절

#### 1-1. 집계함수 (Aggregate Func)

- 여러 행들로 구성된 그룹들이 모여서 그룹당 하나의 결과를 돌려주는 **다중행 함수**
- GROUP BY 절은 행들을 소그룹화 함
- Select, Having, Order By 절에서 사용 가능

#### 1-2. 집계함수명

- ALL / Distinct - Default 값은 ALL
- 주로 숫자형에서 사용 (MAX, MIN, COUNT는 문자, 날짜도 적용 가능)

![제 7절 GROUP BY HAVING 절 : 네이버 블로그](https://mblogthumb-phinf.pstatic.net/20151204_36/liberty264_1449240431458DVp1N_JPEG/1.jpg?type=w2)

- COUNT(*)만 NULL 포함해서 체크
- COUNT(컬럼명), SUM, AVG, IN, BETWEEN 등은 NULL 포함 안함

#### 1-3. Group By 절

- 데이터들을 작은 그룹으로 분류하여 소그룹에 대한 통계정보를 얻을 때 사용
- ROLLUP이나 CUBE에 의한 소계가 계산된 결과에는 GROUPUNG(EXPR) = 1이 표시됨
- 그 외 결과에는 GROUPING(EXPR) = 0이 표시됨

```sql
Select Distinct 컬럼명 FROM 테이블 명
WHERE 조건식
GROUP BY 컬럼 / 표현식
HAVING 그룹의 조건식;
```

#### 1-4. Having 절

- Where절과 차의
  - Group By 뒤에 옴 (앞에 사용해도 에러는 안남)
  - 집계함수 사용 가능
- Where절 조건 변경은 출력되는 레코드 개수가 변경되고, 결과 데이터 값이 변경될 가능성 있음
- Having절 조건 변경은 출력되는 레코드 개수는 변경되지만, 결과 데이터 값은 변경 안됨
- **Select - From - Having도 가능**

#### 1-5. Group By와 Having의 특징

- **Group By에 의한 소그룹별로 만들어진 집계 데이터 중, Having 조건을 만족하는 내용만 출력**
- 가능하면 Group By하기 전에, Where절로 대상을 줄이는 것이 효과적
- Where절은 전체 데이터를 Group으로 나누기 전에 필요없는 조건을 미리 제거하는 역할
- Having은 Group By로 만들어진 소그룹에 대해서만 조건

### 2. ORDER BY 절

#### 2-1. Order By

- Order By에는 **Group By의 컬럼이나 Select의 컬럼만** 올 수 있음
- 숫자형 오름차순 - 작은 값부터 출력 / 날짜형 오름차순 - 빠른 날부터 출력
- `oracle` - NULL 값을 가장 큰 값으로 간주
- `SQL Server` - NULL 값을 가장 작은 값으로 간주
- 만약 Order By 1,2를 실행하면 1번 컬럼 기준으로 정렬한 후, 2번 컬럼 기준으로 정렬

#### 2-2. Select문의 실행 순서

|               실행 순서               |                       설명                       |
| :-----------------------------------: | :----------------------------------------------: |
|           5. Select 컬럼명            |              1. 테이블 참조 (From)               |
|           1. From 테이블명            |   2. 효율을 위해 조건에 안맞는 것 제거 (Where)   |
|            2. Where 조건식            |           3. 행들을 그룹화 (Group By)            |
|       3. Group By 컬럼 / 표현식       | 4. 그룹핑 된 값의 조건에 맞는 것만 도출 (Having) |
|        4. Having 그룹의 조건식        |      5. 도출된 결과를 출력 / 계산 (Select)       |
| 6. Order By 컬럼 / 표현식 (ASC/DESC); |     6. 출력 결과를 정렬한 후 출력 (Order By)     |

#### 2-3. TOP N 쿼리

- SQL Server에서 Order By 한 후에 TOP를 실행하면 상위, 하위권 데이터를 추출 가능

```sql
SELECT TOP(3) WITH TIES 컬럼명 FROM 테이블 명
ORDER BY 컬럼명 DESE;
```

