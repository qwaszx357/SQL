# SQL 16

관계명 데이터베이스를 제어하기 위한 언어이다.

## SQL 기본 및 활용 - SQL 기본

### 1. DDL

#### 1-1. Alter Table (oracle)

-  컬럼 추가:  Alter Table 테이블 명 ADD (추가 컬럼명 Dtype);
- 컬럼 삭제:  Alter Table 테이블 명 DROP COLUMN 삭제 컬럼명;
- 컬럼 속성 변경: Alter Table 테이블 명 MODIFY (컬럼명 Dtype);

#### 1-2. Alter Table + ADD COLUMN 

- 기존 테이블에 새로운 컬럼을 추가

```sql
ALTER TABLE 테이블 명
ADD (컬럼명1 컬럼 유형 제약조건,
	컬럼명2 컬럼 유형 제약조건,
	컬럼명3 컬럼 유형 제약조건
);
```

#### 1-3. Alter Table + DROP COLUMN 

- 컬럼 삭제
- 한 번 삭제된 컬럼은 다시 복구할 수 없음

```sql
ALTER TABLE 테이블 명
DROP COLUMN (삭제할 컬럼명1, 삭제할 컬럼명2,...);
```

#### 1-4. Alter Table + MODIFY

- 이미 존재하는 컬럼의 속성 변경

```sql
ALTER TABLE 테이블 명 MODIFY (컬럼명 DType);
```

#### 1-5. Alter Table + RENAME COLUMN A TO B

- 이미 존재하는 컬럼명 변경

```sql
ALTER TABLE 테이블 명 RENAME COLUMN 기존 컬럼명 TO 새로운 컬럼명;
```

