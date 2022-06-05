# SQL 18

관계명 데이터베이스를 제어하기 위한 언어이다.

## SQL 기본 및 활용 - SQL 기본

### 1. DML

#### 1-1. DML

- 호스트 프로그램 속에 삽입되어 사용됨
- **데이터 부속어**라고도 함
- Procedural DML - 절차적 데이터 조작어
  - 초급언어
  - 사용자가 무슨 데이터(what)를 원하고, 어떻게(how) 접근해 처리할 것인지 명세함
- Nonprocedural DML - 비절차적 데이터 조작어
  - 고급업어
  - 사용자가 무슨 데이터(what)를 원하는지만 명세
  - 사용하가 원하는 데이터만 선언하기 때문에 **선언적 언어**라고도 함

#### 1-2. DML - Insert

- 각 컬럼별 값을 입력
- 데이터가 문자형일 경우 `' '`로 묶어서 입력

```sql 
INSERT INTO 테이블 명 (컬럼명들 (생략 시 전체 컬럼)) VALUES (컬럼명 순서에 맞는 값 맵핑);
```

#### 1-3. DML - Update

- 각 컬럼별 값을 수정

```sql
UPDATE 테이블 명 SET 컬럼명 = 값 WHERE 조건;
```

#### 1-4. DML - Delete

- 각 컬럼별 값을 삭제

```sql
DELETE FROM 테이블 명 WHERE 조건;
```

#### 1-5. DML - Select

- ALL: 기본 옵션 (중복 데이터 모두 출력)
- DISTINCT: 중복 제거 (중복은 하나로 출력)

```sql
SELECT * FROM 테이블 명;
SELECT DISTINCT 컬럼명 FROM 테이블 명;
SELECT 컬럼명 AS 컬럼 별명 FROM 테이블 명;
```

#### 1-6. DML 산술 연산자 우선순위

- `()` > `*` > `/` > `+` > `-`

#### 1-7. DML - 합성 연산자

- 문자와 문자를 연결
- `oracle` - ||
- `SQL Server` - +

#### 1-8. 삭제 SQL 비교

|        Drop Table         |      Truncate Table       |          Delete From           |
| :-----------------------: | :-----------------------: | :----------------------------: |
|            DDL            |     DDL (일부는 DML)      |              DML               |
|        Auto Commit        |        Auto Commit        |         사용자 Commit          |
|       RollBack 불가       |       RollBack 불가       |   Commit 전에 RollBack 가능    |
| 테이블의 모든 데이터 삭제 | 테이블의 모든 데이터 삭제 |   테이블의 모든 데이터 삭제    |
| 디스크 초기화 (로그 제거) | 디스크 초기화 (로그 제거) | 디스크 초기화 안함 (로그 유지) |
| 스키마 정의까지 모두 삭제 |  테이블 스키마 구조 유지  |    테이블 스키마 구조 유지     |

