# SQL 1

관계명 데이터베이스를 제어하기 위한 언어이다.

## SQL 명령문 개괄

### 1. 연산 순서

- from - where - group by - having - select - order by

### 2. SQL문 종류

SQL문은 RDBMS에 부여한 명령 종류에 따라 3가지로 나뉜다.

#### 2-1. DDL (Data Definition Language)

DDL(데이터 정의 언어)는 데이터를 저장하는 DB 및 테이블을 생성, 삭제, 변경하기 위한 것이다.

- `CREATE`: DB or Table 등을 작성한다.
- `DROP`: DB or Table 등을 삭제한다.
- `ALTER`: DB or Table 등의 구성을 변경한다.
- `RENAME`: DB or Table 등의 이름을 수정한다.

 #### 2-2. DML (Data Manipulation Language)

DML(데이터 조작 언어)는 Table의 행을 검색하거나 변경하기 위한 것이다.

- `SELECT`: Table 행을 검색한다.
- `INSERT`: Table에 신규 행을 등록한다.
- `DELETE`: Table에서 행을 삭제한다.
- `UPDATE`: Table에서 행을 수정한다.

#### 2-3. DCL (Data Control Language)

DCL(데이터 제어 언어)는 DB에서 처리한 변경 내용을 확정하거나 취소하기 위한 것이다. 또한 RDBMS 사용자에게 처리 권한을 부여하기도 한다.

- `REVOKE`: 사용자에게 처리 권한을 제거한다.
- `GRANT`: 사용자에게 처리 권한을 부여한다.

#### 2-4. TCL (Transaction Control Language)

- `COMMIT`: DB 변경 내용을 확정한다.
- `ROLLBACK`: DB 변경 내용을 취소한다.

