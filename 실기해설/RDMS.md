### 1-1. 관계형 데이터베이스 구조

관계형 데이터베이스(RDB)는 데이터를 2차원적인 표(테이블) 형태로 표현하며, 이 표는 행(Row)과 열(Column)로 구성됩니다. 이를 통해 데이터를 구조화하고, 서로 간의 관계를 명확히 정의할 수 있습니다. 관계형 데이터베이스의 주요 구성 요소와 구조는 다음과 같습니다:

#### 1. 테이블 (Table)
- **개념**: 테이블은 데이터가 저장되는 기본 단위로, 행(Row)과 열(Column)로 이루어집니다.
- **구성**:
  - **열(Column)**: 각 열은 특정 데이터 속성을 나타내며, 열의 집합을 통해 테이블의 스키마를 정의합니다. 예를 들어, `학생` 테이블에는 `학생ID`, `이름`, `학년` 등의 열이 있을 수 있습니다.
  - **행(Row)**: 각 행은 데이터의 개별 레코드를 나타내며, 행의 집합을 통해 실제 데이터를 저장합니다. 예를 들어, 한 학생의 모든 정보가 한 행에 저장됩니다.

#### 2. 속성 (Attribute)
- **개념**: 속성은 테이블의 열을 의미하며, 각 속성은 특정 유형의 데이터를 저장합니다. 예를 들어, `학생` 테이블의 `이름` 속성은 모든 학생의 이름을 저장합니다.

#### 3. 튜플 (Tuple)
- **개념**: 튜플은 테이블의 행을 의미하며, 각 튜플은 단일 데이터 레코드를 나타냅니다. 예를 들어, `학생` 테이블에서 한 학생의 정보를 하나의 튜플로 저장합니다.

#### 4. 기본 키 (Primary Key)
- **개념**: 기본 키는 테이블의 각 튜플을 고유하게 식별할 수 있는 하나 이상의 속성입니다. 기본 키는 중복될 수 없으며, NULL 값을 가질 수 없습니다.
- **예시**: `학생` 테이블의 `학생ID`는 각 학생을 고유하게 식별하는 기본 키가 될 수 있습니다.

#### 5. 외래 키 (Foreign Key)
- **개념**: 외래 키는 한 테이블의 속성이 다른 테이블의 기본 키를 참조하는 경우 사용됩니다. 이를 통해 테이블 간의 관계를 정의하고 유지합니다.
- **예시**: `수강` 테이블에서 `학생ID`는 `학생` 테이블의 `학생ID`를 참조하는 외래 키가 될 수 있습니다.

#### 6. 릴레이션 (Relation)
- **개념**: 릴레이션은 관계형 데이터베이스에서 테이블을 의미합니다. 각 릴레이션은 고유한 이름을 가지며, 특정 주제나 개체를 나타냅니다.
- **종류**:
  - **개체 릴레이션 (Entity Relation)**: 실제 객체(예: 학생, 강의)를 나타내는 테이블입니다.
  - **관계 릴레이션 (Relationship Relation)**: 개체 간의 관계(예: 학생과 강의의 수강 관계)를 나타내는 테이블입니다.

#### 7. 스키마 (Schema)
- **개념**: 스키마는 데이터베이스의 구조와 제약 조건을 정의하는 청사진입니다. 테이블, 열, 데이터 유형, 제약 조건 등을 포함합니다.
- **예시**: `학생` 테이블의 스키마는 `학생ID` (정수, 기본 키), `이름` (문자열), `학년` (정수) 등의 열을 포함할 수 있습니다.

### 관계형 데이터베이스의 장점 및 단점

#### 장점:
- **간결성**: 데이터를 2차원 표 형태로 간단하고 명확하게 표현할 수 있습니다.
- **편리성**: 표 형태로 데이터를 쉽게 이해하고 관리할 수 있습니다.
- **변환 용이성**: 다른 데이터베이스 시스템으로의 변환이 비교적 용이합니다.

#### 단점:
- **성능**: 대량의 데이터를 처리할 때 성능이 저하될 수 있습니다.
- **복잡성**: 복잡한 쿼리나 관계를 처리할 때 시스템의 복잡도가 증가할 수 있습니다.
