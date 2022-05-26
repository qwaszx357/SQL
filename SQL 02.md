# SQL 2

관계명 데이터베이스를 제어하기 위한 언어이다.

## 1. Database

### 1-1. 데이터베이스 생성

```sql
CREATE DATABASE <이름>
```

## 2. Table

### 2-1. Table 생성

```sql
CREATE TABLE <이름> (
  <열 이름1> <데이터 타입> <이 열의 제약>,
  <열 이름2> <데이터 타입> <이 열의 제약>,
  <열 이름3> <데이터 타입> <이 열의 제약>,
    ...
  <이 table의 제약1>, <이 table의 제약2>, ...
);
```

### 2-2. Data Type

1. INTEGER
   - 정수를 넣기 위한 데이터형으로 실수는 입력할 수 없다.
2. CHAR
   - 문자형을 넣기 위한 데이터형이다.
   - CHAR형 옆에는 고정 문자열이라는 데이터가 저장된다. 고정 문자열에서는 열에 넣는 문자열 길이가 최대 길이보다 작은 경우, 문자 수가 최대 길이가 될 때 까지 공백으로 채운다.
3. VACHAR
   - 가변 문자열 형식으로 문자 수가 최대 길이보다 작아도 공백으로 채우지 않는다.

### 2-3. Table 삭제

```sql
DROP TABLE <table 이름>;
```

### 2-4. Table 정의 변경

- 열 추가하기

```sql
ALTER TABLE <table 이름> ADD COLUMN <열 정의>;
```

- 열 삭제하기

```sql
ALTER TABLE <table 이름> DROP COLUMN <열 정의>;
```

