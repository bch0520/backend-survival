# 🔸 7-5 Spring Data JPA

## Spring Data JPA

* 정의 \
  스프링 데이터의 공통적인 기능에서 JPA의 유용한 기술이 추가된 기술이다.  Spring Data JPA에서는 스프링 데이터의 인터페이스인 PagingAndSortingRepository를 상속 받아 JpaRepository 인터페이스를 만들었으며, JPA를 더 편리하게 사용하는 메서드를 제공합니다.\

* 왜 필요한가?\
  스프링 데이터 JPA를 사용하면, 리포지터리 역할을 하는 인터페이스를 만들어 데이터베이스의 테이블 조회, 수정, 생성, 삭제 같은 작업을 간단하게 할 수 있다.\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://yozm.wishket.com/magazine/detail/2160/](https://yozm.wishket.com/magazine/detail/2160/)

## Dao 와 Repository 차이

1. DAO는 데이터 지속성의 추상화입니다. 그러나 저장소는 객체 모음을 추상화한 것입니다.
2. DAO는 스토리지 시스템에 더 가까운 하위 수준 개념입니다. 그러나 리포지토리는 도메인 개체에 더 가까운 상위 수준 개념입니다.
3. DAO는 데이터 매핑/액세스 레이어로 작동하여 보기 흉한 쿼리를 숨깁니다. 그러나 리포지토리는 도메인과 데이터 액세스 계층 사이의 계층으로, 데이터 수집 및 도메인 개체 준비의 복잡성을 숨깁니다.
4. DAO는 저장소를 사용하여 구현할 수 없습니다. 그러나 저장소는 기본 저장소에 액세스하기 위해 DAO를 사용할 수 있습니다.

* 레퍼런스 모음\
  [https://www.baeldung.com/java-dao-vs-repository](https://www.baeldung.com/java-dao-vs-repository)

## JPA Repository와 DDD의 Repository(차이점)

JPA Repository는 주로 데이터베이스와의 상호 작용을 추상화하기 위한 인터페이스이며, DDD의 Repository는 도메인 모델과의 상호 작용을 중심으로 설계된 인터페이스이다. 도메인 주도 설계에서 Repository는 도메인 모델의 영속성과 도메인 로직을 관리하고, JPA Repository는 주로 엔티티와 데이터베이스 간의 상호 작용을 관리한다.

* 레퍼런스 모음\
  Chat GPT

## Spring AOP

*   정의 \
    AOP는 Aspect Oriented Programming의 약자로 관점 지향 프로그래밍이라고 불린다.\
    관점 지향은 쉽게 말해 어떤 로직을 기준으로 핵심적인 관점, 부가적인 관점으로 나누어서 보고\
    그 관점을 기준을 각각 모듈화하겠다는 것이다. 여기서 모듈화란 어떤 공통된 로직이나 기능을 하나의 단위로 묶는 것을 말한다.


* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://engkimbs.tistory.com/entry/%EC%8A%A4%ED%94%84%EB%A7%81AOP](https://engkimbs.tistory.com/entry/%EC%8A%A4%ED%94%84%EB%A7%81AOP)

## @Transactional

*   정의 \
    데이터베이스 작업에서 트랜잭션을 관리하는 데 사용되는 어노테이션이다.

    트랜잭션을 관리하는 선언적 방법을 제공하며 트랜잭션 어노테이션은 클래스 또는 메서드 레벨에 적용할 수 있다. 클래스 수준에서 적용하면 클래스의 모든 메서드에 대한 기본 트랜잭션 설정을 설정하며,

    메서드 수준에서 적용하면 해당 특정 메서드의  class-level settings 값을 overrides 한다.

    트랜잭션이 구성되었으므로 이제 클래스 또는 메서드 수준에서 @Transactional 어노테이션을 bean에 달 수 있다.\

* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://colevelup.tistory.com/34](https://colevelup.tistory.com/34)
