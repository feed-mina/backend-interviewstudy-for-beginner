### MySQL
#### row - table - database
#### MySQL은 Oracle Corporation에서 만든 Relational Database Management System 관계형 데이터 베이스 관리 시스템(RDBMS)이다. 다른 관계형 시스템처럼 MySQL은 데이터베이스 액세스를 위해 structured query language(SQL)을 사용하여 테이블 형태로 데이터를 저장한다.
#### 즉 다른 관계형 데이터베이스처럼 MySQL은 Table에 데이터를 저장하며 SQL(Structrued query languate)을 이용하여 DB에 접근한다. MySQL 개발자는 애플리케이션에서 사용할 데이터베이스 스키마를 먼저 정의하여야 하며 테이블에 들어갈 필드들에 대한 규칙을 규정하여 사용한다.

#### MySQL 개발자가 애플리케이션에서 데이터에 접근할때 JOIN이라 불리는 작업을 통해 다수의 테이블을 병합한다. MySQL에서는 데이터베이스 스키마를 미리 정의하고 테이블에서 필드 사이의 관계를 제어하는 규칙을 설정한다.

### MongoDB
#### document - collection - database
#### MongoDB는 데이터를 데이터를 JSON-like documents로 저장하는 NoSQL데이터베이스이다. Document는 관계된 정보를 함께 저장하고 MongoDB query language(MQL)을 사용하여 접근한다.

#### Document 별로 필드는 다를 수 있으며 document가 자기 기술 slef-describing 하므로 시스탬에 Document의 구조를 따로 정의할 필요가 없다.
#### 선택적으로 각 컬랙션에 대해 스키마 유효성 검사를 사용하여 관리 제어를 할 수 있다
#### 다양한 규모의 조직에서 MongoDB를 특히 클라우드 데이터베이스로써 채택중이다.

### MySQL과 비교하여 MongoDB가 갖는 장점
#### MongoDB가 사용하는 document 객체 지향 프로그래밍에 언어와 자연스럽게 매핑되기에 개발이 단순화 된다. mongoDB를 사용하는것만으로도 객체를 관계형 테이블로 변환하는 복잡한 매핑 계층(ORM)이 사라진다.
#### MongoDB의 데이터구조는 유연하기에 새로운 비즈니스 요구사항에 대해 잘 반영해줄수 있다. 반면 MySQL은 관계형 구조를 변경시키는데 애플리케이션에 큰 오버해드를 가져온다.
