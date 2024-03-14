# 🔸 7-4 Relationship Mapping

## DDD의 Aggregate

*   정의 \
    도메인을 중심으로 하는 애플리케이션을 개발할 때 등장하는 개념으로 애그리거트가 있다. \
    애그리거트란 관련된 객체들을 모아둔 하나의 단위로, VO와 엔티티로 구성된다.\
    그리고 애그리거트이 중심에는 애그리거트 루트가 존재하는데, 이를 애그리거트 루트라고 부른다.\
    객체들은 이 애그리거트 루트를 중심으로 관리된다.


*   왜 필요한가?\
    많은 수의 도메인 모델 간의 복잡한 관계를 파악하기란 쉬운 일이 아니다.

    그렇기 때문에 서로 관련이 있는 도메인 모델들 끼리 묶어 각 도메인 모델의 상세 구현보다는 더 큰 그림으로 도메인 모델간의 관계를 파악하는것이 좋다.\

* 특징\
  1\. 대부분의 경우 하나의 애그리거트는 하나의 엔티티와 여러개의 밸류로 구성된다. 드물게 하나의 애그리거트에 두개의 엔티티가 존재하기도 한다.\
  \
  2\. 각 애그리거트에는 **애그리거트 루트**라는 도메인 엔티티가 하나씩 있다.\
  \
  3\. 애그리거트 루트는 애그리거트 내에 속한 객체의 변경을 책임지며, 도메인 규칙에 따라 언제나 애그리거트 내 모든 도메인 모델들의 일관성을 유지할 책임이 있다.\
  \
  4\. 애그리거트는 DB 에 도메인을 저장하거나 읽어들이는 단위이며, 애그리거트를 읽을 때는 애그리거트 루트의 id 를 이용한다.\
  \
  5\. 일반적으로 하나의 애그리거트에는 하나의 도메인 엔티티(애그리거트 루트)가 존재하며, 0개 이상의 밸류 타입이 존재한다.\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://sgc109.github.io/2020/08/09/ddd-aggregate/](https://sgc109.github.io/2020/08/09/ddd-aggregate/)\
  [https://mangkyu.tistory.com/318](https://mangkyu.tistory.com/318)

## N + 1 problem

* 정의 \
  연관 관계에서 발생하는 이슈로 연관 관계가 설정된 엔티티를 조회할 경우에 조회된 데이터 갯수(n) 만큼 연관관계의 조회 쿼리가 추가로 발생하여 데이터를 읽어오게 된다.
* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음

## CascadeType.ALL

* 정의 \
  Cascade는 영속성 전이라는 의미이고, 영속성 전이란, 부모 엔티티가 영속화될 때 자식 엔티티도 같이 영속화되고, 부모 엔티티가 삭제될 때 자식 엔티티도 삭제되는 등 특정 엔티티를 영속 상태로 만들 때 연관된 엔티티도 함께 영속 상태로 전이되는 것을 의미한다. \
  즉, CascadeType.ALL은 유지, 변경, 새로고침, 병합, 제거 등 모든 Cascade 타입을 적용한다는 의미이다.
* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://zzang9ha.tistory.com/350](https://zzang9ha.tistory.com/350)

## orphanRemoval

* 정의 \
  JPA에서 자식엔티티의 수정은 insert update update delete 순으로 이어지는데\
  변경된 자식을 먼저 insert 하고, 기존의 자식을 NULL로 update 한다.\
  orphanRemoval = true 로 하면 기존 NULL 처리된 자식을 DELETE 한다.\
  PK값이 NULL로 변한 자식은 고아객체라고 해서 연결된 점이 없는 객체인데, orphanRemoval 옵션은 이 고아객체를 삭제해주는 역할을 한다.\

* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://dev-elop.tistory.com/entry/JPA-orphanRemoval-%EC%9A%A9%EB%8F%84](https://dev-elop.tistory.com/entry/JPA-orphanRemoval-%EC%9A%A9%EB%8F%84)

## Event Sourcing

* 정의 \
  이벤트 소싱이란 application의 모든 상태를 변경시키는 이벤트를 순서에 맞게, 모든 데이터를 저장한다. 사실 일반적인 경우에 필요하진 않다. 하지만 필요한 경우가 있고 장점도 충분히 가지고 있다. 설계할 때 몰라서 고려하지 않는 것 보다는 알아두면 좋은 설계 테크닉 정도로 이해하면 좋다.&#x20;

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F7Kr00%2FbtrKhQ6B3Cm%2FDaUkHS39KNgDGLmY4IrQC1%2Fimg.png" alt="" width="563"><figcaption><p>이벤트 소싱 예시</p></figcaption></figure>

* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://sabarada.tistory.com/231](https://sabarada.tistory.com/231)\


## @OneToMany

* 정의 \
  1:다 관계 매핑을 할 때 사용하는 애너테이션이다.\

*   특징(문제점)\
    이 애너테이션은 1 쪽에서 외래키를 관리하겠다는 의미가 되는데, 하지만 다 쪽에 무조건 외래키가 들어가게된다. 객체와 테이블의 패러다임 차이 때문에 객체의 반대편 테이블의 외래키를 관리하는 특이한 구조이다. \
    일단 업데이트 쿼리가 나간다. 성능상 좋지않다. 쿼리를 추적할 때 1 쪽에서 업데이트 쿼리가 나가는 상황이 나오게 되고, 다른 테이블도 많다면 이러한 상황은 운영을 힘들게 한다.


*   개선방법\
    다대일 단방향 관계로 매핑하고, 필요할 경우 양뱡향 매핑을 통해서 해결한다.\
    객체 입장에서보면, 반대방향으로 참조할 필요가 없는데 관계를 하나 만드는 것이지만,\
    DB의 입장으로 설계 방향을 맞춰서 유지보수하기 쉬운 쪽으로 선택할 수 있다.


* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://ict-nroo.tistory.com/125](https://ict-nroo.tistory.com/125)\


## @JoinColumn

* 정의 \
  이 어노테이션은 엔티티 간의 관계에서 외래 키(Foreign Key)를 매핑할 때 사용된다. 외래 키 컬럼과 참조하는 컬럼을 매핑하여 연관 엔티티 간의 관계를 구성한다.
* 왜 필요한가?\
  외래 키의 매핑을 세부적으로 설정할 수 있다. 컬럼명, 길이, NULL 허용 여부 등을 세부적으로 정의할 수 있다. 이를 통해 데이터베이스에서의 관계를 유연하게 구성할 수 있으며, 데이터베이스 연동 작업을 효율적으로 처리할 수 있다.\
  그리고 이 애너테이션을 사용하지 않으면 조인테이블 방식을 사용한다.(중간에 테이블을 추가한다.)
* 특징\
  이 애너테이션의 name 속성은 자기 필드명을 입력하는 용도이고, 매핑할 대상 컬럼명은 referencedColumnName 에 입력해준다.
* 사용예시\
  ex) @ManyToOne \
  &#x20;     @JoinColumn(name = "customer\_id", referencedColumnName = "id") \
  &#x20;      private Customer customer;
* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://ict-nroo.tistory.com/125](https://ict-nroo.tistory.com/125)\
  [https://newcodingman.tistory.com/entry/%EC%8A%A4%ED%94%84%EB%A7%81-JoinColumn-%EC%96%B4%EB%85%B8%ED%85%8C%EC%9D%B4%EC%85%98](https://newcodingman.tistory.com/entry/%EC%8A%A4%ED%94%84%EB%A7%81-JoinColumn-%EC%96%B4%EB%85%B8%ED%85%8C%EC%9D%B4%EC%85%98)
