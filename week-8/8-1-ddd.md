# 🔸 8-1 DDD

## 도메인 주도 설계

* 정의 \
  소프트웨어의 복잡성은 도메인의 복잡성에서 유래한다. 현실이 복잡하기 때문에, 현실을 위한 소프트웨어가 복잡한 것도 당연하다. 우리는 기술 영역과 도메인 영역을 분리하고(관심사의 분리), 도메인을 적절히 다루기 위한 모델을 구축함으로써 복잡성과 싸울 것이다. 이를 위한 사고방식, 도구 모음이 바로 도메인 주도 설계다.\

* 왜 필요한가?\
  소프트웨어의 복잡성을 최소화하기 위해 필요하다. 그리고 요구사항을 쉽게 반영하고 소통이 원활하게 이루어지게 할 수 있다.\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/8/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/8/textbook?programId=backend-10)

## 기술부채의 의미

* 정의 \
  지저분한 방식으로 빠르게 개발하면 기능을 빠르게 선보일 수 있는 장점은 있지만, 추후에 기능을 추가하거나 수정해야할 때 추가적으로 발생하는 시간은 부채가 된다는 의미.\

* 기술부채를 최소화하는 방법\
  1\. 개발자간의 규칙(컨벤션) 설정\
  2\. 리팩토링\
  3\. 테스트 코드 작성\
  4\. 소통과 협업\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://yozm.wishket.com/magazine/detail/1331/](https://yozm.wishket.com/magazine/detail/1331/)

## 보편언어

* 정의 \
  모두가 하나의 언어(어휘 모음)를 사용한다. 도메인 전문가, 비즈니스 분석가, 소프트웨어 설계자, 프로그래머 등은 모두 같은 언어를 사용한다. 도메인 전문가가 쓰는 어휘에 끌려가야 한다는 의미가 아니라, 비즈니스 도메인을 적절하게 다룰 수 있는 용어를 함께 만들어서 코드를 작성할 때도 사용해야 한다는 의미다. 즉, 설계하기 어렵거나 코딩하기 어려운 어휘 체계는 재검토가 필요하다.&#x20;
* 왜 필요한가?\
  협업하는 개발자들끼리 협업하기에 불편함이 없고, 바로바로 코드의 의도를 이해시키 수 있기 때문에 필요하다.
* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/8/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/8/textbook?programId=backend-10)

## 제한된 컨텍스트

* 정의 \
  같은 용어나 객체이름을 지칭할 때 굳이 다른 개념이나 의미까지 해석할 필요없이 지금 진행하고 있는 프로젝트에 관련된 내용으로 이해할 수 있게 제한된 용어를 쓰는 것을 말한다.
* 왜 필요한가?\
  프로젝트에 관하여 소통할 때 보다 효율적으로 할 수 있고, 오해의 소지를 제거할 수 있다.\

* 특징\

* 사용예시\
  Account라는 용어를 사용할 때 '사용자의 계정'을 의미하는 것인지 '통장 계좌'를 의미하는 것인지 굳이 헷갈리지 않게 한다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/8/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/8/textbook?programId=backend-10)

## 하위 도메인

* 정의 \
  시스템을 나누는데 Bounded Context라는 단위를 사용한다면, 도메인을 나눌 땐 Subdomain이라는 단위를 사용한다. 전자는 소프트웨어를 조직화하는 방법이라면, 후자는 현실을 조직화하는 방법이다. 전자는 개발하면서 발전시킬 수 있지만, 후자는 개발하면서 맞춰나가야 한다. 좀 더 어렵게 표현하면, Subdomain은 Problem Space고, Bounded Context는 Solution Space다. 즉, 서브도메인의 복잡성이 존재하는 문제를 파악하고 정의하는 공간이라면, 제한된 컨텍스트 그 문제를 해결하는, 요구사항을 충족시키는 공간이라고 할 수 있다.\

* 왜 필요한가?\

* 특징\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/8/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/8/textbook?programId=backend-10)
