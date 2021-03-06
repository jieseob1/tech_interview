## SQL과 NOSQL 차이

MYSQL과 같은 SQL을 사용할지, 아니면 MONGODB와 같은 NOSQL을 사용할지

### SQL(관계형 DB)

SQL을 ㅅ용하면 RDBMS에서 데이터를 저장, 수정 ,삭제 및 검색 할 수 있다.
관계형 데이터베이스는 핵심적인 두가지 특징이 있다.

- 데이터는 정해진 데이터 `스키마에 따라 테이블 저장`
- 데이터는 `관계를 통해 여러 테이블에 분산`된다.

따라서 스키마를 준수하지 않은 레코드는 테이블에 추가할 수 없다. 즉, 스키마를 수정하지 않는 이상은 정해진 구조에 맞는 레코드만 추가가 가능한 것이 관계형 데이터베이스의 특징 중 하나다.

하나의 테이블, 중복 없이 하나의 데이터만을 관리하므로, 다른 테이블에서 부정확한 데이터를 다룰 위험이 없어지는 장점이 있다.

### NOSQL (비관계형 DB)

스키마,관계가 없다.
NOSQL에서는 레코드를 문서라고 한다.
SQL은 정해진 스키마를 따르지 않으면 데이터 추가가 불가능 했으나, NOSQL에서는 다른 구조의 데이터를 같은 컬렉션에 추가가 가능하다.
관계형 데이터베이스처럼 여러 테이블에 나누어 담는 것이 아닌, 관련 데이터를 동일한 '컬렉션'에 넣는다.

### SQL 장점

- 명확하게 정의된 스키마, 데이터 무결성 보장
- 관계는 각 데이터를 중복없이 한번만 저장

### SQL 단점

- 덜 유연함. 데이터 스키마를 사전에 계획하고 알려야 함. (나중에 수정하기 힘듬)
- 관계를 맺고 있어서 조인문이 많은 복잡한 쿼리가 만들어질 수 있음
- 대체로 수직적 확장만 가능함

### NoSQL 장점

- 스키마가 없어서 유연함. 언제든지 저장된 데이터를 조정하고 새로운 필드 추가 가능
- 데이터는 애플리케이션이 필요로 하는 형식으로 저장됨. 데이터 읽어오는 속도 빨라짐
- 수직 및 수평 확장이 가능해서 애플리케이션이 발생시키는 모든 읽기/쓰기 요청 처리 가능

### NoSQL 단점

- 유연성으로 인해 데이터 구조 결정을 미루게 될 수 있음
- 데이터 중복을 계속 업데이트 해야 함
- 데이터가 여러 컬렉션에 중복되어 있기 때문에 수정 시 모든 컬렉션에서 수행해야 함 (SQL에서는 중복 데이터가 없으므로 한번만 수행이 가능)

SQL 데이터베이스 사용이 더 좋을 때
관계를 맺고 있는 데이터가 자주 변경되는 애플리케이션의 경우

NoSQL에서는 여러 컬렉션을 모두 수정해야 하기 때문에 비효율적

변경될 여지가 없고, 명확한 스키마가 사용자와 데이터에게 중요한 경우

NoSQL 데이터베이스 사용이 더 좋을 때
정확한 데이터 구조를 알 수 없거나 변경/확장 될 수 있는 경우
읽기를 자주 하지만, 데이터 변경은 자주 없는 경우
데이터베이스를 수평으로 확장해야 하는 경우 (막대한 양의 데이터를 다뤄야 하는 경우)
