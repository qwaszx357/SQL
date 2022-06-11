# SQL 21

관계명 데이터베이스를 제어하기 위한 언어이다.

## SQL 기본 및 활용 - SQL 기본

### 1. 함수

#### 1-1. 단일행 함수

- 내장함수 중 파라미터가 하나 ~ 여러 개인 함수 (SUM, AVG, MAX, MIN 등은 다중행 함수)
- 각 행마다 하나의 결과를 반환
- Select, Where, ORDER BY, Update - Set 절에서 사용 가능

#### 1-2. 단일행 - 문자형 함수

<img src="http://1.bp.blogspot.com/-WAYL43tidd0/UQHpJ8W74dI/AAAAAAAAANs/AvRlWSYo3qE/s1600/%EC%9D%B4%EB%AF%B8%EC%A7%80+2.png" alt="img" style="zoom:100%;" />

#### 1-3. 단일행 - 숫자형 함수

![img](http://2.bp.blogspot.com/-3A23YmSRSC0/UQINimXvm9I/AAAAAAAAAOI/WvyIhvxIZYg/s1600/%EC%9D%B4%EB%AF%B8%EC%A7%80+4.png)

![img](http://3.bp.blogspot.com/-2G0Mr166q88/UQINixgNcPI/AAAAAAAAAOM/bKYSlGWG5vw/s1600/%EC%9D%B4%EB%AF%B8%EC%A7%80+5.png)

#### 1-4. 단일행 - 날짜형 함수

![img](http://2.bp.blogspot.com/-kRmY7NVSQLM/UQIOEjWNgcI/AAAAAAAAAOY/Hu362_S2U8s/s1600/%EC%9D%B4%EB%AF%B8%EC%A7%80+6.png)

#### 1-5. 날짜 연산

- 날짜를 숫자로 저장하기 때문에 숫자로 연산이 가능

![img](http://2.bp.blogspot.com/-H_qzulgs7OA/UQIOkQXl8aI/AAAAAAAAAOg/_d4OQO-hr0c/s1600/%EC%9D%B4%EB%AF%B8%EC%A7%80+7.png)

#### 1-6. 단일행 - 반환형 함수

- 명시적 데이터 유형 변환: 데이터 변환형 함수로 데이터 유형을 변환하도록 명시해 주는 경우
- 암시적 데이터 유형 변환: 데이터베이스가 자동으로 데이터 유형을 변환하여 계산하는 경우

#### 1-7. Case절

- 조건에 따른 결과를 반환 (IF - ELSE와 비슷)

```sql
Select 컬럼명, 
	CASE When 조건절 Then True일 때 반환 값
		ELSE False일 때 반환값
	END AS 컬럼명
FROM 테이블 명;
```

#### 1-8. NULL 관련 함수

- NVL(값1, 값2): 값1 is null -> 값2 // is not null -> 값1
- ISNULL(값1, 값2): 값1 is null -> 값2 // in not null -> 값1
- NVL2(값1, 값2, 값3): 값1 is null -> 값3 // is not null -> 값2
- NULLIF(값1, 값2): 같으면 null // 다르면 값1
- COALESCE(값1, 값2, 값3..): null 아닌 첫 번째 값

#### 1-9. 공집합

- 조건에 맞는 데이터가 한 건도 없는 경우
- SELECT 1 FROM DUAL WHERE 1 = 2; 와 같은 조건이 대표적인 공집합을 발생시키는 쿼리
- 인수값이 공집합인 경우, NVL() / ISNULL() 사용해도 공집합 출력