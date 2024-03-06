# 🔸 6-1 Database

## Database 란?

* 정의 \
  구조화된 정보 또는 데이터의 조직화된 모음으로, 일반적으로 데이터베이스 관리 시스템(DBMS)에 의해 제어된다. 연결된 애플리케이션과 함께 데이터와 DBMS를 하나로 묶어 데이터베이스 시스템이라고 하며, 단축하여 데이터베이스라고도 한다.\

* 역사\
  1\. 1960년대\
  항해용 DBMS - IMS(IBM)의 계층적 모델, CODASYL 접근방식(애플리케이션에 대규모 네트워크로 형성된 연결된 데이터 세트를 탐색하는 기능이며, 검색기능 부족.)\
  \
  2\. 1970년대\
  관계형 DBMS - 테이블 개념 도입, 필요한 데이터를 표현하는 선언적 쿼리 언어 사용\
  \
  3\. 1970년대 후반\
  SQL DBMS - 표준화된 쿼리 언어인 SQL 추가, 엔터티-관계 모델 등장\
  \
  4\. 1980년대\
  데스크탑 컴퓨팅 시대로, dBASE와 같은 데이터베이스 소프트웨어의 도입으로 사용자의 이해가 쉬워짐\
  \
  5\. 1990년대\
  객체지향 프로그래밍의 증가로, 데이터베이스의 데이터를 객체로 취급하기 시작했고, 객체지향언어를 제공하여 객체와 테이블간 변환의 불편함을 해결하려고 함.\
  \
  6\. 2000년대\
  NoSQL과 NewSQL - NoSQL은 속도가 빠르며, 조인작업을 피하고 수평확장이 가능해졌으며, NewSQL은 최신형 관계형 데이터베이스 클래스이다.\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://en.wikipedia.org/wiki/Database](https://en.wikipedia.org/wiki/Database)\
  [https://www.oracle.com/kr/database/what-is-database/](https://www.oracle.com/kr/database/what-is-database/)\


## DBMS

* 정의 \
  DBMS는 데이터베이스 관리 시스템으로, 사용자들이 [데이터베이스](https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4) 내의 데이터를 접근할 수 있도록 해주는 소프트웨어 도구의 집합이다.\

* 왜 필요한가?\
  데이터베이스와 최종 사용자 또는 프로그램 간의 인터페이스 역할을 하여 사용자가 정보의 구성 및 최적화 방법을 검색, 업데이트 및 관리할 수 있게 해준다. 또한 DBMS는 데이터베이스의 감독 및 제어가 용이하여 성능 모니터링, 튜닝, 백업, 복구 같은 다양한 관리 작업이 가능하다.\

* 종류\
  인기 데이터베이스 소프트웨어 또는 DBMS로는 MySQL, Microsoft Access, Microsoft SQL Server, FileMaker Pro, Oracle Database 및 dBASE가 있다.\

* 특징(장점)\
  1\. DBMS는 자료의 통합성을 증진시킨다.\
  2\. DBMS는 데이터의 접근성이 용이하다.\
  3\. 데이터 통제가 강화된다.\
  4\. 애플리케이션 프로그램들을 쉽게 개발하고 관리할 수 있다.\
  5\. 보안이 강화된다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://www.oracle.com/kr/database/what-is-database/](https://www.oracle.com/kr/database/what-is-database/)\
  [https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4\_%EA%B4%80%EB%A6%AC\_%EC%8B%9C%EC%8A%A4%ED%85%9C](https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4\_%EA%B4%80%EB%A6%AC\_%EC%8B%9C%EC%8A%A4%ED%85%9C)

## RDBMS

* 정의 \
  관계형 데이터베이스는 데이터가 하나 이상의 열과 행의 테이블(또는 '관계')에 저장되어 서로 다른 데이터 구조가 어떻게 관련되어 있는지 쉽게 파악하고 이해할 수 있도록 사전 정의된 관계로 데이터를 구성하는 정보 모음이다. \

* 왜 필요한가?\
  테이블을 조인하여 정보 간 관계 또는 링크를 설정할 수 있는 기능이 있어, 여러 데이터 포인트 간의 관계를 쉽게 이해하고 정보를 얻을 수 있다.\

* 장점\
  1\. 유연성\
  전체 데이터베이스 구조를 변경하거나 기존 애플리케이션에 영향을 주지 않고 필요할 때마다 간편하게 테이블, 관계를 추가 또는 삭제하고 데이터를 변경할 수 있다.\
  \
  2\. ACID 규정준수\
  관계형 데이터베이스는 ACID(원자성, 일관성, 격리, 내구성) 성능을 지원하므로 오류, 실패, 기타 잠재적 오작동에 관계없이 데이터 유효성을 검사할 수 있다.\
  \
  3\. 공동작업\
  여러 사용자가 동시에 데이터를 운영하고 액세스할 수 있다. 기본 제공되는 잠금 기능으로 업데이트 도중 데이터에 동시 액세스할 수 없다.\
  \
  4\. 사용편의성\
  기술자가 아닌 사용자도 데이터베이스와 상호작용하는 방법을 배울 수 있는 SQL을 사용하여 복잡한 쿼리를 쉽게 실행할 수 있다.\
  \
  5\. 내장된 보안기능\
  역할 기반 보안을 통해 데이터 액세스가 특정 사용자로 제한된다.\
  \
  6\. 데이터베이스 정규화\
  관계형 데이터베이스는 데이터 중복성을 줄이고 데이터 무결성을 개선하는 정규화라는 설계 기법을 사용한다.\

* 특징\

* 종류\
  MySQL, MariaDB, PostgreSQL, MS SQL Server, Oracle 등이 모두 여기에 속한다.\

* 레퍼런스 모음\
  [https://cloud.google.com/learn/what-is-a-relational-database?hl=ko](https://cloud.google.com/learn/what-is-a-relational-database?hl=ko)

## 데이터베이스 언어

### DDL**(Data Definition Language)**

* 정의 \
  DDL은 데이터베이스를 정의하는 언어이며, 테이블을 생성, 수정, 삭제하는 등의 데이터의 전체의 골격을 결정하는 역할을 하는 언어이다.\

*   명령어 종류\
    1\. create : 데이터베이스, 테이블등을 생성\
    2\. alter : 테이블을 수정\
    3\. drop : 데이터베이스, 테이블을 삭제\
    4\. truncate : 테이블을 초기화


* 레퍼런스 모음\
  [https://velog.io/@ksk5401/DDL-DML-DCL-%EC%9D%B4%EB%9E%80](https://velog.io/@ksk5401/DDL-DML-DCL-%EC%9D%B4%EB%9E%80)

### DML**(Data Manipulation Language)**

* 정의 \
  DML은 정의된 데이터베이스에 입력된 레코드를 조작하는 언어이며, 데이터를 조회하거나 수정하거나 삭제하는 등의 역할을 하는 언어.\

* 명령어 종류\
  1\. select : 데이터 조회\
  2\. insert : 데이터 삽입\
  3\. update : 데이터 수정\
  4\. delete : 데이터 삭제\

* 레퍼런스 모음\
  [https://velog.io/@ksk5401/DDL-DML-DCL-%EC%9D%B4%EB%9E%80](https://velog.io/@ksk5401/DDL-DML-DCL-%EC%9D%B4%EB%9E%80)

### DCL**(Data Control Language)**

* 정의 \
  DCL은 데이터베이스에 접근하거나 객체에 권한을 주는 등의 역할을 하는 언어,\

* 명령어 종류\
  1\. grant : 특정 데이터베이스 사용자에게 특정 작업에 대한 수행 권한을 부여\
  2\. revoke : 특정 데이터베이스 사용자에게 특정 작업에 대한 수행 권한을 **박탈, 회수**\
  **3.** commit : 트랜잭션의 작업을 저장\
  4\. rollback : 트랜잭션의 작업을 **취소, 원래대로 복구**\

* 레퍼런스 모음\
  [https://velog.io/@ksk5401/DDL-DML-DCL-%EC%9D%B4%EB%9E%80](https://velog.io/@ksk5401/DDL-DML-DCL-%EC%9D%B4%EB%9E%80)

## SQL

* 정의 \
  SQL은 데이터를 쿼리, 조작 및 정의하고 액세스 제어를 제공하기 위해 거의 모든 [관계형 데이터베이스](https://www.oracle.com/kr/database/what-is-database/#relational)에서 사용되는 프로그래밍 언어이다.\

* 역사\
  SQL은 1970년대에 관계형 데이터 모델을 기반으로 발명되었습니다. 처음에는 구조적 영어 쿼리 언어(SEQUEL)라고 했다가, 나중에 SQL로 줄였습니다. Oracle(구 Relational Software)은 상용 SQL 관계형 데이터베이스 관리 시스템을 제공하는 최초의 공급업체가 되었습니다.\

* 중요한 이유\
  구조적 쿼리 언어(SQL)는 모든 유형의 애플리케이션에서 자주 널리 사용되는 쿼리 언어이다. 데이터 분석가와 개발자는 SQL이 서로 다른 프로그래밍 언어와 잘 통합되므로 SQL을 배우고 사용한다. 예를 들어, Java 프로그래밍 언어로 SQL 쿼리를 포함시켜 Oracle 또는 MS SQL Server와 같은 주요 SQL 데이터베이스 시스템으로 고성능 데이터 처리 애플리케이션을 빌드할 수 있다. SQL은 문에 일반적인 영어 키워드를 사용하기 때문에 배우기가 매우 쉽다.\

* SQL 시스템의 구성요소\
  1\. SQL 테이블  - 행과 열로 구성.\
  2\. SQL 문 - SQL문 또는 쿼리는 관계형 데이터베이스 관리 시스템에서 유효한 명령어이다.\
  3\. 저장 프로시져 - 관계형 데이터베이스에 저장된 하나 이상의 SQL 문 모음. 저장 프로시저를 사용하여 효율성과 성능을 개선한다. 예를 들어, 서로 다른 애플리케이션에서 동일한 SQL 문을 작성하는 대신 판매 테이블을 업데이트하기 위한 저장 프로시저를 만들 수 있다.\

* SQL 작동방식\
  1\. 구문분석기 - SQL 문의 정확성과 데이터를 조작하는데 필요한 권한이 있는지 검증한다.\
  2\. 관계형 엔진 - 가장 효과적인 방법(바이트 코드 사용)으로 해당 데이터를 검색, 쓰기, 업데이트하기 위한 계획을 만든다.\
  3\. 스토리지 엔진 - 바이트 코드를 처리하고 의도한 SQL 문을 실행하는 소프트웨어 구성 요소이다.\

* 레퍼런스 모음\
  [https://www.oracle.com/kr/database/what-is-database/#link2](https://www.oracle.com/kr/database/what-is-database/#link2)\
  [https://aws.amazon.com/ko/what-is/sql/](https://aws.amazon.com/ko/what-is/sql/)

## 관계형 데이터 모델

* 정의 \
  관계형 데이터 모델이란 2차원 구조의 테이블 형식을 이용하여 데이터를 정의한 모델를 의미한다. 테이블은 릴레이션이라고도 부른다.  \

* 레퍼런스 모음\
  [https://lordofkangs.tistory.com/64](https://lordofkangs.tistory.com/64)

