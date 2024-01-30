# 🔸 2-2 URI & MIME TYPE

## URI / URL / URN

URI는 리소스를 식별하는 방법이다.

URI는 크게 둘로 나뉜다.

1. URL : 리소스의 위치. 위치변경에 취약함 ex) http://www.example.com...
2. URN : 리소스의 유니크한 이름. 사실상 쓰이지 않음. ex) urn : isbn97801303

사실상 URI와 URL은 같은 의미로 쓰인다.

## MIME TYPE(Content Type)

Content의 종류를 표현. `<type>/<subtype>`의 형태로 쓴다. HTTP Headers에 `Content-Type` 속성으로 전달함. [IANA](https://www.iana.org/assignments/media-types/media-types.xhtml)에 등록된 목록을 참고하자.

1. `text/plain` ⇒ E-mail에서 자주 사용.
2. `text/html` ⇒ 일반적인 웹 문서. HTML 문서.
3. `text/css`
4. `text/javascript`
5. `application/xml` ⇒ 범용. 자기서술적이기 상대적으로 어렵다.
6. `application/atom+xml`
7. `application/json` ⇒ 범용. 자기서술적이기 굉장히 어렵다.
8. `application/dns+json`

