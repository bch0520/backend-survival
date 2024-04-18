# 🔸 12-1 CQRS

## CQS

* 정의 \
  상태를 바꾸지만 결과를 리턴하지 않는 Commend(void 메서드), 상태를 변경하지 않지만 결과값을 었는 Query. 이 둘을 분리하는 것이 CQS이다.\

* 왜 필요한가?\
  객체는 시간에 따라 변하는 상태를 갖는다.  하지만 상태가 언제 바뀔지 예측하기 힘들다면 프로그램을 사용하기 힘들어진다. 때문에 우리는 상태를 변경하지 않고 상태를 알 수 있게 해야하는데, 여기서 나온 개념이 메서드를 분리(Commend, Query분리)하는 것이다. \
  &#x20;
* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/12/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/12/textbook?programId=backend-10)

## CQRS

* 정의 \
  CQRS는 [CQS(Command and Query Separation)](https://en.wikipedia.org/wiki/Command%E2%80%93query\_separation) 원리에 기원한다. 사실 CQRS는 처음엔 CQS의 확장으로 얘기되었다. 하지만 CQS는 명령과 조회를 연산 수준에서 분리하는 반면 CQRS는 개체(object)나 시스템(혹은 하위 시스템) 수준에서 분리한다. 즉, CQRS는 아키텍처나 패턴에 해당하는 개념이고 CQS는 그보다 단순한 개념에 해당되는 느낌이다.\

* 왜 필요한가?\
  결국엔 복잡성을 없애거나 줄이기 위해 사용된다. Write Model과 Read Model을 구분하고, 애플리케이션의 상태가 바뀔 때마다(Command가 실행된 후 거의 바로) Read Model을 업데이트한다면 Command와 Query가 명확히 구분되고 트래픽 등이 비대칭적으로 발생하는 대부분의 서비스에서 도움이 된다.\

* 특징\
  1\. DDD와 같은 복잡한 도메인에서 잘 사용할 수 있다.\
  2\. 몇가지 복잡한 도메인을 더 쉽게 해결 할 수 있다.\
  3\. 고성능 애플리케이션을 처리할 수 있다. \
  4\. 읽기와 쓰기 사이에 큰 차이가 있는 경우 더 편리하게 적용할 수 있다.\

* 사용예시\
  아래 그림의 왼쪽부분은 CQRS를 적용하기 전이고, 오른쪽은 CQRS를 적용한 상태이다.\
  CQRS를 적용하지 않으면, 주문내역이나, 상품, 배송 등을 각각 별도의 API로 접근해야 하는데 이는 블로킹을 유발시키며, 각 서비스와 강한 커플링을 가져갈 수 있다. 하지만 조회 정보를 마이페이지의 한 화면으로 가져간다면 빠르게 데이터를 조회할 수 있고 과정을 단순화 시킬 수 있다.

<figure><img src="https://www.msaschool.io/assets/static/image2.eeac726.53fbf36d2d095e583b78993c3e3ee27f.png" alt="" width="563"><figcaption><p><a href="https://www.msaschool.io/operation/integration/integration-six/">https://www.msaschool.io/operation/integration/integration-six/</a></p></figcaption></figure>

* 레퍼런스 모음\
  [https://martinfowler.com/bliki/CQRS.html](https://martinfowler.com/bliki/CQRS.html)\
  [https://class.megaptera.kr/courses/backend-survival/lectures/12/intro?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/12/intro?programId=backend-10)\
  \*[https://www.msaschool.io/operation/integration/integration-six/](https://www.msaschool.io/operation/integration/integration-six/)

## SSOT(Single Source Of Truth)

* 정의 \
  [SSOT](https://en.wikipedia.org/wiki/Single\_source\_of\_truth)는 Single Source of Truth의 약어로, 데이터베이스, 애플리케이션, 프로세스 등의 모든 데이터에 대해 하나의 출처를 사용하는 개념을 의미한다. \

* 왜 필요한가?\
  &#x20;이는 데이터의 정확성, 일관성, 신뢰성을 보장하고, 일관성 있는 의사결정 및 작업 효율성을 높이는 데 도움을 준다.\

* 특징(장점)\
  1\) 정확성 : 데이터에 대한 일관성과 정확성을 유지하므로, 잘못된 데이터로 인한 잘못된 결정을 내리는 경우를 줄일 수 있다.\
  \
  2\) 일관성 : 모든 사용자가 동일한 정보를 사용하도록 보장하기 때문에, 업무 프로세스 및 의사결정에 일관성을 유지할 수 있습니다.\
  \
  3\) 효율성 : 모든 사용자가 동일한 정보를 사용하므로, 중복된 작업을 방지하고, 시간과 비용을 절약할 수 있습니다.\

* 구현방법\
  먼저 모든 데이터와 정보를 이해하고, 이를 표준화해야 한다. 이는 매우 중요한 단계로, 데이터의 표준화를 통해 일관성 있는 정보를 얻을 수 있고, 데이터의 정확성을 보장할 수 있다. 이를 위해 데이터의 유형과 속성을 분석하고, 중복되는 데이터를 제거하며, 데이터 표준화 규칙을 작성해야 한다.\
  \
  또한, 하나의 출처를 지정하고, 모든 데이터를 해당 출처에서 관리하도록 한다. 이는 데이터의 일관성을 유지하고, 중복된 작업을 방지하며, 데이터의 보안성을 높일 수 있다. 이를 위해 데이터의 출처를 식별하고, 데이터의 생성, 저장 및 유지 보수를 담당할 담당자를 지정해야 한다.\
  \
  데이터 변경 및 업데이트를 관리하기 위해서는 데이터 변경 규정을 작성하고, 데이터의 변경 이력을 관리해야 한다. 이를 통해 데이터 변경 과정에서 발생할 수 있는 문제를 최소화하고, 데이터의 신뢰성과 일관성을 유지할 수 있다.\
  \
  마지막으로, 모든 사용자가 동일한 데이터에 액세스할 수 있도록 데이터 액세스 권한을 설정해야 한다. 이를 위해 데이터 보안 규칙을 작성하고, 데이터의 액세스 권한을 지정해야 한다. 이를 통해 데이터의 무단 접근을 방지하고, 데이터의 보안성을 높일 수 있다.\
  &#x20;
* 레퍼런스 모음\
  [https://chancethecoder.tistory.com/45#recentComments](https://chancethecoder.tistory.com/45#recentComments)\


## Materialized View(구체화된 뷰)

* 정의 \
  테이블간(고객, 제품정보) 참조를 하지않고 관련 정보를 단일 임시 테이블에 저장하는 것을 구체화된 뷰라고 한다. 다르게 표현하면, 특정 쿼리의 결과를 미리 계산하고 데이터베이스의 물리적 테이블로 저장하는 데이터베이스 오브젝트이다. 구체화된 뷰에 인덱스 구초를 구조를 구축하여 데이터 읽기 성능을 향상시킬 수 있다. 참고로 적용하려면 RDBMS를 잘 알아야 한다.\

*   특징(장점)\
    1\) **속도**

    구체화된 뷰를 사용하면 매번 새 정보를 계산할 필요 없이 새 뷰에서 직접 데이터를 쿼리할 수 있다. 쿼리가 복잡할수록 구체화된 뷰를 사용하면 더 많은 시간을 절약할 수 있다.\


    #### **2) 데이터 스토리지 단순성**

    구체화된 뷰를 사용하면 복잡한 쿼리 로직을 단일 테이블에 통합할 수 있다. 이를 통해 개발자는 데이터 변환 및 코드 유지관리가 더 쉬워진다. 또한 복잡한 쿼리를 더 쉽게 관리할 수 있다. 데이터 서브셋을 사용하여 뷰에서 복제해야 하는 데이터의 양을 줄일 수도 있다.\


    #### **3) 일관성**

    구체화된 뷰는 특정 순간에 캡처된 데이터를 일관되게 보여줍니다. 구체화된 뷰에서 읽기 일관성을 구성하고 동시성 제어가 필수적인 다중 사용자 환경에서도 데이터에 액세스할 수 있도록 할 수 있다.

    또한 구체화된 뷰는 소스 데이터가 변경되거나 삭제되는 경우에도 데이터 액세스를 제공한다. 시간이 지남에 따라 구체화된 뷰를 사용하여 시간 기반 데이터 스냅샷에 대해 보고할 수 있습니다. 원본 테이블과의 격리 수준을 통해 데이터 전반에서 일관성을 높일 수 있다. \


    #### **4) 향상된 액세스 제어**

    구체화된 뷰를 사용하여 특정 데이터에 액세스할 수 있는 사용자를 제어할 수 있습니다. 원본 테이블에 대한 액세스 권한을 부여하지 않고도 사용자에 대한 정보를 필터링할 수 있습니다. 이 접근 방식은 누가 어떤 데이터에 액세스할 수 있고 얼마나 많은 데이터를 보고 상호 작용할 수 있는지를 제어하려는 경우에 유용합니다.\

*   사례\
    **필터링된 데이터 배포**

    원격 근무자와 같이 최근 데이터를 여러 위치에 배포해야 하는 경우 구체화된 뷰가 도움이 된다. 구체화된 뷰를 사용하여 여러 사이트에 데이터를 복제하고 배포한다. 데이터에 액세스해야 하는 사람들은 지리적으로 가장 가까운 복제 데이터 저장소와 상호 작용한다.

    이 시스템은 동시성을 허용하고 네트워크 부하를 줄인다. 읽기 전용 데이터베이스를 사용하는 효과적인 접근 방식이다.\


    #### **시계열 데이터 분석**

    구체화된 뷰는 타임스탬프가 지정된 데이터 세트 스냅샷을 제공하기 때문에 시간 경과에 따른 정보 변화를 모델링할 수 있다. 월별 또는 주별 요약과 같이 미리 계산된 데이터 집계를 저장할 수 있다. 이러한 용도는 비즈니스 인텔리전스 및 보고 플랫폼에 유용하다. \


    #### **원격 데이터 상호 작용**

    분산 데이터베이스 시스템에서는 구체화된 뷰를 사용하여 원격 서버의 데이터와 관련된 쿼리를 최적화할 수 있다. 원격 소스에서 반복적으로 데이터를 가져오는 대신 로컬 구체화된 뷰에서 데이터를 가져와 저장할 수 있다. 따라서 네트워크 통신의 필요성이 줄어들고 성능이 향상된다.

    예를 들어 외부 데이터베이스나 API를 통해 데이터를 받는 경우 구체화된 뷰가 데이터를 통합하여 처리하는 데 도움이 된다. \


    #### **주기적 배치 처리**

    구체화된 뷰는 주기적인 배치 처리가 필요한 상황에 유용하다. 예를 들어, 금융 기관은 구체화된 뷰를 사용하여 당일 잔액과 이자 계산을 저장할 수 있다. 또는 포트폴리오 성과 요약을 저장하여 각 영업일이 끝날 때 새로 고칠 수도 있다.\

* 레퍼런스 모음\
  [https://aws.amazon.com/ko/what-is/materialized-view/](https://aws.amazon.com/ko/what-is/materialized-view/)

## OLTP(Online Transaction Processing)

* 정의 \
  OLTP(온라인 트랜잭션 처리)는 온라인 뱅킹, 쇼핑, 주문 입력 또는 텍스트 메시지 전송 등 동시에 발생하는 다수의 트랜잭션을 실행하는 데이터 처리 유형이다. 이러한 트랜잭션은 전통적으로 경제 또는 재무 트랜잭션이라고 칭하며, 기업이 회계 또는 보고 목적으로 언제든 정보에 액세스할 수 있도록 기록 및 보호된다.\

* 왜 필요한가?\

* 특징\
  1\)  다수의 사용자에 의한 대량의 데이터베이스 트랜잭션을 실시간으로 실행할 수 있도록 지원\
  2\) 빛의 속도에 가까운 빠른 응답시간 필요\
  3\) 적은 양의 데이터를 자주 수정하고, 일반적으로 읽기 및 쓰기 작업 간 균형이 유지됨\
  4\) 인덱스화된 데이터를 사용해 응답 시간 개선\
  5\) 데이터베이스에 대한 빈번한 또는 동시 백업 필요\
  6\) 상대적으로 적은 스토리지 공간 필요\
  7\) 일반적으로 하나 또는 몇 개의 레코드를 포함하는 단순한 쿼리 실행 \

* 사용예시\
  &#x20;
* 레퍼런스 모음\
  [https://www.oracle.com/kr/database/what-is-oltp/](https://www.oracle.com/kr/database/what-is-oltp/)

## OLAP(Online Analytical Processing)

* 정의 \
  온라인 분석 처리(Online Analytical Processing, OLAP)는 의사결정 지원 시스템 가운데 대표적인 예로, 사용자가 동일한 데이터를 여러 기준을 이용하는 다양한 방식으로 바라보면서 다차원 데이터 분석을 할 수 있도록 도와준다.
* 왜 필요한가?\

* 특징\
  1\) 일반적으로 분석을 목적으로 데이터베이스 내 다수의 레코드(또는 모든 레코드)에 대한 질의 작업 포함\
  2\) OLTP에 대비 훨씬 느린 응답시간 필요\
  3\) 데이터를 전혀 수정하지 않음. 일반적으로 읽기 집약적인 작업\
  4\) 대량의 레코드에 손쉽게 액세스할 수 있도록 컬럼 형식으로 데이터 저장\
  5\) 훨씬 적은 빈도의 데이터베이스 백업 필요\
  6\) 대량의 기록 데이터를 저장하기 때문에 일반적으로 상당한 양의 스토리지 공간 필요\
  7\) 다수의 레코드를 포함하는 복잡한 쿼리 실행\

* 사용예시\
  &#x20;
* 레퍼런스 모음\
  [https://ko.wikipedia.org/wiki/%EC%98%A8%EB%9D%BC%EC%9D%B8\_%EB%B6%84%EC%84%9D\_%EC%B2%98%EB%A6%AC](https://ko.wikipedia.org/wiki/%EC%98%A8%EB%9D%BC%EC%9D%B8\_%EB%B6%84%EC%84%9D\_%EC%B2%98%EB%A6%AC)\
  [https://www.oracle.com/kr/database/what-is-oltp/#link1](https://www.oracle.com/kr/database/what-is-oltp/#link1)\


## Event Sourcing

* 정의 \
  이벤트 소싱이란 application의 모든 상태를 일으키는 이벤트를 순서에 맞게 저장하여 status를 만들어내는 방법이다. 일반적인 경우엔 필요하지 않고, 특정한 경우에만 적용하면 좋다.

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbF2oCK%2FbtrKdQ7nfTI%2FUJumUEpHkkUd7hZvF0kZGk%2Fimg.png" alt="" width="563"><figcaption></figcaption></figure>

* 왜 필요한가?\
  이벤트 소싱은 현재의 상태값 뿐만아니라 이전에 일어났던 상태값들을 모두 알 수 있기 때문에 지금에 상태값이 왜 나왔는지 이유와 과정을 설명해 줄 수 있다.\

* 특징(장/단점)\
  \[장점]\
  1\) History : 모든 상태 변화가 기록하기때문에 이는 Application과의 상호작용(interaction) 로그(History)로써 활용\
  2\) Complete Rebuild : Object의 Event Sourcing를 처음부터 replay하면 현재 상태로 완벽하게 재현 가능\
  3\) Temporal Query : 현재 상태 뿐만 아니라 Object의 특정 시점으로 replay 가능\
  4\) Event Replay : 만약 비즈니스 로직이 잘못되어있어서 문제가 발생했다면 비즈니스 수정 후 Event를 reversing & replay하여 정상화 가능\
  5\) 애자일 방식으로 개발을 진행할 때 기존 event 데이터를 통해서 로직이 정상인지 검증 가능\
  6\) Admin 시스템 등이라면 full audit 기능이 필요하며 이 기능의 log로 활용 가능\
  7\) 경우에 따라 Write( Create / Update / Delete ) Operation의 속도의 상승으로 지연시간 최소화 ( Event를 저장 후 이후 후처리를 하는 방식 채택을 통해 )\
  \
  \[단점]\
  1\) 현재 정확한 정보를 얻기 위해서는 Event Soucring의 Event 데이터를 replay 해야하므로 read 성능 약화\
  2\) 대부분 Eventually Consistency를 기본으로 하기 때문에 유저의 write 성공한다고 바로 유저가 최신 정보를 얻을 수 없을 수 있음\
  3\) 기존 모델에 비해서 상대적으로 데이터 저장을 더 많이 하기 때문에 대용량 데이터 처리에 대한 고민이 필요\
  4\) write에 대한 고민이 줄어드는 대신 read에 대한 고민이 늘어남(어떻게 유저에게 빠르게 보여줄수 있을지, 또는 read모델과 write모델이 다르기때문에 오는 불일치에 따른 CQRS 고민)\

* CQRS와 이벤트 소싱의 관계\
  Event Sourcing은 read 모델과 write 모델이 다르기 때문에 CQRS의 장점과 단점을 그대로 가질 수 밖에 없다. 즉, Event Sourcing은 CQRS가 없이는 이루어 질 수 없다고 보는게 맞는것 같다.\

* 사용예시

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F7Kr00%2FbtrKhQ6B3Cm%2FDaUkHS39KNgDGLmY4IrQC1%2Fimg.png" alt="" width="563"><figcaption></figcaption></figure>

* 레퍼런스 모음\
  [https://sabarada.tistory.com/231](https://sabarada.tistory.com/231)
