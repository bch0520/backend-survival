# 🔸 1-2 HTTP Client

## TCP/IP 통신

인터넷 프로토콜 스위트는 인터넷에서 컴퓨터들이 서로 정보를 주고받는데 쓰이는 통신규약(프로토콜)의 모음이다. 인터넷 프로토콜 스위트 중 TCP와 IP가 가장 많이 쓰이기 때문에 TCP/IP  프로토콜이라고도 불린다.

TCP/IP를 사용하겠다는 것은 IP 주소체계를 따르고 IP 라우팅을 이용해 목적지에 도달하며, TCP의 특성을 활용해 송신자와 수신자의 논리적 연결을 생성하고 신뢰성을 유지할 수 있도록 하는 것이다. 즉 TCP/IP를 말한다는 것은 송신자가 수신자에게 IP주소를 사용하여 데이터를 전송하고, 너무 빠르지는 않은지, 제대로 전송됐는지, 제대로 전달받았다고 연락은 오는지 등을 이야기 하는것이라고 할 수 있다.

## TCP vs UDP

TCP는 연결이 필요하고, 전송과 전달 순서가 중요할 때 사용되는 프로토콜로 전화에 비유할 수 있다. 반면 UDP는  연결이 필요없고 전달 순서가 보장되지 않기 때문에 편지에 비유 될 수 있다. 그렇기 때문에 신뢰성보다는 연속성이 중요한 실시간 스트리밍과 같은 서비스에 자주 사용된다.



<div align="left">

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fx7IGo%2FbtrsW8REhYz%2FjlnTXXNDAb4S6Qg4QCxwDk%2Fimg.png" alt="" width="375"><figcaption><p>TCP (<a href="https://dev-coco.tistory.com/144#head3">https://dev-coco.tistory.com/144#head3</a>)</p></figcaption></figure>

 

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F2ndZ1%2FbtrsW9bZXKB%2FOSV6HaJn7hTxO3eBKXSOV1%2Fimg.png" alt="" width="375"><figcaption><p>UDP (<a href="https://dev-coco.tistory.com/144#head3">https://dev-coco.tistory.com/144#head3</a>)</p></figcaption></figure>

</div>

<figure><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FKTqtjyDTEKUU15PgTVZb%2Fuploads%2Fj4jK3hzlkubY1waqLJwy%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202024-01-26%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.48.22.png?alt=media&#x26;token=141f5cf3-a27f-468e-9362-57e6f3ddce26" alt=""><figcaption><p><a href="https://dev-coco.tistory.com/144#head3">https://dev-coco.tistory.com/144#head3</a></p></figcaption></figure>

## Socket vs Socket API

소켓은 네트워크 상에서 돌아가는  두 개의 프로그램 간 양방향 통신의 하나의 엔드포인트이다.\
소켓은 포트번호에 바인딩 되어 TCP 레이어(TCP/IP 4계층)에서 데이터가 전달되어야 하는 애플리케이션을 식별 할 수 있게 한다. 소켓은 파일과 유사하게 다룰 수 있다.

반면, 소켓 API는 TCP/IP에 대한 네트워크 표준입니다. 다양한 오퍼레이팅 시스템이 소켓 API를 지원한다.

## 호스트

#### IP주소 - 인터넷 상의 모든 컴퓨터가 가지고 있는 숫자로 된 고유한 주소이다. ex) 127.0.0.1

도메인명- 우리에게 가장 익숙한 문자와 숫자로 조합되어 있는 주소이다. ex) naver.com

DNS - Domain Name System의 약자로 ip주소 체계를 도메인명으로 바꾸거나 반대의 경우를 수행할 수 있도록 고안된 데이터베이스 시스템이다.

## 포트

포트는 논리적인 접속 장소를 뜻하며, 인터넷 프로토콜인 TCP/IP를 사용할 때, 클라이언트 프로그램이 네트워크상의 특정 서버 프로그램을 지정하는 방법으로 사용한다. Ip주소 뒤에 :(콜론)표시를 하여 표기한다.

ex) 127.0.0.1 **: 8080**

## URI-path

웹 서버에 지정한 루트 디렉토리부터 시작하여, 웹 페이지, 이미지, 동영상 등이 위치한 경로와 파일명을 나타낸다.

<figure><img src="https://media.vlpt.us/images/jch9537/post/88b0c8ac-5870-4cbc-b613-7dd39f510f31/image.png" alt=""><figcaption><p><a href="https://velog.io/@chayezo/TIL-29-HTTP-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B8%B0%EC%B4%88-3.-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%9D%98-%EC%9E%91%EB%8F%99-%EC%9B%90%EB%A6%AC-%EB%B3%B4%EC%9D%B4%EC%A7%80-%EC%95%8A%EB%8A%94-%EA%B3%B3">https://velog.io/@chayezo/TIL-29-HTTP-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B8%B0%EC%B4%88-3.-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%9D%98-%EC%9E%91%EB%8F%99-%EC%9B%90%EB%A6%AC-%EB%B3%B4%EC%9D%B4%EC%A7%80-%EC%95%8A%EB%8A%94-%EA%B3%B3</a></p></figcaption></figure>



## Java text blocks(자바문법)

html을 그대로 반환해주어야 하는 상황이거나 혹은 string을 여러 줄 작성해야 할 때 사용가능한 기술이다.\
텍스트 블록은 큰따옴표 3개로 열고 닫으면 되고 그 안에 원하는 텍스를 작성하면 된다. 큰 따옴표 안의 공백들을 제거해주기 때문에 여러줄의 텍스트를 한번에 출력해 낼 수 있다.\


## Java InputStream/OutputStream(자바문법)

프로그램이 외부에서 데이터를 읽거나 외부로 데이터를 출력하는 작업을 빈번하게 하는데,\
이때 데이터가 이동하면서 통로 역할을 하는 것이 Stream이다.\
자바는 이러한 기능을 수행하기 위해 InputStream과 OutputStream이 필요하며, 이는 단일방향으로 흘러간다. InputSteam은 데이터를 읽는 역할이며, OutputStream은 데이터를 출력하는 역할이다. \
둘다 추상클래스이며 추상메서드를 오버라이딩해서 다양한 역할을 수행 할 수 있다.



## Java try-with-resources(자바문법)

원래는 try-catch-finally를 사용했으나, 자원을 반납하지 못하는 오류가 종종 있다.\
그래서 자원을 다 사용 한 후에 자동으로 반납해주는 기능을 만들었는데 그것이 try-with-resources이다.\
원래는 finally 이후에 반납을 하는 코드가 있었으나, 자동으로 반납해주기 때문에 해당 코드가 없는 것이 특징이다.

## Reference

{% embed url="https://dev-coco.tistory.com/144#head3" %}

{% embed url="https://velog.io/@chayezo/TIL-29-HTTP-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B8%B0%EC%B4%88-3.-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%9D%98-%EC%9E%91%EB%8F%99-%EC%9B%90%EB%A6%AC-%EB%B3%B4%EC%9D%B4%EC%A7%80-%EC%95%8A%EB%8A%94-%EA%B3%B3" %}

