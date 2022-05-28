# SQL 6

관계명 데이터베이스를 제어하기 위한 언어이다.

## 속성

### 1. 속성

- 인스턴스로 관리하고자 하는 의미상 더 이상 분리되지 않는 최소한의 단위
- 엔터티를 설명하고, 인스턴스의 구성 요소가 됨

### 2. 엔터티 - 속성 - 인스턴스 관계

- 1개의 엔터티 = 2개 이상의 인스턴스 집합 (엔터티가 가장 큰 개념)
- 1개의 인스턴스 = 2개 이상의 속성을 가짐
- 1개의 속성 = 1개의 속성 값을 가짐

<img src="https://jistol.github.io/assets/img/database/database-entity-attribute-relationship/2.jpg" alt="entity(엔터티), attribute(속성), relationship(관계) 요약 - 암기용 · Jistol Github Page" style="zoom: 80%;" />

<img src="https://mblogthumb-phinf.pstatic.net/MjAyMDA4MjRfMjM2/MDAxNTk4MjM2NTIwMTk2.nbsikImSDThBE_CaXtZDLaonuvEEVUAjXO88uyY6L1cg.0MlxUl8nbqSx82HmxOh6TnkPE7gUvnF23i-cT8ns1p0g.PNG.clsrnclsrn95/image.png?type=w800" alt="img" style="zoom:80%;" />

> 엔터티 > 인스턴스 > 속성 > 속성값

### 3. 속성 분류

1. 속성의 특성에 따른 분류
   - 기본 속성: 기본적인 모든 속성
   - 설계 속성: 사용자에 의해 새로 만들어지거나 정의되는 속성
   - 파생 속성: 다른 속성의 영향을 받아 발생
2. 엔터티 구성방식에 따른 분류
   - PK: 엔터티 식별
   - FK: 다른 엔터티와 관계에서 포함된 속성
   - 일반: 엔터티에 포함되어 있으며, PK, FK가 아닌 속성

### 4. 도메인 

- 각 속성이 가질 수 있는 범위
- 테이터 타입, 크기, 제약사항(NOT NULL, CHECK 조건)을 지정

> 제약사항에서 테이블의 속성간 FK 제약조건 지정은 없음

### 5. 속성 명명

- 약어 사용 안함
- 서술식의 속성명 사용 안함
- 현업에서 실제 사용하는 용어 사용
- 유일한 이름 부여