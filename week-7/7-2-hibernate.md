# 🔸 7-2 Hibernate

## **Hibernate**

* 정의 \
  프로그래밍 언어를 위한 관계형 매핑 도구로 ORM 중 하나이다.
* 사용하는 이유\
  Hibernate는 직접적이고 [지속적인](https://en.wikipedia.org/wiki/Persistence\_\(computer\_science\)) 데이터베이스 액세스를 높은 수준의 객체 처리 기능으로 대체하여 [객체-관계형 임피던스 불일치 문제를 처리](https://en.wikipedia.org/wiki/Object%E2%80%93relational\_impedance\_mismatch)
* 주요기능\
  [Java 클래스에서 데이터베이스 테이블](https://en.wikipedia.org/wiki/Table\_\(database\)) 로 매핑 하고 Java 데이터 유형에서 [SQL](https://en.wikipedia.org/wiki/SQL) 데이터 유형으로 매핑하는 것이다. Hibernate는 또한 데이터 쿼리 및 검색 기능을 제공하며, 이는 SQL 호출을 생성하고 개발자가 결과 집합을 수동으로 처리하고 개체를 변환하는 수고를 덜어준다.
* 특징\
  1\. [클래스 간 일대다](https://en.wikipedia.org/wiki/One-to-many\_\(data\_model\)) 및 [다대다](https://en.wikipedia.org/wiki/Many-to-many\_\(data\_model\)) 관계를 구성할 수 있는 기능이 제공됩니다 . Hibernate는 객체가 [클래스 ](https://en.wikipedia.org/wiki/Class\_\(computer\_programming\))[유형](https://en.wikipedia.org/wiki/Data\_type)의 다른 인스턴스와 일대다 관계를 갖는 [재귀](https://en.wikipedia.org/wiki/Reflexive\_relation) 연관을 관리할 수도 있다.\
  \
  2\. Hibernate 는 Hibernate의 데이터 객체에 대해 SQL과 유사한 쿼리를 작성하기 위 HQL(Hibernate Query Language)이라는 [SQL](https://en.wikipedia.org/wiki/SQL) 에서 영감을 받은 언어를 제공한다.\
  \
  3\. Hibernate는 POJO( [Plain Old Java Objects](https://en.wikipedia.org/wiki/Plain\_Old\_Java\_Object) ) 에 대한 투명한 지속성을 제공한다.\
  \
  4\. [Hibernate는 독립형 Java](https://en.wikipedia.org/wiki/Java\_\(programming\_language\)) 애플리케이션과 [서블릿](https://en.wikipedia.org/wiki/Java\_Servlet) , [EJB](https://en.wikipedia.org/wiki/Enterprise\_JavaBeans) 세션 Bean 및 [JBI 서비스 구성 요소를 사용하는 ](https://en.wikipedia.org/wiki/Java\_Business\_Integration)[Java EE](https://en.wikipedia.org/wiki/Java\_EE) 애플리케이션 모두에서 사용할 수 있다.\
  \
  5\. Hibernate [전문 용어](https://en.wikipedia.org/wiki/Jargon) 에서 엔터티 _는 다른 객체와 독립적으로 조작될 수 있는 Hibernate의_ [지속](https://en.wikipedia.org/wiki/Persistence\_\(computer\_science\)) 메커니즘 에 있는 독립형 객체이다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://en.wikipedia.org/wiki/Hibernate\_(framework)](https://en.wikipedia.org/wiki/Hibernate\_\(framework\))\


## **데이터 모델**&#x20;

* 정의 \
  데이터 모델(data model)은 [데이터](https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0)의 관계, 접근과 그 흐름에 필요한 처리 과정에 관한 추상화된 모형이다.  [소프트웨어](https://ko.wikipedia.org/wiki/%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4) 개발과 유지, 보수의 기준이 된다. 데이터 모델은 데이터 구조를 결정한다.\

* 특징\
  데이터 모델은 관계형 데이터베이스와 같은 데이터 관리 시스템에서 기억장치를 위한 정형 데이터를 기술한다. 이들은 일반적으로 [워드 처리](https://ko.wikipedia.org/wiki/%EC%9B%8C%EB%93%9C\_%ED%94%84%EB%A1%9C%EC%84%B8%EC%84%9C) 문서, [이메일 메시지](https://ko.wikipedia.org/wiki/%EC%A0%84%EC%9E%90\_%EC%9A%B0%ED%8E%B8), 사진, 디지털 오디오, 비디오와 같은 비정형 데이터를 가리키지는 않는다.\

*   구성요소\
    1\. 구조 - 데이터베이스에 표현될 대상으로서의 개체 타입과 개체 타입들간의 관계\
    2\. 연산 - 저장된 실제 데이터를 처리하는 방법, 데이터를 조작하는 기본 도구\
    3\. 제약조건 - 저장될 수 있는 데이터의 논리적인 제약조건


* 표현용어\
  1\. 개체 -  행, 튜플, 카디널리티(개체의 수)\
  2\. 속성 - 열, 필드, 디그리(속성의 수)\
  3\. 관계 \

*   관점\
    1\. 개념적 데이터 모델

    현실세계에 대한 인식을 추상적인 개념으로 표현, 인간이 이해할수 있는 정보 구조로 표현, \
    대표적으로 개체-관계(E-R) 모델\


    2\. 논리적 데이터 모델\
    구현 모델이라고도 함. 개념 데이터 모델링의 개념 구조를 컴퓨터가 이해할 수 있도록 변환한 구조.\
    필드, 데이터타입 등으로 개념적 모델 구현. 관계 모델, 계층 모델, 네트워크 모델 등으로 구분.\
    \
    3\. 물리적 데이터 모델\
    성능과 직접적인 연관. 하위수준의 데이터 모델로 데이터가 저장되는 방법을 표현. 레코드형식, 레코드 순서, 접근경로, 저장방법에 관한 전문가가 정의.\

*   종류\
    1\. 관계형 데이터 모델\


    1\) 표(Table)을 이용해 데이터 관계를 정의

    2\) 데이터간의 관계를 Key를 통해 구성\
    3\) 1:1, 1:N, N:M 관계를 자유롭게 표현

    4\) 간결하고 명확하고 상호변환성이 좋지만 성능이 떨어진다.

    5\) 대표 DBMS: 오라클, MySQL, MsSQL, SQLite, 포스트그레

    \
    2\. 계층형 데이터 모델\
    \
    1\) 트리 형태의 논리적 구조를 가지며, 개체는 트리의 노드로 표현

    2\) 개체간의 관계를 링크로 표현되며 부모-자식 관계를 가짐\
    3\) 1:N 대응관계만 존재\
    4\) 레코드 삭제 시 연쇄 삭제(Triggered Delete)가 이루어짐\
    5\) 개체들 간 Cycle이 허용되지 않음\
    6\) 개체(Entity)를 세그먼트(Segment)라 지칭\
    7\) 대표 DBMS: IMS\
    \
    3.네트워크형 데이터 모델\
    \
    1\) 망형 모델, 그래프형 모델이라고도 불린다.

    2\) CODASYL이 제안한 모델로, CODASYL 모델이라고도 한다.

    3\) 대표적인 DBMS가 DBTG로, DBTG 모델이라고도 한다.

    4\) 그래프를 이용해서 데이터 논리 구조를 표현

    5\) 상하위 레코드는 N:M 대응 관계

    6\) 상위 레코드를 Owner, 하위 레코드를 Member라 지칭

    7\) 이러한 구조 때문에 Owner-Member 모델이라고도 한다.

    8\) 대표 DBMS: DBTG, EDBS, TOTAL


* 레퍼런스 모음\
  [https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0\_%EB%AA%A8%EB%8D%B8](https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0\_%EB%AA%A8%EB%8D%B8)\
  [https://itwiki.kr/w/%EB%8D%B0%EC%9D%B4%ED%84%B0\_%EB%AA%A8%EB%8D%B8](https://itwiki.kr/w/%EB%8D%B0%EC%9D%B4%ED%84%B0\_%EB%AA%A8%EB%8D%B8)\


## EntityManager

* 정의 \
  엔티를 관리하는 역할을 하는 클래스로, 내부에 영속성 컨텍스트라는 것을 두어서 엔티티들을 관리한다.\
  엔티티가 과자라면, 엔티티 매니저는 과자를 만드는 주체, 엔티티 매니저 팩토리는 과자를 만드는 공장에 비유할 수 있다.\

* 개인적인 생각(추가적인 질문 또는 내용)\
  **<영속성 컨텍스트>**\
  **'**영속성'이라 함은 비휘발성이라고 말할 수 있다. 하지만 일반적으로 저장장치를 말할 때 휘발, 비휘발이라는 용어를 사용하고, DB에 관해 얘기할 때는 영속성이라 하는 것 같다.\
  '컨텍스트'는 직역하면 문맥, 맥락이라는 뜻인데 프로그래밍 쪽에서는 환경이라는 뜻으로 쓰이는 것 같다.\
  즉, 영속성 컨텍스트는 엔티티를 영구히 저장하는 환경이라는 뜻이다.\
  \
  **\<Entity Manager Factory>**\
  \

* 레퍼런스 모음\
  [https://perfectacle.github.io/2018/01/14/jpa-entity-manager-factory/](https://perfectacle.github.io/2018/01/14/jpa-entity-manager-factory/)\


## 트랜잭션

* 정의 \
  작업단위에서 중간에 하나의 작업이라도 실패하면 아예 맨 처음의 상태로 되돌리는 하나의 작업단위를 말한다. 트랜잭션 처리가 정상적으로 완료된 경우 [커밋](http://wiki.hash.kr/index.php/%EC%BB%A4%EB%B0%8B)(commit)을 하고, 오류가 발생할 경우 원래 상태대로 [롤백](http://wiki.hash.kr/index.php/%EB%A1%A4%EB%B0%B1)(rollback)을 한다.\

* 왜 필요한가?\
  데이터베이스 서버에 여러 개의 클라이언트가 동시에 액세스 하거나 응용프로그램이 갱신을 처리하는 과정에서 중단될 수 있는 경우 등 데이터 부정합을 방지하고자 할 때 사용한다
* 특징\
  [데이터베이스](http://wiki.hash.kr/index.php/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4)의 트랜잭션이 안전하게 수행되기 위해서는 ACID 조건을 충족해야 한다.\
  \
  1\. 원자성(atomicity)\
  트랜잭션은 더 이상 쪼갤 수 없는 최소한의 업무단위이다. 트랜잭션이 데이터베이스에 모두 반영되던지, 아니면 전혀 반영되지 않아야 하며 작업이 부분적으로 실행되거나 중단되지 않는 것을 보장하는 것으로 즉, All or Nothing의 개념으로서 작업 단위를 일부분만 실행하지 않는다는 것을 의미한다\
  \
  2\. 일관성(consistency)\
  트랜잭션이 완료된 결괏값이 일관적인 DB 상태를 유지하는 것을 말한다. 시스템이 가지고 있는 고정요소는 수행 전과 후의 상태가 같아야 하며 트랜잭션의 작업 처리 결과가 항상 일관성이 있어야 한다는 것으로 트랜잭션이 진행되는 동안 데이터베이스가 변경되더라도 업데이트된 데이터베이스로 트랜잭션이 진행되는 것이 아니라, 처음 트랜잭션을 진행하기 위해 참조한 데이터베이스로 진행된다. 이렇게 함으로써 각 사용자가 일관성 있는 데이터를 볼 수 있는 것이다.\
  \
  3\. 고립성(isolation)\
  하나의 트랜잭션 수행시 다른 트랜잭션의 작업이 끼어들지 못하도록 보장하는 것이다. 즉, 트랜잭션 끼리는 서로를 간섭할 수 없다. 트랜잭션이 실행하는 도중에 변경한 데이터는 이 트랜잭션이 완료될 때까지 다른 트랜잭션이 참조하지 못하게 하는 특성이다.\
  \
  4\. 지속성(durability)\
  트랜잭션이 정상적으로 종료된 다음에는 영구적으로 데이터베이스에 작업의 결과가 저장되어야 한다. 지속성(durability)은 트랜잭션의 성공 결과 값은 장애 발생 후에도 변함없이 보관되어야 한다는 것이다.\

* 사용 예시\
  상품구매라는 작업을 예시로 들면,\
  1\. 상품 재고 조회\
  2\. 구매자 잔액 조회\
  3\. 상품재고 -1\
  4\. 유저 잔고에서 돈을 뺌\
  5\. 주문생성\
  이러한 과정이 있다고 한다면 주간에 유저잔고에 돈이 충분히 없다면, 이 작업은 모두 실패로 돌아갈 것이다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://perfectacle.github.io/2018/01/14/jpa-entity-manager-factory/](https://perfectacle.github.io/2018/01/14/jpa-entity-manager-factory/)\
  [http://wiki.hash.kr/index.php/%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98](http://wiki.hash.kr/index.php/%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98)\


## JPQL

*   정의 \
    JPQL은 객체지향 데이터베이스에서 엔티티를 조회하고 조작하기위한 쿼리 언어이다.\
    이는 SQL과 쿼리 언어임에는 동일하지만 엔티티를 대상으로 쿼리를 작성하기 때문에&#x20;

    객체지향 관점에서 데이터를 다룰 수 있게 해준다.\

*   왜 필요한가?\
    1\. 모든 쿼리를 객체지향 방식으로 표현할 수 없다.\
    2\. SELECT문은 조회에 여러 조건이 붙는 경우도 많고 조건이 동적으로 변하기도 한다.\
    3\. JPA를 사용하면 엔티티 객체를 중심으로 개발한다.\
    4\. 검색을 할 때도 테이블이 아닌 엔티티 객체를 대상으로 검색한다.\
    5\. 모든 DB 데이터를 객체로 변환해서 검색하는 것은 불가능하다.

    \

* 특징\
  1\. 객체지향쿼리\
  2\. 플랫폼 독립적. 즉 jpa가 지원하는 모든 데이터베이스에 사용가능.\
  3\. 타입세이프. 컴파일 시점에 쿼리 오류를 확인할 수 있어 안전하다.\
  4\. 유연한 결과 반환. 다양한 타입의 결과를 반환 할 수 있다.\

* 사용방법\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://lordofkangs.tistory.com/386](https://lordofkangs.tistory.com/386)\
  [https://sirobako.co.kr/detail/156](https://sirobako.co.kr/detail/156)\
  [https://velog.io/@koo9b9h/JPA%EC%97%90-%EB%8C%80%ED%95%B4-%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5-%EC%BF%BC%EB%A6%AC-%EC%96%B8%EC%96%B4JPQL-%EA%B8%B0%EB%B3%B8](https://velog.io/@koo9b9h/JPA%EC%97%90-%EB%8C%80%ED%95%B4-%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5-%EC%BF%BC%EB%A6%AC-%EC%96%B8%EC%96%B4JPQL-%EA%B8%B0%EB%B3%B8)\


## @Entity

* 정의\
  이 애너테이션이 붙은 클래스는 JPA가 관리하는 것으로 엔티티라고 불리며, 테이블과 매핑할 때 사용한다.\

* 속성\
  _**Name**_  -   JPA에서 사용할 엔티티 이름을 지정. 보통 기본값인 클래스 이름을 사용.\

*   특징(주의사항)\
    \- 기본 생성자는 필수 (JPA가 엔티티 객체 생성 시 기본 생성자를 사용)

    \- final 클래스, enum, interface, inner class 에는 사용할 수 없음

    \- 저장할 필드에 final 사용 불가\

* 레퍼런스 모음\
  [https://data-make.tistory.com/610](https://data-make.tistory.com/610)\


## @Table

* 정의 \
  이 애너테이션은 엔티티와 매핑할 테이블을 지정하며, 생략 시 매핑한 엔티티 이름을 테이블 이름으로 사용한다.
*   속성\
    _**Name**_ : 매핑할 테이블 이름 (default. 엔티티 이름 사용)

    _**Catalog**_ : catalog 기능이 있는 DB에서 catalog 를 매핑 (default. DB 명)

    _**Schema**_ : schema 기능이 있는 DB에서 schema를 매핑

    _**uniqueConstraints**_ : DDL 생성 시 유니크 제약조건을 만듦. 스키마 자동 생성 기능을 사용해서 DDL을 만들 때만 사용\

* 특징\

* 레퍼런스 모음\
  [https://data-make.tistory.com/610](https://data-make.tistory.com/610)\


## @Id

* 정의 \
  기본키 직접 매핑 방법 중 기본키 직접 할당과 자동생성 중 직접할당 방법을 사용할 때 사용하는 애너테이션이다. @Id 필드에 em.persist()로 엔티티를 저장하기 전, setId()를 사용하여 직접 식별자 값을 할당해준다.\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\
  기본키를 매핑하는 이유는 영속성 컨텍스트는 식별자 값으로 구분하므로, 엔티티를 영속상태로 만들기 위해서는 반드시 식별자값이 필요.\

* 레퍼런스 모음\
  [https://velog.io/@sweet\_sumin/id-%EC%95%8C%EA%B3%A0-%EC%94%81%EC%8B%9C%EB%8B%A4](https://velog.io/@sweet\_sumin/id-%EC%95%8C%EA%B3%A0-%EC%94%81%EC%8B%9C%EB%8B%A4)\
  [https://data-make.tistory.com/610](https://data-make.tistory.com/610)\
  [https://coding-start.tistory.com/71](https://coding-start.tistory.com/71)



