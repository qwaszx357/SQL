# SQL 15

관계명 데이터베이스를 제어하기 위한 언어이다.

## SQL 기본 및 활용 - SQL 기본

### 1. DDL

#### 1-1. DDL

- 스키마, 도메인, 테이블, 뷰, 인덱스를 정의 / 변경 / 제거할 때 사용
- Auto Commit이 수행되면 ROLLBACK 있어도 데이터는 COMMIT 됨

#### 1-2. DDL - Create Table

- 테이블 생성하기

```sql
CREAT TABLE 테이블 명(
	컬럼1 컬럼type <constraint>,
    컬럼2 컬럼type <constraint>,
    컬럼3 컬럼type <constraint>
)
```

- select문을 활용해서 테이블 복사 생성하기
  - `oracle` - Create Table 테이블B AS Select * From 테이블A;
  - `SQL Server` - Select * Into 테이블B From 테이블A;

#### 1-3. 제약조건 (CONSTRAINT)

- 테이터의 **무결성**을 유지하기 위한 방법으로, 사용자가 원하는 조건의 데이터만 유지하는 방법
- Primary Key
  - 기본키
  - **한 테이블에 하나**만 지정 가능
  - 자동으로 UNIQUE한 인덱스 생성
  - NULL 값 입력 불가
- UNIQUE
  - 행을 고유하기 식별하기 위한 고유 키 (중복 안됨)
  - **NULL 값 입력 가능**
- NOT NULL
  - 명시적으로 NULL 입력 방지
- CHECK
  - 데이테 무결성을 유지하기 위해 테이블의 특정 컬럼에 설정하는 제약
- Foreign Key
  - 외래키
  - 참조 무결성 옵션 선택 가능
  - **여러개 가능**

#### 1-4. PK 제약조건 생성 DDL

1. CREATE문 안에 생성

   ```sql
   CREATE TABLE EMP(
   	EMP_NO VARCHAR(10) PRIMARY KEY,
       EMP_NM VARCHAR(300) NOT NULL
   );
   ```

   ```sql
   CREATE TABLE EMP(
   	EMP_NO VARCHAR(10) NOT NULL,
       EMP_NM VARCHAR(300) NOT NULL,
       CONSTRAINT EMP_PK PRIMARY KEY (EMP_NO)
   );
   ```

2. CREATE문 밖에 생성

   ```sql
   ALTER TABLE EMP ADD CONSTRAINT EMP_PK PRIMARY KEY (EMP_NO);
   ```

#### 1-5. NULL

- **알 수 없는 값** (0, 공백 아님)
- null은 `IS NULL`과 `IS NOT NULL`로만 비교 가능
- `SQL Server`에서 a = '' 입력하면 NULL아니고 공백값 입력됨 (IS NULL = False)

#### 1-6. 외래키(FK) 참고사항

- 테이블 생성 시 설정할 수 있음
- 외래키는 NULL값을 가질 수 있음
- 한 테이블에 여러 개 존재 가능
- 참조 무결성 제약을 받음
