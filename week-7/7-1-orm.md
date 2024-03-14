# 🔸 7-1 ORM

## ORM(Object-Relational Mapping)

* 정의 \
  객체와 데이터베이스의 관계를 매핑해주는 도구를 말한다. 프로그래밍 언어의 객체와 관계형 데이터베이스의 데이터를 자동으로 매핑(연결)해주는 도구이며, 프로그래밍 언어의 객체와 관계형 데이터베이스 사이의 중계자(통역자) 역할을 한다.\

* 왜 사용하는가?\
  객체지향 프로그래밍과 관계형 데이터베이스를 사용하는데 객체와 관계형 데이터 사이의 불일치가 존재한다. 이때, ORM을 이용해서 데이터베이스 접근을 프로그래밍 언어의 관점으로 맞출 수 있다.\
  또한, SQL을 자동으로 생성하여 불일치를 해결한다.  SQL문을 직접 작성하지 않고 엔티티를 객체로 표현할 수 있고, 객체를 통해 간접적으로 데이터베이스를 다루어 데이터베이스와 프로그래밍 언어 사이의  간극을 줄여준다. 이를 통해 느슨하게 연결된, 테스트에 용이한 애플리케이션을 만들 수 있다.\

* 장점\
  1\. 직관적인 코드 (가독성) + 비지니스 로직 집중 가능 (생산성)\
  ORM을 이용하면 SQL Query 가 아닌 메서드로 데이터를 조작할 수 있고, 이로써 프로그래머가 객체 모델로 프로그래밍하는 것에 더 집중할 수 있게 도와준다.\
  \
  2\. 재사용 및 유지보수 편리성 증가\
  ORM은 독립적으로 작성되었고 해당 객체들을 재활용 할수 있기 때문에, 디자인 패턴을 견고하게 만드는 데 유리하다.\
  \
  3\. DBMS에 대한 종속성 저하\
  객체 간 관계를 바탕으로 SQL을 자동으로 생성하기 때문에 RDBMS의 데이터 구조와 프로그래밍 언어의 객체 모델 사이의 간격을 좁힌다. 프로그래머는 Object에 집중하므로 DBMS를 다루는 큰 작업에도 비교적 적은 리스크와 시간만 소요할 수 있다.\

*   단점\
    ORM 으로만 서비스를 구현하기 어려움이 있다. 추후 변경이 어려우므로 설계는 신중하게 해야한다. 또한 프로젝트의 복잡성이 커질 경우 난이도 또한 올라간다.


* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://velog.io/@eunhye\_/DB-ORM](https://velog.io/@eunhye\_/DB-ORM)

## JPA(Jakarta Persistence API)

* 정의 \
  JPA는 자바에서 사용하는 ORM 기술 표준이다. JPA는 자바 애플리케이션과 JDBC 사이에서 동작하며, 자바 인터페이스로 정의되어 있다.
* 왜 사용하는가?\
  기존의 개발 방식은 SQL 중심적인 개발이었지만, JPA를 통해 객체 중심 애플리케이션 개발이 가능해졌다.\
  \
  **1. 생산성(CRUD)**\
  JPA를 사용하면 기본적으로 생산성이 높아진다. JDBC 방식의 경우 SQL 쿼리문을 직접 작성해야 데이터베이스에 접근할 수 있다. 하지만, JPA는 쿼리문을 별도로 작성할 필요가 없다. 다음과 같이 간단한 메서드를 통해 CRUD가 가능하다.\
  \
  저장 : jpa.persist(member)\
  조회 : Member member = jpa.find(memberId)\
  수정 : member.setName(”변경할 이름”)\
  삭제 : jpa.remove(member)\
  \
  **2. 유지보수**\
  기존에는 엔티티 클래스의 필드가 변경되면 모든 SQL을 수정해야 했다.\
  JPA에서는 쿼리를 직접 작성하지 않기 때문에 필드가 변경되더라도 매핑 정보만 잘 연결하면 SQL문은 자동으로 작성된다.\
  \
  **3. 패러다임의 불일치 문제 해결**\
  상속, 연관관계, 객체 그래프 탐색, 비교 등의 설계 차이로 인해 발생하는 패러다임 불일치 문제를 해결한다. \
  \
  1\) 객체는 상속 구조를 만들 수 있으며, 다형성 구현이 가능하지만, 관계형 데이터베이스의 테이블은 상속이라는 개념이 존재하지 않는다.\
  2\) 객체는 참조를 통해 관계를 표현하며 방향을 가지고 있으나, 관계형 데이터베이스는 외래 키를 통해 관계를 표현하며, 방향이 존재하지 않는다. 또한, 다대다 관계 문제를 해결하기 위해 조인을 사용한다.\
  3\) 이 외에도 다양한 패러다임 불일치 문제가 존재.\
  \
  이와 같이 객체와 데이터베이스는 서로 다른 목적을 가지고 설계되었기 때문에 매핑하는 데 있어 여러 문제가 발생한다. 하지만 JPA를 사용하면 이러한 문제를 모두 해결할 수 있다.\

* 동작 / 특징\
  JPA는 애플리케이션과 JDBC 사이에서 동작하며, DBC API를 사용하여 데이터베이스와 데이터를 주고받게 된다.\
  \
  1\. 저장\
  1\) MemberDao 클래스를 통해 persist()를 실행하면, JPA가 Entity 객체를 분석하여 SQL문을 생성한다.\
  2\) JDBC API를 사용하여 DB에 생성된 INSERT SQL을 보내게 된다.\
  3\) 이 과정에서 JPA는 객체와 데이터베이스 테이블의 패러다임 불일치를 해결한다.\
  \
  2\. 조회\
  1\) MemberDao 클래스를 통해 find(id)를 실행하면, JPA는SELECT SQL을 생성한다.\
  2\) JDBC API를 사용하여 생성된 SELECT SQL을 보낸다.\
  3\)  DB에서 반환된 정보를 ResultSet 매핑을 통해 객체로 변환해 준다.\
  4\) 이 과정에서 패러다임 불일치 문제를 해결해 준다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://ittrue.tistory.com/253](https://ittrue.tistory.com/253)

## Jakarta EE

* 정의 \
  자카르타 EE은 [자바](https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94\_\(%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D\_%EC%96%B8%EC%96%B4\))를 이용한 서버측 개발을 위한 플랫폼이다. 자카르타 EE 플랫폼은 PC에서 동작하는 표준 플랫폼인 [Java SE](https://ko.wikipedia.org/wiki/Java\_SE)를 확장하여, [웹 애플리케이션 서버](https://ko.wikipedia.org/wiki/%EC%9B%B9\_%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98\_%EC%84%9C%EB%B2%84)에서 동작하는 장애복구 및 분산 멀티티어를 제공하는 자바 소프트웨어의 기능을 추가한 서버를 위한 플랫폼이다. \

* 특징\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://ko.wikipedia.org/wiki/%EC%9E%90%EC%B9%B4%EB%A5%B4%ED%83%80\_EE](https://ko.wikipedia.org/wiki/%EC%9E%90%EC%B9%B4%EB%A5%B4%ED%83%80\_EE)

## Entity

* 정의 \
  엔터티는 컨테이너 관리 지속성을 사용하여 자동으로 관계형 데이터베이스에 저장된 영구 데이터를 나타냅니다. 엔터티는 경량 지속성 도메인 개체입니다. 일반적으로 엔터티는 관계형 데이터베이스의 테이블을 나타내며 각 엔터티 인스턴스는 해당 테이블의 행에 해당합니다.\

* 특징\
  1\. 엔터티는 해당 데이터가 데이터베이스와 같은 일부 형태의 데이터 저장 시스템에 지속적으로 저장되므로 지속성입니다. 서버 오류, 장애 조치 또는 네트워크에서도 살아남습니다. 실패. 엔터티가 다시 인스턴스화되면 이전 인스턴스의 상태가 자동으로 복원됩니다.\
  \
  2\. 엔터티는 단일 비즈니스 프로세스 내에서 비즈니스 엔터티 또는 여러 작업을 모델링합니다. 엔터티는 데이터 및 해당 데이터에 대한 계산과 관련된 비즈니스 서비스를 촉진하는 데 사용되는 경우가 많습니다. 예를 들어 구매 주문서 내의 항목을 검색하고 계산을 수행하는 엔터티를 구현할 수 있습니다. 엔터티는 작업을 수행하면서 여러 개의 종속적 영구 개체를 관리할 수 있습니다.\
  \
  3\. 엔터티는 원격으로 액세스할 수 있는 구성 요소가 아니기 때문에 세분화된 영구 객체를 나타낼 수 있습니다.\
  \
  4\. 엔터티는 객체를 함께 집계하고 JPA 지속성 공급자의 트랜잭션, 보안 및 동시성 서비스를 사용하여 데이터 및 관련 객체를 효과적으로 유지할 수 있습니다.
* JPA 엔터티 컨테이너 관리 영구 필드란?\

* JPA 엔터티 컨테이너 관리 관계 필드란 무엇입니까?\

*   [JPA 엔터티 기본 키란 무엇입니까?](https://docs.oracle.com/cd/E16439\_01/doc.1013/e13981/undejbs003.htm#BABJHAFE)

    \
    \

* 레퍼런스 모음\
  [https://docs.oracle.com/cd/E16439\_01/doc.1013/e13981/undejbs003.htm](https://docs.oracle.com/cd/E16439\_01/doc.1013/e13981/undejbs003.htm)
