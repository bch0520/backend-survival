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
  즉, 각 클래스의 역할은 각각 1개라는 의미이다.
* 적용방법\
  각자 역할을 분배해서 클래스를 구성했지만 중복되는 코드가 있을때 super 클래스를 사용하여, 부모 클래스에 위임하는 방법이 있으며, 책임을 한 클래스에 모을 수가 없거나 애매할 때는 새로운 클래스를 만들어서 그곳에 모으는 것도 응집성을 높이는 방법이다.
* 적용사례\
  guitar라는 클래스가 있는데, 기타 시리얼 넘버, 기타색상, 가격, 타입, 모델 등의 정보군이 있다고 하자.\
  여기서 시리얼 넘버는 고정적인 정보이고, 나머지는 변화가 있을 수 있는 유동적인 정보이다. (시간이 흐르고 가격이 변할 수 있고 특정 모델이 변동되거나 사라질 수도 있고 기타 색상도 변할 수도 있다.)\
  이럴때 고정적인 정보인 시리얼넘버(guitar)와 나머지 유동적인 정보군(guitar spec)을 분리해서 관리해준다면 변화에 의해서 변경되는 것을 한곳에서 관리해 줄 수 있게 된다.
* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)\
  [https://www.nextree.co.kr/p6960/](https://www.nextree.co.kr/p6960/)

## OCP (Open-Closed Principle, 개방-폐쇄 원칙)

* 정의 \
  클래스, 모듈, 함수등은 확장에 대해서는 열려있어야 하고, 수정에 대해서는 닫혀있어야 한다.\
  \
  Open - 모듈의 기능을 변경할 수 있어야 한다.\
  Close - 변경이 다른 곳으로 퍼져나가지 않아야 한다.\

* 특징\
  이 원칙은 추상화를 통해 실현 가능하고, interface를 활용한다.
* 적용방법\
  1\. 변경될 것과 변하지 않을 것을 엄격하게 구분한다.\
  2\. 이 두 모듈이 만나는 지점에 인터페이스를 정의한다.\
  3\. 구현에 의존하기보다는 인터페이스에 의존하도록 코드를 작성합니다.\

* 적용사례\
  1.`CartRepository`라는 인터페이스를 만들고, `JdbcCartRepository`란 클래스로 구현한다. 추후에 DBMS를 MongoDB로 변경하기로 했다면, `MongoCartRepository`라는 클래스를 새로 만들고, 기존에 `CartRepository`를 사용하던 곳은 아무 것도 수정하지 않아도 된다.\
  \
  2\. 기타라는 클래스가 있지만 추후에 바이올린, 피아노 등의 악기도 추가가 될 수 있는데 이때 최소한의 수정을 위해 StringInstrument라는 인터페이스를 생성하여 추상화를 진행하면 된다.

<figure><img src="https://www.nextree.co.kr/content/images/2021/01/ocp_after-e1400596262977.png" alt="" width="563"><figcaption></figcaption></figure>

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)\
  [https://www.nextree.co.kr/p6960/](https://www.nextree.co.kr/p6960/)

## LSP (Liskov Substitution Principle, 리스코프 치환 원칙)

* 정의 \
  서브타입이란 그것의 기반타입으로 치환가능해야한다. 치환가능 하다는 말은 그것을 대체했을 때 ,  행위의 변화가 없어야 한다.\

* 왜 필요한가?\

* 적용방법\
  1\. 만약 두 개체가 똑같은 역할을 한다면, 둘을 하나의 클래스로 표현하고 이들을 구분할 수 있는 필드를 만든다.\
  2\. 똑같은 연산을 제공하지만, 이들을 약간씩 다르게 구현한다면 공통의 인터페이스를 만들고 둘이 이를 구현한다.(인터페이스 상속)\
  3\. 공통된 연산이 없다면 완전 별개인 2개의 클래스를 만든다.\
  4\. 만약 두 개체가 하는 일에 추가적으로 무언가를 더 구현한다면 구현 상속을 사용한다.\

* 적용사례\
  List만 사용하면 문제가 되지 않지만, 속도개선은 위해 HashSet을 사용해야한다고 하면\
  별도로 코드의 수정이 많을 수 있기 때문에 기반타입인 Collection을 적용해 코드를 변경해준다.\
  아래와 같이 1)을 2)로 변경해준다.\
  \
  1\) void f() {\
  LinkedList list = new LinkedList();\
  // ...\
  modify(list);\
  }\
  \
  void modify(LinkedList list) {\
  list.add(...);\
  doSometingWith(list);\
  }\
  \
  2\) void f() {\
  Collection collection = new HashSet();\
  // ...\
  modify(list);\
  }\
  \
  void modify(Collection collection) {\
  collection.add(...);\
  doSometingWith(collection);\
  }\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)\
  [https://www.nextree.co.kr/p6960/](https://www.nextree.co.kr/p6960/)

## ISP (Interface Segregation Principle, 인터페이스 분리 원칙)

* 정의 \
  응집력이 없는 커다란 인터페이스를 여러 개의 작은 인터페이스로 나눈다. 하나의 인터페이스가 여러 인터페이스를 상속하는 형태로 작성할 수 있다. SRP가 클래스의 단일 책임만을 강조한다면, ISP는 인터페이스 단일 원칙을 강조한다. 즉 여러 개의 작은 인터페이스로 나눈다는 의미는 꼭 필요한 인터페이스만 사용해야 한다는 의미이다.\

* 적용 방법\
  1\. 클래스 인터페이스를 통한 분리\
  클래스의 상속을 통하여 인터페이스를 나눌 수 있다. 이와 같은 구조는 클라이언트에게 변화를 주지 않을 뿐만아니라, 인터페이스를 분리하는 효과를 갖습니다.\
  \
  2.객체 인터페이스를 통한 분리\
  위임을 이용하여 인터페이스를 나눌 수 있다. 위임이란, 특정 일의 책임을 다른 클래스나 메소드에 맡기는 것이다. 만약 다른 클래스의 기능을 사용하고 싶지만, 그 기능을 변경하고 싶지 않다면 상속 대신 위임을 사용한다.\

* 적용 사례\
  Java Swing의 Jtable 클래스에는 굉장히 많은 메소드들이 있는데, 모든 서비스들을 필요로하는 객체에게는 기능 전부를 노출하지만, 이벤트 처리와 관련해서는 여러 리스너 인터페이스를 통해 해당기능만 노출한다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)\
  [https://www.nextree.co.kr/p6960/](https://www.nextree.co.kr/p6960/)

## DIP (Dependency Inversion Principle, 의존관계 역전 원칙)

* 정의 \
  상위수준의 모듈은 하위수준의 모듈에 의존해서는 안되며, 둘 모두 추상화에 의존해야 한다.\
  또한, 추상화는 구체적인 사항에 의존해서는 안되며, 구체적인 사항은 추상화에 의존해야 한다.\

* 적용방법\
  이를 적용하는 방법은 레이어링이다. 상위레벨의 레이어가 하위레벨의 레이어를 바로 의존하게 하는게 아니라 이 둘 사이에 존재하는 추상레벨을 통해 의존해야 한다는 것이다.

<figure><img src="https://www.nextree.co.kr/content/images/2021/01/jdchoi_20140305_layer.png" alt="" width="563"><figcaption><p>레이어링 예시</p></figcaption></figure>

* 적용사례\
  소켓 통신 프로그램에서 응답을 비동기로 확인할 때, 클라이언트 스레드는 메시지를 send한 후 receive하는 대신 응답을 처리하는 훅 메서드(커맨드 오브젝트)를 등록한다. receive를 담당하는 스레드는 서버로부터 응답을 접수하면 대응하는 훅 메서드를 찾아 실행한다. 즉, receive 스레드는 서버의 응답접수와 훅 메서드 실행을 담당한다. \
  이렇게 하면 두 가지 장점이 있다.\
  첫째, 클라이언트 스레드의 잦은 응답 확인을 제거할 수 있고, \
  둘째, 클라이언트는 응답을 확인하는 작업에서 자유로워지므로 다른 작업을 할 수 있는 기회비용을 확보할 수 있다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/9/textbook?programId=backend-10)\
  [https://www.nextree.co.kr/p6960/](https://www.nextree.co.kr/p6960/)

