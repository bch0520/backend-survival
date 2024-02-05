# 🔸 1-1 HTTP의 이해

## HTTP 란?

HTTP는 HyperText Transfer Protocol의 줄임말로, HTTP는 네트워크 장치 간에 정보를 전송하도록 설계된 애플리케이션 계층이며, HTML 문서와 같은 리소스들을 가져올 수 있도록 해주는 프로토콜이다.

#### #특징

* 클라이언트가 서버에 **요청**을 보내면, 서버가 요청에 대한 **응답**을 보내는 **클라이언트-서버 구조**로 이루어져 있다.
* HTTP에서는 서버가 **클라이언트의 상태를 보존하지 않는다(무상태성)**. 따라서 응답과 요청이 독립적이다.
* **비연결성**을 가지는 HTTP는 실제로 요청을 주고받을 때만 연결을 유지하고 **응답을 주고 나면 TCP/IP 연결을 끊는다**.

## HTTP vs HTTPS

HTTP에서 보안 기능을 추가한 것이 HTTPS라고 생각하면 된다. 즉, 암호화를 위해 SSL/TLS 인증서를 사용한 확장 프로토콜이다.

## 클라이언트-서버 모델

클라이언트 서버 모델은 클라이언트가 요청을 전송하고 서버가 응답을 하는 상호작용 모델이다.

## Stateless vs Stateful

위에서 언급했듯이, stateless(무상태성)는 서버가 클라이언트의 상태를 보존하지 않는 다는 뜻이다. 모든 상태 정보들은 클라이언트가 보유 및 관리하며 서버와 통신할 때 데이터를 실어보내는 것이 무상태 구조이다. HTTP와 UDP가 이에 해당한다. 쿠키가 이에 해당한다.

반대로 stateful(상태유지)은 서버가 클라이언트 상태를 보존한다. 이에 대한 예로는 세션을 들 수 있다.\


<figure><img src="../.gitbook/assets/스크린샷 2024-01-26 오후 2.46.56.png" alt=""><figcaption><p><a href="https://inpa.tistory.com/entry/WEB-%F0%9F%93%9A-Stateful-Stateless-%EC%A0%95%EB%A6%AC">https://inpa.tistory.com/entry/WEB-%F0%9F%93%9A-Stateful-Stateless-%EC%A0%95%EB%A6%AC</a>(무상태성)</p></figcaption></figure>

## Cookie vs Session

쿠키는 클라이언트에 저장되는 키와 값이 있는 작은 데이터 파일이다. 이러한 쿠키는 클라이언트에 저장되어 필요시 정보를 참조하거나 재사용할 수 있다.&#x20;

반면, 세션은  일정기간 동안 같은 사용자에게 들어오는 데이터를 하나의 상태로 보고 그 상태를 일정하게 유지시킨다. 세션은 서버에서 데이터를 저장하고 관리한다.

쿠키와 세션의 차이점은 다음과 같다.

1. 쿠키는 클라이언트에 저장되지만, 세션은 서버에 저장된다.
2. 서버에 요청을 보내는 사용자가 많은 경우 세션은 부하가 심하지만 쿠키는 그렇지 않다.
3. 쿠키는 만료시간 동안 파일로 저장되므로 브라우저를 종료해도 정보가 남아있고, 세션은 브라우저가 종료되면 만료시간에 상관없이 삭제된다.
4. 보안면에서 세션이 더 우수하다. 그 이유는 세션은 쿠키를 이용해 세션 Id만 저장하고 서버에서 세션을 처리하기 때문이다. 반면 쿠키는 사용자의 민감 정보를 그대로 담아 요청을 보내게 된다면 중간에 정보를 해킹당 할 수도 있다.

## MIME에서의 multipart/form-data

#### multipart 메세지

* 서로 붙어있는 여러 개의 메세지를 포함하여 하나의 복합 메세지로 보내진다.
* MIME multipart 메세지는 “Content-type:” 헤더에 boundary 파라미터를 포함한다.
* boundary는 메세지 파트를 구분하는 역할을 하며, 메세지의 시작과 끝 부분도 나타납니다.

#### multipatr form 제출

* HTTP form을 채워서 제출하면, 가변 길이 텍스트 필드와 업로드 될 객체는 각각 멀티파트 본문을 구성하는 하나의 파트가 되어 보내집니다. 멀티 파트 분몬은 여러 다른 종류와 길이의 값으로 채워진 form을 허용한다.
* multipart/form-data: 사용자가 양식을 작성한 결과 값의 집합을 번들로 만드는데 사용한다.

<figure><img src="https://user-images.githubusercontent.com/45350356/181057825-d9dd352b-0c0c-4ab0-9ecb-59b1e0a4672f.png" alt=""><figcaption><p>서버에 multipart/form-data로 데이터를 보낼때의 request header와 body의 이미지<br>(<a href="https://bradheo.tistory.com/entry/HTTP-multipartform-data">https://bradheo.tistory.com/entry/HTTP-multipartform-data</a>)</p></figcaption></figure>

## 멱등성

데이터를 보낼 때 한 번 보낸 것과 여러 번 보낸  것의 결과값이 같을 때 멱등성이 있다고 말한다. 멱등성의 기준은 '**상태코드'가 아니라 '서버에 미치는 의도된 영향이 동일한가?'** 이다. GET, PUT, DELETE는 멱등성이 있지만 POST, PATCH는 멱등성이 없다. PATCH 메소드가 멱등하다고 생각할 수 있는데, 예를들어 수정한 값을 계속 입력하면 똑같은 값만 계속나온다. 하지만 PATCH는 값을 추가할 때도 사용되어, 값을 여러번 입력하면 그 값이 계속 쌓이는 경우도 있기 때문이다.



## HTTP 상태코드 3XX - 리다이렉션

3XX 상태 코드들은 리다이렉션을 의미하며, 이것은 요청을 완료하려면 추가적인 작업이 필요함을 의미한다.\
클라이언트가 관심있어 하는 리소스에 대한 다른 위치를 사용하라고 하거나  그 리소스 대신 다른 응답을 제공한다.

<figure><img src="../.gitbook/assets/스크린샷 2024-02-05 오후 6.59.18.png" alt=""><figcaption><p><a href="https://inpa.tistory.com/entry/HTTP-%F0%9F%8C%90-3XX-Redirection-%EC%83%81%ED%83%9C-%EC%BD%94%EB%93%9C-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0#3xx_redirection">https://inpa.tistory.com/entry/HTTP-%F0%9F%8C%90-3XX-Redirection-%EC%83%81%ED%83%9C-%EC%BD%94%EB%93%9C-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0#3xx_redirection</a></p></figcaption></figure>

리다이렉션은 크게 3가지로 나눌 수 있다.

1. 영구 리다이렉션 : 특정 리소스의 URL이 영구적으로 이동 ex) 301, 308
2. 일시 리다이렉션 : 특정 리소스의 URL이 일시적으로 이동 ex) 302, 303, 307
3. 특수 리다이렉션 : 캐시를 활용할 것인지에 대한 여부 ex) 304,

## Reference

{% embed url="https://inpa.tistory.com/entry/WEB-%F0%9F%93%9A-Stateful-Stateless-%EC%A0%95%EB%A6%AC" %}

{% embed url="https://bradheo.tistory.com/entry/HTTP-multipartform-data" %}

{% embed url="https://inpa.tistory.com/entry/HTTP-%F0%9F%8C%90-3XX-Redirection-%EC%83%81%ED%83%9C-%EC%BD%94%EB%93%9C-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0#3xx_redirection" %}
