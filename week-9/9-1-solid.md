# 🔸 9-1 SOLID

## SOLID

* 정의 \
  &#x20;SOLID란 [로버트 마틴](https://ko.wikipedia.org/wiki/%EB%A1%9C%EB%B2%84%ED%8A%B8\_%EB%A7%88%ED%8B%B4)이 2000년대 초반에 명명한 [객체 지향 프로그래밍](https://ko.wikipedia.org/wiki/%EA%B0%9D%EC%B2%B4\_%EC%A7%80%ED%96%A5\_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D) 및 [설계](https://ko.wikipedia.org/w/index.php?title=%EA%B0%9D%EC%B2%B4\_%EC%A7%80%ED%96%A5\_%EC%84%A4%EA%B3%84\&action=edit\&redlink=1)의 다섯 가지 기본 원칙을 마이클 페더스가 [두문자어](https://ko.wikipedia.org/wiki/%EB%91%90%EB%AC%B8%EC%9E%90%EC%96%B4) [기억술](https://ko.wikipedia.org/wiki/%EA%B8%B0%EC%96%B5%EC%88%A0)로 소개한 것이다.&#x20;
* 왜 필요한가?\
  프로그래머가 시간이 지나도 [유지 보수](https://ko.wikipedia.org/wiki/%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4\_%EC%9C%A0%EC%A7%80\_%EB%B3%B4%EC%88%98)와 확장이 쉬운 시스템을 만들고자 할 때 이 원칙들을 함께 적용할 수 있다.
* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://ko.wikipedia.org/wiki/SOLID\_(%EA%B0%9D%EC%B2%B4\_%EC%A7%80%ED%96%A5\_%EC%84%A4%EA%B3%84)#cite\_note-ub-solid-2](https://ko.wikipedia.org/wiki/SOLID\_\(%EA%B0%9D%EC%B2%B4\_%EC%A7%80%ED%96%A5\_%EC%84%A4%EA%B3%84\)#cite\_note-ub-solid-2)\


## SRP (Single Responsibility Principle, 단일 책임 원칙)

* 정의 \
  응집도를 높이는 설계원칙으로 한 클래스는 단 한가지 변경 이유만 가져야 한다는 원칙이다.\
  즉, 각 클래스의 역할은 각각 1개라는 의미로 이해했다.
* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)

## OCP (Open-Closed Principle, 개방-폐쇄 원칙)

* 정의 \
  클래스, 모듈, 함수등은 확장에 대해서는 열려있어야 하고, 수정에 대해서는 닫혀있어야 한다.\
  \
  Open - 모듈의 기능을 변경할 수 있어야 한다.\
  Close - 변경이 다른 곳으로 퍼져나가지 않아야 한다.\

* 왜 필요한가?\

* 특징\
  이 원칙은 추상화를 통해 실현 가능하고, interface를 활용한다.\

* 사용예시\
  `CartRepository`라는 인터페이스를 만들고, `JdbcCartRepository`란 클래스로 구현한다. 추후에 DBMS를 MongoDB로 변경하기로 했다면, `MongoCartRepository`라는 클래스를 새로 만들고, 기존에 `CartRepository`를 사용하던 곳은 아무 것도 수정하지 않아도 된다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)

## LSP (Liskov Substitution Principle, 리스코프 치환 원칙)

* 정의 \
  서브타입이란 그것의 기반타입으로 치환가능해야한다. 치환가능 하다는 말은 그것을 대체했을 때 ,  행위의 변화가 없어야 한다.\

* 왜 필요한가?\

* 특징\

* 사용예시\
  직사각형은 정사각형을 대체할 수 없다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)

## ISP (Interface Segregation Principle, 인터페이스 분리 원칙)

* 정의 \
  응집력이 없는 커다란 인터페이스를 여러 개의 작은 인터페이스로 나눈다.\
  하나의 인터페이스가 여러 인터페이스를 상속하는 형태로 작성할 수 있다.\

* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)

## DIP (Dependency Inversion Principle, 의존관계 역전 원칙)

* 정의 \
  상위수준의 모듈은 하위수준의 모듈에 의존해서는 안되며, 둘 모두 추상화에 의존해야 한다.\
  또한, 추상화는 구체적인 사항에 의존해서는 안되며, 구체적인 사항은 추상화에 의존해야 한다.
* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)

