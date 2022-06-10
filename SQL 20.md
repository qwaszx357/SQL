# SQL 20

관계명 데이터베이스를 제어하기 위한 언어이다.

## SQL 기본 및 활용 - SQL 기본

### 1. WHERE

#### 1-1. WHERE절

- 자신이 **원하는 자료만을 검색**하기 위해 이용
- Where절에 조건이 없는 FTS (Full Table Scan) 문장은 SQL 튜닝 1차 검토 대상임
- FTS가 무조건 나쁜 것은 아님 - 병렬처리를 이용해 유용하게 사용할 수 있음

#### 1-2. Where - 연산자 종류

- 비교 연산: =, >, >=, <=
- 부정 비교 연산: !=, ^=, <>, NOT 컬럼명 =, NOT 컬럼명 >

- SQL 연산: Between a AND b, IN (list), Like '비교 문자열', IS NULL
- 부정 SQL 연산: NOT Between a AND b, NOT IN (list), IS NOT NULL
- 논리 연산: AND, OR, NOT

#### 1-3. Where - 연산자 우선순위

- **부정 => 비교, SQL => 논리**
- () > NOT (부정 연산자) > 비교 연산자, SQL 연산자 > AND > OR

#### 1-4. Where - SQL 연산자

- **Brtween a AND b**: a와 b 사이의 모든 값 (a,b 포함)
- **IN (list)**: 리스트 안에 있는 값 중 하나라도 일치하면 True, 없으면 False
- **LIKE** '비교문자열': 비교 문자열과 형태가 일치하면 됨
  - `%` : 0개 이상의 문자열
  - `_` : 1개의 단일 문자

#### 1-5. Where - IS NULL 과 IS NOT NULL

- IS NULL: NULL 값이면 True, 아니면 False (Null인 것만 찾기)
  - **NULL값과 수치 연산은 NULL 값 리턴**
    - 30 + 40 + NULL = NULL
    - 50 / NULL = NULL
    - 20 * '' = NULL
  - NULL값과 비교 연산은 False를 리턴
- IS NOT NULL: 널이 아닌 경우를 찾기 위해 사용

#### 1-6. Where - 논리 연산자

- 우선순위
  - **() > NOT > AND > OR**

#### 1-7. Where - 부정 연산자

- 부정 논리 연산자

|    연산자    |              연산자의 의미              |
| :----------: | :-------------------------------------: |
|      !=      |               같지 않다.                |
|      ^=      |               같지 않다.                |
|      <>      | 같지 않다. (모든 운영체제에서 사용가능) |
| NOT 컬럼명 = |             ~와 같지 않다.              |
| NOT 컬럼명 > |            ~보다 크지 않다.             |

- 부정 SQL 연산자

|       연산자        |                연산자의 의미                 |
| :-----------------: | :------------------------------------------: |
| NOT BETWEEN a AND b | a와 b의 값 사이에 있지 않다. (a,b 포함 안함) |
|    NOT IN (list)    |          list 값과 일치하지 않는다.          |
|     IS NOT NULL     |            NULL 값을 갖지 않는다.            |

#### 1-8. RowNum (oricle)

- 컬럼과 비슷한 성격의 Pseudo Column
- SQL 처리 결과 집합의 각 행에 대해 임시로 부여되는 일련번호
- 테이블이나 집합에서 원하는 만큼의 행만 가져올 때, **Where에서 행의 개수를 제한**하는 용도

```sql
SELECT 컬럼 명 FROM 테이블 명 WHERE ROWNUM <= 3; 
```

> 출력 결과의 3번째 행까지만 출력됨

#### 1-9. TOP (SQL Server)

- select 결과물의 행의 수를 제한 (맨 위에 n개만 출력)
- TOP (Expression) [PERCENT] [WITH TIES];
- `Expression`: 결과를 리턴할 행의 수를 지정하는 int 값
- `PERCENT`: 쿼리 결과 집합에서 처음 Expression%의 행만 반환됨을 나타냄
- `WITH TIES`: Order by 절이 지정된 경우에만 사용 가능. 동점은 추가 출력함