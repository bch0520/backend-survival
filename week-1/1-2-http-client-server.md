# 🔸 1-2 HTTP Client / Server

## TCP/IP 통신

인터넷 프로토콜 스위트는 인터넷에서 컴퓨터들이 서로 정보를 주고받는데 쓰이는 통신규약(프로토콜)의 모음이다. 인터넷 프로토콜 스위트 중 TCP와 IP가 가장 많이 쓰이기 때문에 TCP/IP  프로토콜이라고도 불린다.

TCP/IP를 사용하겠다는 것은 IP 주소체계를 따르고 IP 라우팅을 이용해 목적지에 도달하며, TCP의 특성을 활용해 송신자와 수신자의 논리적 연결을 생성하고 신뢰성을 유지할 수 있도록 하는 것이다. 즉 TCP/IP를 말한다는 것은 송신자가 수신자에게 IP주소를 사용하여 데이터를 전송하고, 너무 빠르지는 않은지, 제대로 전송됐는지, 제대로 전달받았다고 연락은 오는지 등을 이야기 하는것이라고 할 수 있다.

## TCP vs UDP

TCP는 연속성보다 신뢰성 있는 전송이 중요할 때 사용되는 프로토콜이며, UDP는 TCP보다 빠르고 네트워크 부하가 적다는 장점이 있지만, 신뢰성 있는 데이터 전송을 보장하지는 않는다. 그렇기 때문에 신뢰성보다는 연속성이 중요한 실시간 스트리밍과 같은 서비스에 자주 사용된다.



<div align="left">

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fx7IGo%2FbtrsW8REhYz%2FjlnTXXNDAb4S6Qg4QCxwDk%2Fimg.png" alt="" width="375"><figcaption><p>TCP (<a href="https://dev-coco.tistory.com/144#head3">https://dev-coco.tistory.com/144#head3</a>)</p></figcaption></figure>

 

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F2ndZ1%2FbtrsW9bZXKB%2FOSV6HaJn7hTxO3eBKXSOV1%2Fimg.png" alt="" width="375"><figcaption><p>UDP (<a href="https://dev-coco.tistory.com/144#head3">https://dev-coco.tistory.com/144#head3</a>)</p></figcaption></figure>

</div>

<figure><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FKTqtjyDTEKUU15PgTVZb%2Fuploads%2Fj4jK3hzlkubY1waqLJwy%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202024-01-26%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.48.22.png?alt=media&#x26;token=141f5cf3-a27f-468e-9362-57e6f3ddce26" alt=""><figcaption><p><a href="https://dev-coco.tistory.com/144#head3">https://dev-coco.tistory.com/144#head3</a></p></figcaption></figure>

## ServerSocket

ServerSocket의 클래스는 서버 프로그램을 구현하는데 사용된다. 일반적인 통신 순서는 다음과 같다.

1. 서버는 접속을 받기 위한 소켓을 연다.(Listen)
2. 클라이언트는 소켓을 만들고, 서버에 접속을 요청한다.(Connect)
3. 서버는 접속 요청을 받아서, 클라이언트와 통신할 소켓을 따로 만든다.(Accept)
4. 소켓을 통해 서로 데이터를 주고 받는다.(Send & Receive -> 반복)
5. 통신을 마치며 소켓을 닫는다.(Close)

## Blocking vs nonBlocking(feat. 동기 vs 비동기)

#### blocking/non-blocking <a href="#blockingnon-blocking" id="blockingnon-blocking"></a>

> 이 그룹은 호출되는 함수가 **바로 return하느냐 마느냐**가 관심사이다.

호출된 함수가 **바로 return해서 호출한 함수에게 제어권을 넘겨주고**\
**호출한 함수가 다른 일을 할 수 있는 기회**를 줄 수 있으면 non-blocking이다.

호출된 함수가 **자신의 작업을 모두 마칠 때까지**\
호출한 함수에게 **제어권을 넘겨주지 않고 대기**하게 만든다면 blocking이다.

#### 동기/비동기 <a href="#undefined" id="undefined"></a>

> 이 그룹은 호출되는 함수의 **작업 완료 여부를 누가 신경쓰느냐**가 관심사이다.

호출되는 함수에게 **callback**을 전달해서 호출되는 함수의 작업이 완료되면\
호출되는 함수가 전달받은 callback을 실행하고, **호출한 함수는 작업 완료 여부를 신경쓰지 않는다면** 비동기이다.

호출하는 함수가 호출되는 함수의 작업 완료 후 **return을 기다리거나**\
호출되는 함수로부터 바로 return 받더라도 **작업 완료 여부를 호출한 함수 스스로 확인**하며 신경 쓴다면 동기이다.

## Reference

{% embed url="https://dev-coco.tistory.com/144#head3" %}



