# SQL 7

관계명 데이터베이스를 제어하기 위한 언어이다.

## 관계

### 1. 관계 정의

- 엔터티의 인스턴스 사이 논리적 연관성
- 존재하는 형태나 행위로서 서로서로에게 연관성이 부여된 상태
- 관계명 / 차수(Cardinality) / 선택성(optionality) 로 구성됨

### 2. 페어링

- 엔터티 안에 인스턴스가 개별적으로 관계를 갖는 것
- 관계 = 페어링의 집합

### 3. 관계 분류

- ERD: 존재에 의한 관계 / 행위에 의한 관계 
  - 둘이 구분 없이 단일화된 표기법 사용
- UML: 연관 관계 / 의존 관계
  - 실선과 점선 표기법으로 구분

### 4. 관계 표기법

- 관계명 / 관계 차수(Cardinality) / 선택성(optionality) 세가지로 작성

<img src="https://dataonair.or.kr/publishing/img/knowledge/SQL_041.jpg" alt="관계 – DATA ON-AIR" style="zoom:80%;" />

### 5. 두 엔터티 사이에 정의한 관계를 체크하는 사항

- 두 엔터티 사이 **연관규칙**이 존재하는지?
- 두 엔터티 사이 **정보의 조합**이 발생하는지?
- 업무기술서, 장표에 관계 연결을 가능하게 하는 **동사**가 존재하는지?
- 업무기술서, 장표에 관계 연결에 대한 **규칙**이 존재하는지?