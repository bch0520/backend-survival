# 🔸 3-1 DTO

## DTO 란?

데이터 전송 객체(Data Transfer Object). \
메소드 호출 수를 줄이기 위해 프로세스 간에 데이터를 전달하는 객체이다.\
즉, 여러 원격 호출을 단일 호출로 일괄처리하는 역할을 한다.\
또한, 직렬화를 캡슐화 함으로써 직렬화 이외의 코드를 제외하고, \
직렬화를 변경할 수 있는 명확한 지점을 제공해준다.\
B/E와 F/E 사이에서 일반적으로 사용되지만, 넓게는 B/E와 DB사이에서 쓰이기도 한다.\
JSON을 활용한 직렬화. getter/setter를 포함하되 다른 로직은 포함하지 않는다.

#### 제약조건

"between processes"\
“working with a remote interface, such as Remote Facade”\
다른 프로세스와 통신, 그것도 원격(네트워크를 통해)으로!

#### 프로세스간 통신(IPC=Inter Process Communication)

서로 다른 프로그램이 통신하는 기술이며, B/E와 F/E가 나뉜 환경에서 필수적이라 볼 수 있다.\
IPC에서 쓸 수 있는 기술은&#x20;

1. 파일 -> 가장 기본적인 접근이며, 원격에서 활용하기 어렵다.
2. 소켓 -> 파일과 유사하게 읽고 쓸 수 있지만, 원격에서 활용가능하다. HTTP 같은 고수준 프로토콜을 사용하면 상대적으로 쉬워진다. REST를 활용하면, RPC가 아닌 리소스에 대한 CRUD를 정리해야 함.
3. RPC(원격 프로시저 호출)를 위한 RMI(원격 함수 호출) 기술 제공. RPC를 이용하면 프로그래머는 함수의 위치가 로컬이든 원격이든 상관없이 동일한 코드를 사용할 수 있다. RMI는 객체간 컴퓨터간 메서드(함수)를 호출할 수 있게 해주는 기술이다.

## “무기력한 도메인 모델” 이란 그리고 안티 패턴인 이유

이러한 모델은 객체지향 디자인의 기본 개념에 너무 어긋난다. 데이터와 프로세스를 결합하여, 절차적 스타일을 지향한다. 이것의 단점은 어떠한 이점을 얻지 못한채 도메인 모델의 모든 비용을 발생시킨다는 점이다. \
주요비용은 데이터베이스에 매핑하는 것이 어색하다는 점이며, 이로 인해 O/R 매핑의 전체 계층이 발생한다.

## 자바빈즈(JavaBeans)

자바빈즈는 빌더형식의 개발도구에서 가시적으로 조작이 가능하고 또한 재사용이 가능한 소프트웨어 컴포넌트이다. 자바빈즈는 [엔터프라이즈 자바빈즈](https://ko.wikipedia.org/wiki/%EC%97%94%ED%84%B0%ED%94%84%EB%9D%BC%EC%9D%B4%EC%A6%88\_%EC%9E%90%EB%B0%94%EB%B9%88%EC%A6%88)(EJB)와 혼동하지 말아야 한다.&#x20;

#### 자바빈즈 관례

* 클래스는 직렬화되어야 한다.(클래스의 상태를 지속적으로 저장 혹은 복원시키기 위해)
* 클래스는 기본 생성자(인자가 없는)를 가지고 있어야 한다.
* 클래스의 속성들은 _get_, _set_ 혹은 표준 명명법을 따르는 메서드들을 사용해 접근할 수 있어야 한다.
* 클래스는 필요한 이벤트 처리 메서드들을 포함하고 있어야 한다.

## EJB(Enterprise JavaBeans)

EJB는 [자바 플랫폼, 엔터프라이즈 에디션](https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94\_%ED%94%8C%EB%9E%AB%ED%8F%BC,\_%EC%97%94%ED%84%B0%ED%94%84%EB%9D%BC%EC%9D%B4%EC%A6%88\_%EC%97%90%EB%94%94%EC%85%98)(Java EE)의 일부로서 서버 계열의 컴포넌트이다.

## Java의 record란?

불변데이터를 보다 간결하고 쉽게 생성할 수 있도록 하는 새로운 유형의 클래스이다.\
필드에 final을 사용하지 않으며, 생성자도 사용하지 않는다.\
레코드는 암묵적으로 final 클래스이고, abstract 선언불가.\
다른 클래스를 상속(extends) 받을 수 없음, 인터페이스 구현(implements)은 가능.

## DAO

데이터 접근 객체(Data Access Object).\
데이터베이스에 접근하는 객체이자, 서비스 모델부분과 데이터베이스를 연결하는 역할.\
데이터에 대한 CRUD 기능을 전담하는 객체.

#### 사용이유

효율적인 커넥션 관리와 보안성.\
비즈니스 로직을 분리하여 도메인 로직으로부터 DB와 관련한 메커니즘을 숨기기 위해 사용.

## ORM(Object Relational Mapping)

객체와 DB의 테이블 매핑을 말한다. \
자세히 말하면, 객체형 데이터와(자바 객체) 관계형 데이터(관계형 데이터베이스) 사이에서 개념적으로 일치하지 않는 부분을 해결하기 위해 이 둘 사이를 Mapping한 것을 의미한다.\
SQL문 작성없이 간단한 매핑설정으로 데이터베이스 테이블 데이터를 자바 객체로 전달 받을 수 있다.\
즉, 쿼리를 작성하지 않고 매서드 호출만으로 쿼리가 수행된다.

\
ex) USER 테이블 조회시 SELECT \* FROM USER; 쿼리 실행시켜야 하지만, user.findAll()이라는 메서드 호출을 통해 데이터 조회 가능.



