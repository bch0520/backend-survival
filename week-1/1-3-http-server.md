# 🔸 1-3 HTTP Server

## Java ServerSocket

SeverSocket 클래스는 서버 프로그램을 구현하는데 사용된다.

1. 서버는 접속 요청을 받기 위한 소켓을 연다. → Listen
2. 클라이언트는 소켓을 만들고, 서버에 접속을 요청한다. → Connect
3. 서버는 접속 요청을 받아서 클라이언트와 통신할 소켓을 따로 만든다. → Accept
4. 소켓을 통해 서로 데이터를 주고 받는다. → Send & Receive ⇒ 반복!
5. 통신을 마치면 소켓을 닫는다. → Close ⇒ 상대방은 Receive로 인지할 수 있다.

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
