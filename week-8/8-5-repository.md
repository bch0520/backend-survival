# 🔸 8-5 Repository

## 리파지토리

* 정의 \
  리포지토리(Repository)는 소프트웨어 개발에서 데이터 액세스 계층을 추상화하는 디자인 패턴이다. 주로 데이터베이스나 외부 소스와 같은 데이터 저장소에 접근하고 데이터를 조작하는 데 사용되며, 리포지토리는 비즈니스 로직과 데이터베이스 간의 결합을 최소화하여 시스템의 유연성과 유지보수성을 향상시킨다.
* 왜 필요한가?\

* 특징
  1. **데이터 액세스 추상화**: 리포지토리는 데이터 액세스를 추상화하여 비즈니스 로직에서 데이터베이스의 세부 사항을 숨깁니다. 이를 통해 데이터베이스와의 결합을 최소화하고 데이터 액세스 코드를 분리할 수 있습니다.
  2. **CRUD 작업 지원**: 대부분의 리포지토리는 데이터베이스에서의 CRUD(Create, Read, Update, Delete) 작업을 지원합니다. 이를 통해 애플리케이션에서 데이터를 생성, 읽기, 갱신, 삭제할 수 있습니다.
  3. **도메인 객체 관리**: 리포지토리는 도메인 객체를 관리하고 데이터베이스와의 변환을 처리합니다. 도메인 객체와 데이터베이스 간의 매핑 및 변환을 담당하여 데이터 액세스 코드를 단순화하고 중복을 줄일 수 있습니다.
  4. **쿼리 지원**: 일부 리포지토리는 데이터베이스에서 복잡한 쿼리를 실행하고 결과를 반환하는 기능을 제공합니다. 이를 통해 애플리케이션에서 다양한 데이터 액세스 요구를 처리할 수 있습니다.
  5. **트랜잭션 관리**: 일부 리포지토리는 데이터 액세스 작업을 트랜잭션으로 묶어서 원자적으로 실행하는 기능을 제공합니다. 이를 통해 데이터의 일관성과 안전성을 보장할 수 있습니다.\

* 사용예시\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  chat GPT

## Application Layer와 UI Layer

* 특징(비교)
  1. **Application Layer (응용 계층)**:
     * Application Layer는 비즈니스 로직과 사용자 인터페이스(UI) 사이의 중간 계층이다.
     * 비즈니스 로직을 구현하고 처리하는 데 사용됩니다. 이 계층은 사용자 인터페이스(UI)와 데이터 액세스 계층(Data Access Layer 또는 Persistence Layer) 간의 상호 작용을 조정하고 중재한다.
     * 주요 책임에는 비즈니스 규칙 및 프로세스의 구현, 데이터의 가공 및 전달, 외부 시스템과의 통합 등이 포함된다.
     * Application Layer는 도메인 모델과 관련된 작업을 처리하고, UI Layer로부터 입력을 받아 처리한 후 결과를 반환한다.\

  2. **UI Layer (사용자 인터페이스 계층)**:
     * UI Layer는 사용자와 소프트웨어 간의 상호 작용을 담당하는 계층이다.
     * 사용자 인터페이스(UI)를 구현하고 사용자와의 상호 작용을 처리한다. 이는 주로 화면에 데이터를 표시하고 사용자의 입력을 받아들이는 등의 작업을 포함한다.
     * 주요 책임에는 사용자 인터페이스(UI)의 디자인과 구현, 사용자 입력의 수신 및 처리, 화면 표시 등이 포함된다.
     * UI Layer는 사용자의 요청을 Application Layer로 전달하고, Application Layer에서 처리된 결과를 사용자에게 표시한다.

<figure><img src="https://wikibook.co.kr/images/readit/20141002/figure4.png" alt="" width="375"><figcaption></figcaption></figure>

* 레퍼런스 모음\
  chat GPT
