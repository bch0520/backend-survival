# 🔸 9-2 Hexagonal Architecture

## Hexagonal Architecture

* 정의 \
  헥사고날이란 6각형이란 뜻인데, 핵심 비즈니스 로직을 다루는 애플리케이션을 제외한 외부는 여러개가 존재할 수 있다는 차원에서 이런 표현이 쓰였다. 이 아키텍처의 주요 목표는 응용 프로그램의 비즈니스 로직을 외부 세계로부터 격리시켜 유연하고 테스트하기 쉬운 구조를 만드는 것이다. 이를 위해 핵심 비즈니스 로직은 중앙의 도메인 영역에 위치하며, 입력과 출력을 처리하는 포트와 어댑터를 통해 외부와 소통한다. \

* 3계층 아키텍쳐 VS 헥사고날\
  가장 대중적으로 사용하는 아키텍처는 3계층 아키텍처(3 Tier Layered Architecture)로 비즈니스 로직, 데이터 액세스, 프레젠테이션 계층으로 구성된다. 이와 달리 헥사고날 아키텍처는 비즈니스 로직에 중점을 두고 외부와 격리되어 있어, 더욱 유연하고 테스트하기 쉽다.

<figure><img src="https://tech.osci.kr/wp-content/uploads/2023/03/hexagonal-green.png" alt="" width="563"><figcaption></figcaption></figure>

*   장/단점\
    1\. 장점\
    1\) 유연성: 외부 시스템이나 인프라와의 의존성을 낮추어, 구성 요소를 쉽게 교체하거나 업데이트할 수 있다.

    2\) 테스트 용이성: 비즈니스 로직을 독립적으로 테스트할 수 있어 품질 향상과 개발 속도 향상에 도움이 된다.

    3\) 유지보수성: 책임이 분리되어 있어, 코드의 이해와 수정이 용이하며, 변화에 빠르게 대응할 수 있다.\
    \
    2\. 단점\
    1\) 구현 복잡성: 포트와 어댑터를 구성하고 관리하는 데 약간의 복잡성이 따른다.

    2\) 초반 개발 시간 증가: 아키텍처를 처음 구축할 때 시간과 노력이 더 필요할 수 있다.\

*   사용예시(비교)\
    <3계층 아키텍처>\
    // UserService.java public class UserService { private UserRepository userRepository;

    ```
    public UserService(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

    public void createUser(String name, String email) {
        User user = new User(name, email);
        userRepository.save(user);
    }
    ```

    }

    // UserRepository.java public interface UserRepository { void save(User user); }

    // UserRepositoryImpl.java public class UserRepositoryImpl implements UserRepository { public void save(User user) { // 데이터베이스에 사용자 저장 } }\
    \
    <헥사고날 아키텍처>\
    // CreateUserUseCase.java public interface CreateUserUseCase { void createUser(String name, String email); }

    // CreateUserUseCaseImpl.java public class CreateUserUseCaseImpl implements CreateUserUseCase { private UserRepository userRepository;

    ```
    public CreateUserUseCaseImpl(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

    public void createUser(String name, String email) {
        User user = new User(name, email);
        userRepository.save(user);
    }
    ```

    }

    // UserRepository.java public interface UserRepository { void save(User user); }

    // UserRepositoryAdapter.java public class UserRepositoryAdapter implements UserRepository { public void save(User user) { // 데이터베이스에 사용자 저장 } }\

* 개인적인 생각(추가적인 질문 또는 내용)\
  위 코드 예시를 보면,  3계층에서는 비즈니스 로직인 서비스 클래스에서 리포지토리의 거쳐 데이터엑세스 계층에 접근하는 반면(비즈니스 로직이 격리되어 있지 않음), 핵사고날은  CreateUserUseCase 인터페이스를 통해 비즈니스 로직을 정의하고, CreateUserUseCaseImpl 클래스(비즈니스 로직 격리)에서 구현한다. UserRepositoryAdapter는 UserRepository 인터페이스를 구현하며, 외부와의 소통을 담당한다. 결론적으로, 헥사고날 아키텍처는 비즈니스 로직과 외부 요소를 격리시키기 때문에, 유연성과 테스트 용이성이 향상되는 것 같다.\

* 레퍼런스 모음\
  [https://tech.osci.kr/hexagonal-architecture/](https://tech.osci.kr/hexagonal-architecture/)

## POJO

*   정의 \
    POJO란 Plain Old Java Object의 약자로, 이를 직역하면 순수한 오래된 자바 객체이다.\
    즉, Java로 생성하는 순수한 객체를 뜻한다.\
    이를 해석하면 POJO는 객체 지향적인 원리에 충실하면서 환경과 기술에 종속되지 않고, 필요에 따라 재활용 될 수 있는 방식으로 설계된 오브젝트를 의미한다.\
    이러한 POJO에 애플리케이션의 핵심 로직과 기능을 담아 설계하고 개발하는 방법을 POJO 프로그래밍이라고 한다.


*   왜 필요한가?\
    1\) 특정 환경이나 기술에 종속적이지 않으면 재사용이 가능하고, 확장 가능한 유연한 코드를 작성할 수 있다.\
    2\) 저수준 레벨의 기술과 환경에 종속적인 코드를 제거하여 코드를 간결해지면 디버깅하기에도 상대적으로 쉬워진다.\
    3\) 특정 기술이나 환경에 종속적이지 않기 때문에 테스트가 단순해진다.\
    4\) 객체지향적인 설계를 제한 없이 적용할 수 있다.(가장 중요)


* POJO와 Spring의 관계\
  Spring은 POJO 프로그래밍을 지향하는 프레임워크이다.\
  최대한 다른 환경이나 기술에 종속적이지 않도록 하기 위한 POJO 프로그래밍 코드를 작성하기 위해 Spring 프레임워크에서는 IoC/DI, AOP, PSA를 지원하고 있다.\

*   특징\
    1\. Java나 Java의 스펙에 정의된 것 이외에는 다른 기술이나 규약에 얽매이지 않아야 한다.\
    다른 기술을 상속받는 경우, 다른 요구사항이 생겨서 코드를 수정해야 하는 경우 기술전체를 삭제할 수도 있고, 다중 상속이 불가능 하기때문에 객체지향적이 코드 구현이 어려워 진다.\
    \
    2\. 특정환경에 종속적이지 않아야 한다.\
    이는 특정한 프레임워크에서만 동작하면 안된다는 의미이다. 아파치 톰캣이든, jetty든 상관없이 동작해야 한다. 최악의 경우 애플리케이션을 전부 수정해야 할 수도 있다.

    \

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://ittrue.tistory.com/211](https://ittrue.tistory.com/211)
