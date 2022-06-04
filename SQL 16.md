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

#### 1-6. RENAME A TO B

- 기존에 존재하는 테이블의 이름 변경

- `oracle`

  - ```sql
    RENAME 기존 테이블 명 TO 새로운 테이블 명 
    ```

- `SQL Server`

  - ```sql
    SP_NAME 기존 테이블 명, 새로운 테이블 명 
    ```

#### 1-7. Alter Table + ADD CONSTAINT

- 기존 테이블에 제약조건 추가
- CONSTAINT는 수정하는 개념이 없으므로 수정을 원한다면 기존 CONSTAINT를 삭제하고 다시 만들어야 함

```sql
ALTER TABLE 테이블 명 ADD CONSTAINT PK명 PRIMARY KEY (컬럼명)
```

#### 1-8. Alter Table +DROP CONSTAINT

- 테이블에 존재하는 제약조건을 삭제하는 경우

```sql
ALTER TABLE 테이블 명 DROP CONSTAINT PK명 PRIMARY KEY (컬럼명)
```

#### 1-9. ALTER TABLE 컴럼 변경 시 주의사항

- 컬럼의 길이 (크기)를 늘리는 것은 자유롭지만, 값이 존재할 경우 크기 줄이는 것은 불가능
  - NULL 값만 가지고 있거나 아무 행도 존재하지 않으면 컬럼 길이 줄이기 가능
- 해당 컬럼이 NULL 값만 가지고 있으면 타입 (숫자, 문자) 변경 가능
- NULL이 없는 경우에만 NOT NULL 제약조건 추가 가능
  - 이미 NULL 값이 존재하는 경우 NOT NULL 제약 조건 추가 불가능
- DEFAULT 값을 설정하는 경우, 변경 작업 이후 발생하는 행 삽입에 대해서만 DEFAULT 값이 영향
