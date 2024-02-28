# 🔸 5-2 Unit Test

JUnit 테스트 픽스처 예시JUnit 테스트 픽스처 예시자바 텍스트 자ㅂ더ㅏV 모델

* 정의 \
  V 모델(V-model)은 [소프트웨어 개발 프로세스](https://ko.wikipedia.org/wiki/%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4\_%EA%B0%9C%EB%B0%9C\_%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4)로 [폭포수 모델](https://ko.wikipedia.org/wiki/%ED%8F%AD%ED%8F%AC%EC%88%98\_%EB%AA%A8%EB%8D%B8)의 확장된 형태 중 하나로 볼 수 있으며 문제 해결 프로세스이다. 아래 방향으로 선형적으로 내려가면서 진행되는 [폭포수 모델](https://ko.wikipedia.org/wiki/%ED%8F%AD%ED%8F%AC%EC%88%98\_%EB%AA%A8%EB%8D%B8)과 달리, 이 프로세스는 코딩 단계에서 위쪽으로 꺾여서 알파벳 V자 모양으로 진행된다. V 모델은 개발 생명주기의 각 단계와 그에 상응하는 [소프트웨어 시험](https://ko.wikipedia.org/wiki/%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4\_%EC%8B%9C%ED%97%98) 각 단계의 관계를 보여준다.
* 왜 필요한가?\
  V 모델은 소프트웨어 개발의 각 단계마다 상세한 문서화를 통해 작업을 진행하는 잘 짜인 방법을 사용한다. 또한 테스트 설계와 같은 테스트 활동을 코딩 이후가 아닌 프로젝트 시작 시에 함께 시작하여, 전체적으로 많은 양의 프로젝트 비용과 시간을 감소시킨다.
*   적용방법

    1. 요구사항 분석 → 사용자 중심 ⇒ 인수 테스트
    2. 시스템 설계 → 시스템 사양 결정 ⇒ 시스템 테스트
    3. 아키텍처 설계 → 고수준 설계 ⇒ 통합 테스트
    4. 모듈 설계 → 저수준 설계 ⇒ 단위 테스트
    5. 구현 → 코딩



    <figure><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/96/V-model.JPG/700px-V-model.JPG" alt="" width="375"><figcaption><p>V 모델 개발 프로세스</p></figcaption></figure>
* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://ko.wikipedia.org/wiki/V\_%EB%AA%A8%EB%8D%B8](https://ko.wikipedia.org/wiki/V\_%EB%AA%A8%EB%8D%B8)

## Test Matrix

* 정의 \
  Test Matrix는 다양한 테스트 시나리오와 그에 해당하는 테스트 모듈을 나타내는 매트릭스이다.
* 왜 필요한가?\
  스프링 애플리케이션을 다양한 방법으로 체계적으로 테스트 할 수 있다.\

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음

## 내적 품질(테스트 코드 작성)을 높이면 좋은 이유

1. 신뢰성 향상 - 테스트 코드는 소프트 웨어의 동작을 확인하고 검증하는 데 사용한다. 내적 품질이 높은 테스트 코드는 소프트 웨어가 예상대로 작동하는지 확인할 수 있어서 신뢰성이 향상된다.
2. 유지보수성 향상 &#x20;
3. 디버깅 및 문제해결 용이성 향상
4. 코드 설계 개선
5. 프로덕션 코드 품질 향상
6. 개발 생산성 향상

## J 유닛

* 정의 \
  [자바 프로그래밍 언어](https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94\_\(%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D\_%EC%96%B8%EC%96%B4\))용 [유닛 테스트](https://ko.wikipedia.org/wiki/%EC%9C%A0%EB%8B%9B\_%ED%85%8C%EC%8A%A4%ED%8A%B8) [프레임워크](https://ko.wikipedia.org/wiki/%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4\_%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC)이다. JUnit은 [테스트 주도 개발](https://ko.wikipedia.org/wiki/%ED%85%8C%EC%8A%A4%ED%8A%B8\_%EC%A3%BC%EB%8F%84\_%EA%B0%9C%EB%B0%9C) 면에서 중요하며 [SUnit](https://ko.wikipedia.org/w/index.php?title=SUnit\&action=edit\&redlink=1)과 함께 시작된 [XUnit](https://ko.wikipedia.org/wiki/XUnit)이라는 이름의 [유닛 테스트](https://ko.wikipedia.org/wiki/%EC%9C%A0%EB%8B%9B\_%ED%85%8C%EC%8A%A4%ED%8A%B8) 프레임워크 계열의 하나이다. \
  자동화된 테스트를 지원하는 도구이며, 이름에 Unit이 들어가지만 단위 테스트만 지원하는 건 아님. 통합 테스트, 심지어는 E2E 테스트를 작성하는데도 사용한다.
* 특징\
  1\) 단정 메서드(assert)로 테스트 케이스 수행결과를 판별\
  2\) Junit 4부터는 테스트 어노테이션을 제공\
  3\) 각 테스트 어노테이션 호출시 새로운 인스턴스를 생성하여 독립적인 테스트가 이루어 지도록 함.\

* 사용예시

<figure><img src="../.gitbook/assets/스크린샷 2024-02-28 오후 5.14.38.png" alt="" width="375"><figcaption><p>JUnit 테스트 픽스처 예시</p></figcaption></figure>

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://ko.wikipedia.org/wiki/JUnit](https://ko.wikipedia.org/wiki/JUnit)

## 단위 테스트

* 정의 \
  응용프로그램에서 테스트 가능한 가장 작은 소프트웨어를 실행하여 예상대로 동작하는지 확인하는 테스트. 일반적으로 클래스나 메서드 단위에서 테스트 대상 단위를 정한다. 단위 테스트는 해당 부분만 독립적으로 테스트 하기 때문에 리펙토링을 하게 되는 경우에도 문제를 빠르게 파악 할 수 있다.
* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음

## E2E 테스트

* 정의 \
  End to End 테스트. 테스트하고자 하는 기능에서 필요로하는 모든 컴포턴트들이 올바르게 협업해서 최종적으로 원하는 결과를 내는지 확인하는 테스트.\

* 사용예시\
  아래와 같이 아키텍쳐가 나누어진 서비스에서, E2E 검증을 위해 컨트롤러, 서비스, 레파지토리를 모두 사용한다고 하면 모든 컴포넌트들의 협업을 검증한 것이므로 E2E 테스트라고 부를 수 있다.

<figure><img src="https://amaran-th.github.io/static/c7f3bad0885078e96f678409056fa976/78612/e2e.png" alt="" width="563"><figcaption></figcaption></figure>

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://amaran-th.github.io/Spring/\[Spring\]%20Test/](https://amaran-th.github.io/Spring/\[Spring]%20Test/)
