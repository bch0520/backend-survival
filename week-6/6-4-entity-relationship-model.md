# 🔸 6-4 Entity-Relationship Model

## ERM(Entity-Relationship Model) 이란?

1. 정의\
   ER모델은  특정 지식 영역에서 상호 관련된 관심 사항을 설명합니다. 기본 ER 모델은 관심 항목을 분류하는 엔터티 유형으로 구성되며 [엔터티](https://en.wiktionary.org/wiki/entity) (해당 엔터티 유형의 인스턴스) 간에 존재할 수 있는 관계를 지정한다.\

2.  구성요소\
    1\) 개체\
    현실 세계에서 꼭 필요한 사람이나 사물과 같이 구별되는 모든 것을 가르키며, 데이터로써 DB에 저장할 가치가 있는 중요한 사람, 사물, 개념, 사건 등을 뜻하며 최소 하나 이상의 개체를 가지고 있어야 한다.\
    (ex. 학원에 필요한 개체 - 학생, 수업 등)

    \
    2\) 속성\
    개체나 관계가 가지고 있는 고유의 특성으로 DB에 저장할 데이터의 가장 작은 논리적 단위이다.\
    (ex. 학생 개체의 속성 - 이름, 성별, 핸드폰 번호 등)\
    \
    3\) 관계\
    서로 다른 개체가 맺고 있는 의미 있는 연관성을 뜻한다. 즉, 개체 사이의 대응 관계(매핑)를 뜻한다.

    (ex. 학원과 수업사이의 연관성은 '수강'.)\

3. 리퍼런스 모음\
   [https://en.wikipedia.org/wiki/Entity%E2%80%93relationship\_model](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship\_model)\
   [https://nirsa.tistory.com/99](https://nirsa.tistory.com/99)\


## Entity

1. 정의\
   엔터티는 물리적으로나 논리적으로 존재하는 것. 엔터티는 집이나 자동차와 같은 물리적 객체, 주택 매매나 자동차 서비스와 같은 이벤트, 고객 거래나 주문과 같은 개념.\

2. 적절한 엔터티 특징\
   1\) 업무에서 필요한 정보이며, 업무 프로세스에 이용되어야 한다.\
   2\) 두개 이상의 인스턴스의 집합이어야 한다. ex)고객정보는 2명 이상\
   3\) 엔터티와 관계는 속성을 가진다. 다만 [약한 엔터티(속성만으로 고유하게 식별할 수 없는 엔터티)를](https://en.wikipedia.org/wiki/Weak\_entity) 제외한 모든 엔터티에는 [고유](https://en.wikipedia.org/wiki/Unique\_key) / [기본](https://en.wikipedia.org/wiki/Primary\_key) 키로 사용될 수 있는 고유 식별 속성의 최소 집합이 있어야 한다.\
   ex_)_ 고객 엔터티에는 회원 ID, 패스워드, 이름, 주소 전화번호의 속성이 존재.\
   4\) 다른 엔티티간의 관계가 존재해야 한다.\

3. 리퍼런스 모음\
   [https://en.wikipedia.org/wiki/Entity%E2%80%93relationship\_model](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship\_model)\
   [https://coding-factory.tistory.com/870](https://coding-factory.tistory.com/870)\


## 데이터베이스 정규화

1.  정의\
    데이터베이스 내의 데이터 구조를 조직화하고 최적화하는 과정이다.


2.  필요한 이유\
    데이터 중복을 제거하고, 효율성을 향상시키며, 데이터 무결성을 보장하기 위함이다.


3.  정규화의 단계\
    1\) 제1 정규화\
    데이터베이스의 각 컬럼이 원자 값을 가지도록 하는 과정이다. 즉, 각 컬럼은 하나의 데이터만 저장하며, 다중 값을 갖지 않는다.

    \
    2\) 제2 정규화\
    제1 정규화를 완료한 테이블에서 주제와 관련없는 컬럼을 다른 테이블로 빼는 작업이다.\
    ex) 회원주문 테이블에서 회원테이블과 상품테이블로 별도로 나눈다.

    \
    3\) 제3 정규화\
    제2 정규화를 완료한 테이블에서, 이행적 함수 종속성을 제거하는 과정이다. 이행적 함수 종속이란 A -> B 종속, B -> C 종속,  A -> C 종속인 관계를 말한다.

    ex) 강의ID가 교수ID와 교수이름에 종속되어 있는 경우, 강의ID+교수ID와 교수ID+교수이름으로 분리한다.
4. 리퍼런스 모음\
   [https://hstory0208.tistory.com/entry/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4-%EC%A0%95%EA%B7%9C%ED%99%94Normalization%EB%9E%80-%EC%98%88%EC%8B%9C%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%B4%EB%B3%B4%EC%9E%90](https://hstory0208.tistory.com/entry/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4-%EC%A0%95%EA%B7%9C%ED%99%94Normalization%EB%9E%80-%EC%98%88%EC%8B%9C%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%B4%EB%B3%B4%EC%9E%90)
