# 🔸 3-3 Jackson ObjectMapper

## Jackson ObjectMapper 란?

Jackson은 자바에서 Json을 다루기 위한 유용한 라이브러리인데, Jackson ObjectMapper는 Jackson 라이브러리의 일부분이다.

## ObjectMapper

DTO(자바 객체)를 Json(문자열)으로 변환하거나, Json(문자열)을 DTO(자바 객체)로 변환시키는 역할을 수행한다.

## @JsonProperty

이 어노테이션은 Json 형식으로 변환할때 한 개의 키값을 설정할 수 있도록 해준다.\
(카멜 케이스 <-> 스네이크 케이스)\
`@JsonProperty("memberPhoneNumber")`\
`privite String member_phone_number;`

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcRngDp%2FbtrHZUZaHKX%2FpZF7mQ25dYqOtkKpclHHSK%2Fimg.png" alt=""><figcaption><p><a href="https://dev-jwblog.tistory.com/120">https://dev-jwblog.tistory.com/120</a></p></figcaption></figure>

`키값이 카멜 케이스로 변환된 것을 확인 할 수 있다.`

#### `반면 @JsonNaming 은 여러개의 키 값을 한번에 변환할 수 있게 해준다.`

`@JsonNaming(value=PropertyNamingStrategies.SnakeCaseStrategy.class)`\
`public class UserRequestDto {` \
`private String memberId;` \
`private String memberName;` \
`private String memberPhoneNumber;` \
`private String zipCode; }`

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FSyl11%2FbtrH3bSozTB%2FMkkTlxzR2RheuXYGSPoCT1%2Fimg.png" alt=""><figcaption><p><a href="https://dev-jwblog.tistory.com/120">https://dev-jwblog.tistory.com/120</a></p></figcaption></figure>

키값이 모두 스네이크 케이스로 변환된 것을 확인 할 수 있다.

## Reference

{% embed url="https://dev-jwblog.tistory.com/120" %}
