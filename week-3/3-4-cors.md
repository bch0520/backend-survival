# 🔸 3-4 CORS

## CORS(Cross Origin Resource Sharing)란?

서로 다른 출처(FE/BE)의 리소스를 공유할 때 알려주는 정책이다.  백엔드 응답 헤더에\
"Access-Control-Allow-Origin"을 포함시켜주면, 서버쪽에서 "이 FE에서 요청한 건 괜찮아요"라는 의미라서 해결된다.

#### 동일출처정책

출처가 동일한 경우에만 리소스를 공유할 수 있게 제한하는 정책.



JSONP

CORS 이전에 사용되었던 방식으로, 클라이언트에서 데이터를 요청하는게 아닌 다른 도메인의 서버에서 데이터 비동기 요청을 하던 방식이다. 이것은 자바스크립트에서 script 태그는 동일 출처를 따지지 않는다는 점을 이용했으며 지정해뒀던 콜백함수를 포함시켜주면 된다. 콜백함수를 포함시키는 이유는 직접 JSON 데이터를 삽입하면 중괄호 때문에 문법오류가 발생하기 때문이다. 이 방식은 프론트에서 별도로 추가를 하는 방식인것 같고, CORS가 도입되면서 보안상에 문제로 백엔드에서 교차출처를 허용해주는 방식으로 바뀐듯 하다.

ex) \
\<script type="application/javascript"

src="http://server.example.com/Users/1234?callback=parseResponse">

\</script>                                       출처 : [https://ko.wikipedia.org/wiki/JSONP](https://ko.wikipedia.org/wiki/JSONP)

####

#### Access-Control-Allow-Origin

이 문구는 브라우저 리소스에 접근하는 임의의 origin으로부터의 요청을 허용한다는 의미.

## @CrossOrigin

CORS를 해결하는 방법중에 하나로 컨트롤러, 메서드 상단에 이 에너테이션을 붙여주면 된다. \
하지만 여러 곳에 붙여야 될 경우에 실수로 누락할 가능성이 있다.

#### cf) WebMvcConfigurer 설정하기

여러 곳에 @CrossOrigin을 붙이기 어렵다면, 메인 함수가 있는 곳에 @Bean을 추가하고 세부적인 항목(CRUD 혹은 API 별로)을 작성해주면 된다.



## Reference

{% embed url="https://ko.wikipedia.org/wiki/JSONP" %}
