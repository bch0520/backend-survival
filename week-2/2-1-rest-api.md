# 🔸 2-1 REST API

## API

컴퓨터나 컴퓨터 프로그램 사이의 연결이다. 쉬운 표현을 빌리자면, 두 소프트웨어 구성요소가 통신할 수 있게하는 메커니즘이다. API를 구성하는 호출들은 서브루틴, 메소드, 요청, 통신 엔드포인트라고 부른다. API 규격은 이 호출들을 정의하며, API의 한 가지 목적은 시스템이 동작하는 방식에 관한 내부의 세세한 부분을 숨기는 것으로, 내부의 세세한 부분이 나중에 변경되더라도 프로그래머가 유용하게 사용할 수 있고 일정하게 관리할 수 있는 부분들만 노출시킨다.

## 정보은닉 vs 캡슐화

정보은닉은 캡슐화되어 있는 데이터와 함수에 대해 외부에서 어떻게 구현되어 있는지 모르게 세부 구현 사항을 숨기는 것을 말한다. 캡슐화가 되었다고 해서 반드시 정보은닉이 되어있는 것은 아니다. 정보은닉은 블랙박스와 같다.

반면, 캡슐화는 관련된 정보를 묶음으로써 캡슐 내부와 외부를 구별짓는 장치이다. 즉, 특정 객체 속에 있는 데이터와 함수들이 다른 객체 속에 있는 데이터와 함수들과 구별이 이루어진다. 정보은닉이 이루어지기 위해서는 캡슐화가 선행되어야 한다.

#### #정보은닉의 이점

1. 정보은닉은 추상화를 향상시켜준다.(정보은닉의 정도에 따라 추상화의 정도도 변한다.)
2. 내부 데이터나 알고리즘의 변경이 용이하다.
3. 모듈의 독립성을 높여준다.(해당 모듈이 타 모듈에 끼치는 영향력 낮아짐)
4. 확장성을 높여준다.(타 객체에 영향을 주지 않기 때문에 데이터의 추가 및 삭제에 용이)

## Architecture vs Architecture Style

아키텍처란 시스템 구성 및 동작원리이며, 또한 설계과정에서 수행되는 다양한 의사결정의 결과물이다.  즉, 아키텍처는 구조화 과정의 시작이자 기준점이라고 말 할 수 있다.

아키텍처 스타일은 아키텍처 설계에서 나타나는 문제점을 해결하고 아키텍처가 만족시켜야하는 시스템 품질속성을 달성할 수 있는 방법을 문서로 정리한 것이다. 다른 말로는, 그 스타일을 따르는 아키텍처가 지켜야하는 제약조건들의 집합이며 아키텍처 패턴이라고도 불린다.

<figure><img src="https://learn.microsoft.com/ko-kr/azure/architecture/includes/images/microservices-logical.png" alt=""><figcaption><p>아키텍처 스타일 예시: 마이크로 서비스(<a href="https://learn.microsoft.com/ko-kr/azure/architecture/guide/architecture-styles/">https://learn.microsoft.com/ko-kr/azure/architecture/guide/architecture-styles/</a>)</p></figcaption></figure>

## REST(7가지 제약 조건)

1.  #### Starting with the Null Style

    architectural design을 할 때 두 가지 관점이 있다.

    하나는 빈 곳에서 시작하여 원하는 시스템의 조건을 충족시킬때까지 architecture을 만드는 것이다.

    다른 하나는 제한이 없던 시스템에서 출발하여 제한을 추가하면서 원하는 시스템으로 만드는 것이다.

    첫번째 방법은 창의성을 중시하고, 두번째 방법은 제한과 시스템 context에 대한 이해를 중시한다.

    REST는 두번째 방법에 의해서 발전되어 왔다.
2.  #### Client-Server

    유저 인터페이스와 데이터 저장을 분리함으로써 여러 플랫폼에서의 이식성을 높이고 서버를 단순화시켜 scale up 하기도 쉽게 하였다. 웹에서는 이런 분리가 독립적인 진화를 가능하게 하였다.
3.  #### Stateless

    커뮤니케이션은 stateless여야만 하고 client로부터 서버로 가는 각 request들은 request를 이해할 때 필요한 모든 정보를 포함하고 있어야 하며 server에 저장된 어떠한 context에 의해서도 advantage를 받으면 안된다. 따라서 Session state는 client에 의해서만 관리된다.
4.  #### Cache

    Cache 제약은 response에 담긴 data에 cacheable한지 아닌지 라벨링을 강제한다.

    만약 response가 cacheable하면 client의 cache는 나중의 동일한 request에 대해 data를 재사용할 권한을 갖게 된다. cache 제약의 장점은 부분적인 interaction들을 제거하여 효율성과 scalability를 높이고 평균적인 지연을 줄여 user가 느끼는 performance를 향상시켜준다.

    그러나 trade-off로 cache에 있는 data가 stale된 경우에도 server로 바로 보낼 수 있어 reliability를 떨어뜨린다.
5.  #### Uniform Interface

    Component interface를 도입함으로써 전체적인 시스템 architecture가 단순해지고 interaction의 visibility도 높아졌다. Implemenation이 서비스를 주는 쪽과 decoupled 되면서 독립적인 발전이 가능해졌다. Trade-off는 uniform interface가 정보들이 표준화되어 이동하다 보니 효율성을 낮아졌다.

    REST는 Web의 흔한 case와 hypermedia data 전송에 효율적이나 다른 형태의 architectural interaction에 최적화된 것은 아니다. \
    \
    \#필딩제약 조건\
    a. Four Interface Constraints\
    &#x20;    i. URI 등으로 리소스를 식별할 수 있다.\
    &#x20;    ii. 표현으로 리소스를 조작한다.\
    &#x20;    iii. 메시지는 자기서술적이므로,  여러 레이어에서 처리 가능하다.\
    &#x20;         (자기서술적이라 함은 데이터를 스스로 설명하고 해석할 수 있는 능력을 의미)\
    &#x20;    iiii. HATEOAS\
    b. 아키텍처 요소(5.2)에서 리소스와 표현을 구분\
    &#x20;    i. 리소스는 추상적. 특정 시점의 스냅샷이 아니라, 모든 시간에 통용되는 엔티티 집합. 객체지향에서 말                        \
    &#x20;       하는 Entity라고 생각하면 편하다.\
    &#x20;    ii. 표현 → Data + Metadata + Meta-metadata… ⇒ 사실상 HTTP 메시지라고 보\
    &#x20;        면됨.  \
    c. URI 파트(6.2)에서 리소스에 대해 다시 강조\
    &#x20;    i. 리소스는 저장 객체가 아니다.\
    &#x20;    ii. 리소스, 표현, 실제 데이터 등은 전부 구분된다.\
    d. 아키텍처 데이터 뷰(5.3.3)에서 HATEOAS에 대해 언급.\
    &#x20;    i. 모델 애플리케이션이 현재 상태에서 다음 상태로 전이할 때 가능한 여러 가지 대안을 검토하고 선택\
    &#x20;       하는 엔진으로서 작동한다.(하이퍼미디어 링크)\
    &#x20;    ii. 대부분은 효율 문제로 표현에 링크를 넣지 않고, 클라이언트 개발자가 API 문서를 활용해 처리한다. \
    &#x20;        표현에서 상태 전환을 선택하는 게 아니라, API 문서를 참조해서 상태 전환을 강제하는 것\
    &#x20;    iii. 성숙한 REST라면 표현에 하이퍼미디어 컨트롤(링크)이 포함되어야 한다.\

6.  #### Layered System

    layered system style은 component들을 제한시켜(예를 들면 각 component는 자신과 소통하고 있는 layer의 너머를 보지 못한다) architecture을 구조적인 layer들로 이뤄지게 한다.

    한 layer의 knowledge를 제한시켜 전체적인 시스템의 복잡도를 제한시키고 독립성을 촉진시킨다.

    Layer는 legacy service들을 캡슐화시키고 새로운 서비스를 legacy client로부터 보호한다.

    또한 자주 사용되지 않는 기능을 공유되는 intermediary로 이동시켜 component들을 단순화 시킨다.

    Intermediary는 여러 네트워크와 프로세서들 사이에서 로브 밸런싱을 수행해 시스템 scalability를 높일 때 사용되기도 한다.

    &#x20;Layered system의 가장 큰 단점은 데이터를 처리할 때 오버헤드와 지연이 생겨 유저가 느끼는 performance를 떨어뜨릴 수 있다.

    Cache constraints을 지원하는 network-based system의 경우 intermediaries의 shared caching의 이득으로 이는 상쇄된다. organizational domain의 경계에 공유되는 cache를 놓는 것은 큰 performance 향상을 낳는다.

    &#x20;Layered system과 uniform interface constraints의 조합으로 architectural 속성들은 uniform pipe-and-filter style과 흡사해진다. REST interaction은 two-way 인데도도 불구하고, hypermedia interacion은 data-flow network처럼 처리된다. filter component들이 선택적으로 data stream에 적용을 함으로써 컨텐츠가 전달될 때 변환시킬 수 있기 때문이다.

    REST에서는 intermediary component들이 content들의 메시지를 actively하게 바꿀 수 있다. 왜냐하면 메시지들은 self-descriptive하고 의미가 intermediary에게 visible 하기 때문이다.
7.  #### Code-On-Demand

    REST는 client에게 코드(애플릿, 스크립트 형태)를 다운로드하고 실행할 수 있게 하였다.

    이로써 client는 수 많은 속성들을 미리 준비할 필요가 없어졌다. 그러나 이는 가시성을 감소시켜 REST에 선택적 제약이다.

## Reference

{% embed url="https://learn.microsoft.com/ko-kr/azure/architecture/guide/architecture-styles/" %}
