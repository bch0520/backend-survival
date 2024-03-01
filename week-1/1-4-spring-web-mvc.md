# 🔸 1-4 Spring Web MVC

## Spring vs Spring boot

스프링은 프레임 워크이고, 스프링 부트는 스프링으로 애플리케이션을 만들때에 필요한 설정을 간편하게 처리해주는 Spring 프레임 워크를 기반으로한 별도의 도구이다. 스프링은 다양한 기능과 모듈을 제공하고 웹 애플리케이션 개발, 데이터 액세스, 보안, 배치 및 일괄 처리 등의 기능을 가지고 있다. 반면 스프링 부트는 스프링 프레임워크 기반의 애플리케이션의 개발 만을 진행할 수 있으며 이를 편리하게 하기 위한 프레임워크이다. 스프링 부트는 초기 설정이 간편할 뿐만 아니라, 자체적인 내장 서버가 있어 배포를 빠르고 쉽게 할 수 있다.



## Web Server vs Web Application Server(WAS)

#### 다루는 태스크

웹서버는 간단한 요청에 대한 응답을 제공하며, WAS는 데이터베이스, 서비스 및 엔터프라이즈 시스템의 더 복잡한 콘텐츠를 제공한다.

**사용되는 프로토콜**

웹서버는 주로 HTTP를 사용하고 FTP와 SMTP도 지원하며, WAS는 많은 프로토콜을 지원한다.

**콘텐츠 유형**

웹 서버는 HTML 페이지, 이미지, 비디오 및 파일과 같은 정적 콘텐츠를 제공하며, WAS는 실시간 업데이트, 개인화된 정보 및 고객 지원과 같은 동적 콘텐츠를 제공한다.

**멀티스레딩**

웹서버는 일반적으로 멀티스레딩을 사용하지 않으며, WAS는 멀티스레딩을 사용하여 요청을 동시에 처리한다.

### Tomcat(=WAS)

톰캣은 동적인 웹을 만들기 위한 웹 컨테이너, 서블릿 컨테이너 라고 불리며 웹서버에서 정적으로 처리할 데이터를 제외하고 jsp, asp, php등은 웹 컨테이너(톰캣)에게 전달한다.\
아파치는 정적인 웹페이지만 처리하기 때문에 안정적이고, 빠르다. 하지만 톰캣은 속도가 느리고, 트래픽 과부하에 약하지만 데이터 흐름이 유동적이며, DB연결, 데이터조작, 다른 응용프로그램과 상호작용이 가능하다.\
톰캣은 8080포트로 처리한다.



## MVC 패턴

**MVC** (모델-뷰-컨트롤러) 는 사용자 인터페이스, 데이터 및 논리 제어를 구현하는데 널리 사용되는 소프트웨어 디자인 패턴이다.

#### 모델

모델은 앱이 포함해야할 데이터가 무엇인지를 정의한다. 데이터의 상태가 변경되면, 모델을 일반적으로 뷰에게 알리며 가끔 컨트롤러에게 알리기도 한다. 예를 들어, 쇼핑 리스트 앱에서 모델은 리스트 항목이 포함해야 하는 데이터(품목, 가격 등) 이미 존재하는 리스트 항목이 무엇인지를 지정한다.

#### 뷰

뷰는 앱의 데이터를 보여주는 방식을 정의한다. 쇼핑 리스트 앱에서, 뷰는 항목이 사용자에게 보여지는 방식을 정의하며, 표시할 데이터를 모델로부터 받는다.

#### 컨트롤러

컨트롤러는 앱의 사용자로부터 입력에 대한 응답으로 모델 또는 뷰를 업데이트하는 로직을 포함한다. 예를 들어보면, 쇼핑 리스트는 항목을 추가하거나 제거할 수 있게 해주는 입력 폼과 버튼을 갖는다. 이러한 액션들은 모델이 업데이트되는 것이므로, 입력이 컨트롤러에게 전송되고, 모델을 적당하게 처리한 다음, 업데이트된 데이터를 뷰로 전송한다.

##

## 관심사의 분리

#### 관심사 분리를 해야하는 이유

관심사의 분리는 하나의 관심사가 하나의 기능만 수행하도록 코드를 구성하는 것을 말한다. 한 객체(모듈, 클래스) 안에서 다양한 관심사를 수행하면 코드가 복잡해져서 코드에 대한 이해도가 떨어진다. 이는 유지보수적인 측면에서 악영향을 줄 수 있다. 때문에 하나의 관심사가 하나의 기능을 수행하도록 코드를 작성하는 것이 좋다.

#### 관심사를 분리하는 방법(SOLID 원칙)

1.SRP(단일 책임의 원칙) : 하나의 클래스는 하나의 책임(관심사)을 갖는다.

2.ORP(개방/폐쇄 원칙): 소프트웨어는 확장에는 열려있으나, 변경에는 닫혀 있어야 한다.

3.LSP(리스코프 치환 원칙): 프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다.

4.ISP(인터페이스 분리 원칙): 특정 클라이언트를 위한 인터페이스 여러 개가 범용 인터페이스 하나보다 낫다.

5.DIP(의존관계 역전 원칙): 프로그래머는 “추상화에 의존해야지, 구체화에 의존하면 안된다.”

이외에도 "변하는 것과 변하지 않는 것의 분리", "공통(중복)코드의 분리" 등으로 코드를 분리할 수 있다.

&#x20;

## Spring Annotation&#x20;

#### @RestController

Spring에서 Controller 중 View로 응답하지 않는 Controller를 의미한다.\
method의 반환 결과를 JSON 형태로 반환한다. @RestController가 적혀있는 Controller의 method는 HttpResponse로 바로 응답이 가능하다. @ResponseBody 역할을 자동적으로 해주는 어노테이션이다. data return이 주목적이다.

#### @Controller

API와 view를 동시에 사용하는 경우에 사용한다.\
대신 API 서비스로 사용하는 경우는 @ResponseBody를 사용하여 객체를 반환한다.\
view return이 주목적이다.

즉, @RestController = @Controller + @ResponseBody

#### @ResponseBody

HttpMessageConverter를 이용하여 JSON으로 요청에 응답할 수 있게 해주는 어노테이션이다.\
view가 아닌 `JSON 형식의 값을 응답할 때` 사용하는 어노테이션으로, 문자열을 리턴하면 그 값이 http response header가 아닌 response body에 들어간다. 이미 @RestController 어노테이션이 붙어 있다면, 쓸 필요가 없다. 허나 그렇지 않은 단순 컨트롤러라면, HttpResponse로 응답 할 수 있게 해준다.

#### @GetMapping

@RequestMapping(Method=RequestMethod.GET)과 같은 역할을 한다.

#### @RequestMapping

어떤 URL을 어떤 method가 처리할 지 매핑해주는 어노테이션이다. Controller나 Controller의 메소드에 적용한다. 요청을 받는 형식인 GET/POST/PUT/PATCH/DELETE를 정의하기도 한다. (정의하지 않으면 자동적으로 GET으로 설정된다.)