# SQL 17

관계명 데이터베이스를 제어하기 위한 언어이다.

## SQL 기본 및 활용 - SQL 기본

### 1. DDL

#### 1-1. Drop Table

- 사용하지 않는 테이블 제거
- 구조 및 행까지 영구적으로 삭제

```sql
DROP TAbLE 테이블 명;
```

#### 1-2. Drop Table + CASCADE 

- 테이블을 삭제하되, 참조 제약에 걸린 행까지 연쇄적으로 제거
- Drop Table 시 자식 테이블에 참조 제약이 걸려있는 경우 삭제 시 에러가 뜰 수 있음
- `SQL Server`에는 CASCADE 옵션이 없음

```sql
DROP TABLE 테이블 명 CASCADE CONSTRAINT;
```

#### 1-3. Truncate Table

- 테이블의 모든 행 제거
- 테이블 삭제가 아닌, 해당 테이블의 모든 행만 제거 후 저장공간을 재사용하도록 해제해줌

```sql
TRUNCATE TABLE 테이블 명;
```

#### 1-4. DDL과 DML 삭제의 차이점

- DDL
  - 반드시 AUTO COMMIT 이 일어남
  - DROP, TRUNCATE
- DML 
  - 사용자가 COMMIT 해야함
  - DALETE - ROLLBACK로 복구 가능

#### 1-5. DDL 참고사항

- DROP COLUMN: 데이터 유무 관계없이 모두 삭제 가능. 한번에 하나의 컬럼만 삭제
- DROP CONSTRAINT: 테이블 생성 시 부여했던 제약조건을 삭제하는 명령어
- ADD CONSTRAINT: 테이블 생성 이후에 필요에 의해서 제약조건을 추가

### 2. 참조동작

#### 2-1. Insert Action

- Automatic: 자식 삽입 시 부모에 PK가 없으면, 부모에 PK 생성 후, 자식에 삽입
- Set Null: 자식 삽입 시 부모에 PK가 없으면, 자식 외부키를 Null 값으로 셋팅
- Set Default: 자식 삽입 시 부모에 PK가 없으면, 자식 외부키를 지정된 Default 값으로 셋팅
- Dependent: 자식 삽입 시 부모에 PK가 존재할 때만 자식 삽입 허용
- No Action: 참조 무결성을 위반하는 삽입 액션은 취하지 않음

#### 2-2. Delete / Modify Action

- Cascade: 부모 삭제 시 자식도 같이 삭제
- Set Null: 부모 삭제 시 자식의 해당 필드는 Null로 셋팅
- Set Default: 부모 삭제 시 자식의 해당 필드를 Default 값으로 셋팅
- Restrict: 부모 삭제 시 자식 테이블에 PK가 없는 경우에만 부모 삭제 허용
- No Action: 참조 무결성을 위반하는 삭제, 수정 액션은 취하지 않음