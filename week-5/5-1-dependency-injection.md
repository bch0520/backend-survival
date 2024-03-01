# 🔸 5-1 Dependency Injection

## Spring AOP

* 정의\
  AOP는 Aspect Oriented Programming의 약자로 관점 지향 프로그래밍이라고 불린다.\
  관점 지향은 어떤 로직을 기준으로 핵심적인 관점, 부가적인 관점으로 나누어서 보고 그 관점을 기준으로 모듈화(어떤 로직이나 기능을 하나로 묶음) 하겠다는 것이다.
* 왜 필요한가? /왜 생겼는가?\
  모듈화가 생긴 이유는 여기저기 흩어진 관심사를 수정해야 할 때, 일일이 진행하게 되면 유지보수에 어려움이 있기 때문이다.  흩어진 관심사란 코드상에서 반복해서 사용하지만 여기저기 흩어져 있는 코드를 말한다. 결국 흩어진 관심사를 모듈화하는 이유는 작업을 효율적으로 할 수 있기 때문이다. 위 그림에서 모듈화 시켜놓은 블럭을 Aspect라 한다.

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FZrxxK%2FbtrxoHWDBA4%2Fhs93YWUYWe1vwIkUr2fru1%2Fimg.png" alt="" width="375"><figcaption><p>AOP 예시</p></figcaption></figure>

* 특징\
  1\) 스프링에서 제공하는 스프링 AOP는 프록시 기반의 AOP 구현체이다.\
  2\) 프록시 객체를 사용하는 것은 접근제어 및 부가기능을 추가하기 위해서이다.\
  3\) 스프링 AOP는 스프링 Bean에만 적용할 수 있다.\
  4\) 모든 AOP 기능을 제공하는 것이 아닌 중복코드, 프록시 클래스 작성의 번거로움을 해결하기 위해서이다.\
  5\) 스프링 AOP는 순수 자바로 구현되어 있기 때문에 특별한 컴파일 과정이 필요하지 않다.\

* AOP 적용방법\
  1\) 컴파일 타임 적용\
  컴파일 시점에 바이트 코드를 조작하여 AOP가 적용된 바이트 코드를 생성하는 방법\
  2\) 로드 타임 적용\
  순수하게 컴파일 한 뒤, 클래스를 로딩하는 시점에 클래스 정보를 변경하는 방법\
  **3) 런타임 적용**\
  스프링 AOP가 주로 사용하는 방법, A라는 클래스 타입의 Bean을 만들때 A타입의 프록시 Bean을 만들어 프록시 Bean이 Aspect 코드를 추가하여 동작하는 방법\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://code-lab1.tistory.com/193](https://code-lab1.tistory.com/193)\


## Dependency Injection

* 정의 \
  DI란 코드에 나타날 수 있는 특정 클래스에 대한 의존관계(또는 의존성)을 외부로 제거하는 것이다.
* 왜 필요한가?\
  DI란 의존성을 제거하기 위해 필요하다.
* 특징\
  DI방식의 컨테이너가 해주는 일은 구체적으로 런타임시 의존객체를 전달해주어서 그것과 런타임 의존관계를 만들어주는 것이다. 즉, 코드상에서 구체 클래스에 의존관계를 가지지 않도록 한다.
* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://groups.google.com/g/ksug/c/77jLQan8Q-E/m/yTo8xj-F-8gJ?pli=1](https://groups.google.com/g/ksug/c/77jLQan8Q-E/m/yTo8xj-F-8gJ?pli=1)

## 싱글턴패턴

* 정의 \
  생성자가 여러 차례 호출되더라도 실제로 생성되는 객체는 하나이고 최초 생성 이후에 호출된 생성자는 최초의 생성자가 생성한 객체를 리턴한다. 이와 같은 디자인 유형을 싱글턴 패턴이라고 한다
* 사용하는 이유\
  &#x20;싱글턴 패턴을 사용하면 메모리 낭비를 방지할 수 있다. 예를들어, 사용자가 1초에 10번 똑같은 요청을 보내면 똑같은 객체를 1초에 10번 생성하고 소멸되는 메모리 낭비 문제가 발생하게 된다. 하진만 싱글턴 패턴은 1번 객체를 생성하여 이후에도 계속 사용하도록 공유(static)하면 메모리 낭비문제를 방지할 수 있다.
* 특징(단점)\
  1\) 의존성이 높아진다. 정적 메서드를 이용하기 때문에 다른 클래스에도 영향을 미친다.\
  2\) private 생성자 때문에 상속이 어렵다. 싱글턴 패턴은 기본 생성자를 private으로 만들기 때문에 상속이 어렵다.\
  3\) 싱글턴 패턴의 인스턴스는 자원을 공유하고 있는데 이것은 단위 테스트를 하기에 문제가 있다.\

* 사용예시\
  싱글톤 기본 생성자를 private으로 선언해서 외부에서 new 키워드로 새로운 객체 생성을 못하게 막는다.\
  해당 클래스를 아래와 같이 테스트 해보면 같은 결과값이 나온다.

<figure><img src="../.gitbook/assets/스크린샷 2024-02-27 오후 1.54.37.png" alt="" width="563"><figcaption><p>싱글톤 구현 예시</p></figcaption></figure>

<figure><img src="../.gitbook/assets/스크린샷 2024-02-27 오후 1.55.11.png" alt="" width="563"><figcaption><p>테스트 결과</p></figcaption></figure>

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://velog.io/@jhbae0420/%EC%8B%B1%EA%B8%80%ED%86%A4-%ED%8C%A8%ED%84%B4%EC%9D%98-%EC%82%AC%EC%9A%A9-%EC%9D%B4%EC%9C%A0%EC%99%80-%EB%AC%B8%EC%A0%9C%EC%A0%90](https://velog.io/@jhbae0420/%EC%8B%B1%EA%B8%80%ED%86%A4-%ED%8C%A8%ED%84%B4%EC%9D%98-%EC%82%AC%EC%9A%A9-%EC%9D%B4%EC%9C%A0%EC%99%80-%EB%AC%B8%EC%A0%9C%EC%A0%90)

## IoC(Inversion of Control)

* 정의 \
  소프트웨어 설계 원칙 중 하나로 프로그래밍에 있어 객체 생성 및 관리를 개발자에서 프레임 워크나 애플리케이션에 위임하는 것을 뜻한다.
* 왜 필요한가?\

* 특징\
  1\. 프레임 워크가 객체 생성 및 생명 주기를 관리한다.\
  2\. 개발자는 단지 필요한 인터페이스나 규약을 따르면 그것을 구현한다.\
  3\. 객체간의 의존성은 외부에서 정의되며, 프레임 워크가 이러한 의존성을 주입하여 연결한다.
* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://bitkunst.tistory.com/entry/ABOUTSeries-12-IoC-Inversion-of-Control-%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%EC%A0%84-DI-Dependency-Injection-%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85](https://bitkunst.tistory.com/entry/ABOUTSeries-12-IoC-Inversion-of-Control-%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%EC%A0%84-DI-Dependency-Injection-%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85)

## Spring Bean

*   정의 \
    빈은 스프링 컨테이너에 의해 관리되는 재사용 가능한 소프트웨어 컴포넌트이다.\
    즉, 스프링 컨테이너가 관리하는 자바 객체를 뜻하며, 하나 이상의 빈을 관리한다.\
    빈은 인스턴스화된 객체를 의미하며, 스프링 컨테이너에 등록된 객체를 스프링 빈이라고 한다.&#x20;

    쉽게 이해하자면 new 키워드 대신 사용한다고 보면된다.&#x20;
* 왜 사용하는가?\
  가장 큰 이유는 스프링 간 객체가 의존관계를 관리하도록 하는 것에 가장 큰 목적이 있다. 객체가 의존관계를 등록할 때 스프링 컨테이너에서 해당하는 빈을 찾고, 그 빈과 의존성을 만든다.\

*   스프링 빈 등록방법\
    1\) xml에 직접등록\
    2\) @Bean 어노테이션을 이용\
    3\) @Component, @Controller, @Service, @Repository 어노테이션을 이용


* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://dev-wnstjd.tistory.com/440](https://dev-wnstjd.tistory.com/440)

## BeanFactory

* 정의 \
  빈을 생성하고 의존관계를 설정하는 기능을 담당하는 가장 기본적인 IoC 컨테이너이자 클래스를 말한다. 스프링 빈 컨테이너에 접근하기 위한 최상위 인터페이스이다.
* 왜 필요한가?\
  스프링 빈을 관리하고 조회하는 역할을 담당한다.
* 특징\
  1\) `getBean()`을 제공한다.\
  2\) **Lazy-loading** 방식을 사용한다\
  3\) 빈을 사용할 때 빈을 로딩한다. ( 필요할 때만 로딩하기 때문에, 가벼운 경량 컨테이너이다. )
*   개인적인 생각(추가적인 질문 또는 내용)\
    cf) ApplicationContext\
    1\) BeanFactory를 확장하고 있어 BeanFactory의 확장된 버전이라고 생각해도 좋다.

    **2) Eager-loading** 방식을 사용한다

    3\) 런타임 실행시 모든 빈을 미리 로딩시킨다.
* 레퍼런스 모음\
  [https://velog.io/@saint6839/BeanFactory-%EC%99%80-ApplicationContext%EC%9D%98-%EC%B0%A8%EC%9D%B4](https://velog.io/@saint6839/BeanFactory-%EC%99%80-ApplicationContext%EC%9D%98-%EC%B0%A8%EC%9D%B4)
