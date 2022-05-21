# SQL 4

관계명 데이터베이스를 제어하기 위한 언어이다.

## 데이터 모델링의 이해

### 1. 정보시스템 구축에서 모델링 활용

- 계획 / 분석 / 설계 할 때 업무를 분석하고 설계하는데 이용
- 구축 / 운영 단계에서는 변경과 관리의 목적으로 이용

### 2. 모델링의 특징

- 추상화: 일정한 형식에 맞추어 표현
- 단순화: 제한된 표기법, 언어로 표현해서 이해하기 쉽도록 도움
- 명확화(정확화): 누구나 쉽게 이해할 수 있도록 정확하게 현상을 기술

### 3. 모델링의 3가지 관점

- 데이터 관점 (Data, What): 업무와 데이터, 데이터와 데이터 간의 관계
- 프로세스 관점 (Process, How): 업무 프로세스가 실제 하는 일 또는 무엇을 해야하지
- 상관 관점 (Interaction): 업무가 처리하는 일의 방법에 따른 데이터가 받는 영향

### 4. 데이터 모델링 기능

- 시스템 가시화, 시스템 구조, 행동 명세화, 시스템 구축의 구조화 틀 제공
- 시스템 구축 과정을 문서화, 세부사항은 숨기는 다양한 관점 제공
- 상세한 수준의 표현방법도 제공

### 5. 데이터 모델링이 필요한 이유

- 업무 정보를 일정한 표기법으로 표현
- 분석된 모델로 DB 생성 및 개발
- 업무 흐름을 설명

### 6. 데이터 모델링의 중요성

- 간결: 파급효과가 큼 (일련의 변경 시 다른 것도 변경)
- 정확: 복잡한 것을 간결하게 표현 (명확하고 간결하게 함)
- 신뢰: 데이터 품질을 유지 (오래된 데이터의 정확성과 신뢰성)

### 7. 데이터 모델링의 유의점

- 중복: 데이터베이스가 여러 장소에 같은 정보로 저장되는 것을 주의
- 비유연성: 데이터 정의를 데이터 프로세스와 분리해서 유연하게
- 비일관성: 데이터간 상호 연관관계를 일관되고 명확히 정의

### 8. 데이터 모델링 3단계

- 개념적: 추상화 수준이 높고, 업무중심적, 전체에 대해 초관적인 수준의 모델링
- 논리적: 키, 속성, 관계를 표현, 재사용성이 높음, 정규화를 수행
- 물리적: 실제 DB에 이식, 물리적 성격, 개념적보다 구체적

### 9. 프로젝트 생명주기

- 폭포수 생명주기: 데이터 모델링이 명확히 구분됨.  (분석 -> 개념, 논리 // 설계 -> 물리)
- 정보공학 / 구조적 방법론: (분석 -> 논리) // (설계 -> 물리)
- 나선형 생명주기:업무 크기에 따라 논리, 물리적 설계가 분석, 설계 양쪽에서 수행

### 10. 독립성 필요성

- 유지보수 비용 절감
- 중복된 데이터 줄이기
- 데이터 복잡도 낮추기
- 요구사항 대응을 높임

### 11. 데이터베이스 3단계 구조

- 외부 단계
- 개념적 단계
- 내부적 단계

### 12. 데이터 독립성 요소

- 외부 스키마
- 개념 스키마
- 내부 스키마

### 13. 두 영역의 데이터 독립성

- 논리적 독립성 (외부 <-> 개념)
- 물리적 독립성 (개념 <-> 내부)

---

- 외부단계 - 외부 스키마 (사용자와 가까운 단계)
- 개념적 단계 - 개념 스키마 (DB에 저장되는 데이터와 사용자 관계 표현. 모든 사용자 관점을 통합, 조직 전체 통합)
- 내부단계 - 내부 스키마

### 14. Mapping (사상)

- 매핑: 상호 독립적인 두 개념을 연결시키는 다리
- 외부적 / 개념적 사상 + 개념적 / 물리적 사상

### 15. 데이터 모델링의 주요 세가지 개념

- Things: 업무가 관여하는 **어떤 것**
- Attributes: 어떤 것이 가지는 **성격**
- Relarionships: 업무가 관여하는 어떤 것 간의 **관계**

| 개념                              | 복수 / 집합개념 & 타입 / 클래스 | 개별 / 단수개념 & 어커런스 / 인스턴트       |
| --------------------------------- | ------------------------------- | ------------------------------------------- |
| Things (어떤 것)                  | Entity Type (엔터티 타입)       | Entity (엔터티)                             |
|                                   | Entity (엔터티)                 | Instance (인스턴스) / Occurrence (어커런스) |
| Attributes (어떤 것의 성격)       | Attribute (속성)                | Attribute Value (속성값)                    |
| Relarionships (어떤 것 간의 연관) | Relarionship (관계)             | Pairing (페어링)                            |

### 16. 데이터 모델 표기법 ERD 이해

- ERD 표기법 
  - 엔터티 = 사각형
  - 관계 = 마름모
  - 속성 = 타원형
- ERD로 모델링 하는 방법
  1. 엔터티 그리기
  2. 엔터티 배치
  3. 엔터티 간 관계 설정
  4. 관계의 참여도 설정
  5. 관계의 필수 여부 설정

### 17. 좋은 데이터 모델의 요소

- 완전성
- 중복 배제
- 업무규칙
- 데이터 재사용
- 의사소통
- 통합성