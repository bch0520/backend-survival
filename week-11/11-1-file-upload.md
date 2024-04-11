# 🔸 11-1 File Upload

## multipart/form-data

* 정의 \
  HTML에서 \<form> 요소가 서버로 파일이나 이미지를 전송할 때 사용하는 타입.\

*   왜 필요한가?\
    사진에 대한 설명을 위한 `input`과 사진 파일을 위한 `input` 2개가 들어간다. 그런데 이 두 `input` 간에 `Content-type`은 사진 설명은 `application/x-www-form-urlencoded` 이 될 것이고, 사진 파일은 `image/jpeg`이다.

    두 종류의 데이터가 하나의 `HTTP Request Body`에 들어가야 하는데, 그럴때 한번에 두 종류의 데이터를 전송할 때 필요한 것이 multipart 타입이다.\
    &#x20;
* 특징\
  `multipart/form-data`는 `POST`로 보내줘야 하기 때문에 method는 `POST`로 해준다.\

* 사용예시\
  &#x20;
* 레퍼런스 모음\
  [https://velog.io/@shin6403/HTTP-multipartform-data-%EB%9E%80](https://velog.io/@shin6403/HTTP-multipartform-data-%EB%9E%80)

## `@ModelAttribute`

*   정의 \
    `@ModelAttribute` 어노테이션은 컨트롤러의 메서드에서 모델에 속성을 추가하는 데 사용된다. 이 어노테이션을 사용하면 해당 메서드의 리턴 값이 모델에 자동으로 추가되어 뷰로 전달된다.\
    \
    `@Controllerpublic` `class` `MyController {`     \
    `@ModelAttribute`    \
    `public` `void` `addCommonAttributes(Model model) {        model.addAttribute("appName", "My Spring Boot App");    }` `@GetMapping("/home")`    \
    `public` `String home() {`        \
    `return` `"home";`    \
    `}}`\


    위의 예제에서 `addCommonAttributes` 메서드는 `@ModelAttribute` 어노테이션을 사용하여 모델에 “appName”이라는 속성을 추가한다. 이 속성은 모든 컨트롤러 메서드가 호출될 때마다 모델에 자동으로 추가되어 뷰에서 사용할 수 있게 된다.\
    \

*   사용예시\
    @ModelAttribute를 이용한 HTML 폼 데이터 처리

    HTML 폼에서 전송된 데이터를 컨트롤러에서 받아 처리할 때 `@ModelAttribute`를 사용할 수 있다. 폼의 입력 필드와 동일한 이름을 가진 객체를 매개변수로 사용하면 스프링이 자동으로 폼 데이터를 해당 객체에 매핑해준다.\
    `@Controllerpublic` `class` `UserController {` `@GetMapping("/register")`    \
    `public` `String showRegistrationForm(Model model) {        model.addAttribute("user", new` `User());`        \
    `return` `"register";`    \
    `}`     \
    `@PostMapping("/register")`    \
    `public` `String registerUser(@ModelAttribute("user") User user) {        // 사용자 등록 로직 수행`        \
    `return` `"redirect:/login";`    \
    &#x20; `}`\
    `}`

    위의 예제에서 `/register` 경로로 GET 요청이 오면 `showRegistrationForm` 메서드가 실행되어 “user”라는 이름의 빈 `User` 객체를 모델에 추가합니다. 이 객체는 뷰에서 폼을 생성할 때 사용됩니다. POST 요청이 오면 `registerUser` 메서드가 실행되고, 폼 데이터가 `User` 객체에 자동으로 매핑됩니다.



*   @RequestParam과 차이점\


    #### 사용 위치

    **@ModelAttribute:**

    1\) 메서드 매개변수 또는 메서드 레벨에서 사용할 수 있다.

    2\) 메서드 매개변수로 사용될 경우 해당 매개변수를 모델에 추가합니다.

    3\) 메서드 레벨에서 사용될 경우 해당 메서드의 리턴 값이 모델에 추가됩니다.\


    **@RequestParam:**

    1\)메서드 매개변수로 사용되며, 요청의 파라미터 값을 추출합니다.\


    #### 동작 방식

    **@ModelAttribute:**

    1\) 모델에 데이터를 추가하거나, 메서드의 리턴 값으로 모델에 데이터를 추가합니다.

    2\) 주로 뷰에 필요한 데이터를 모델에 추가하는 데 사용됩니다.

    3\) 폼 데이터를 객체에 바인딩하거나, 모든 요청 핸들러 메서드에서 공통으로 사용되는 데이터를 모델에 추가하는 데 유용합니다.\


    **@RequestParam:**

    1\)HTTP 요청의 파라미터 값을 추출합니다.

    2\)주로 HTTP 요청에서 특정한 파라미터 값을 가져오는 데 사용됩니다.

    3\)일반적으로 쿼리 문자열이나 폼 데이터의 특정 파라미터 값을 추출하는 데 사용됩니다.

    ```java
    ```
* 레퍼런스 모음\
  [https://everyshare.co.kr/modelattribute-%EC%96%B4%EB%85%B8%ED%85%8C%EC%9D%B4%EC%85%98-dto-%EA%B0%9D%EC%B2%B4%EC%97%90-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%9B%EA%B8%B0/](https://everyshare.co.kr/modelattribute-%EC%96%B4%EB%85%B8%ED%85%8C%EC%9D%B4%EC%85%98-dto-%EA%B0%9D%EC%B2%B4%EC%97%90-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%9B%EA%B8%B0/)\
  [https://codinghejow.tistory.com/370](https://codinghejow.tistory.com/370)

## IOException

*   정의 \
    입출력 작업 중에 발생하는 예외로, 파일이 존재하지 않거나 파일에 접근할 수 없는 경우 등의 입출력 관련 오류 시 발생한다. 파일을 열거나 읽거나 쓸 때, 네트워크와의 통신 시, 입출력 잡업을 수행하는 도중에 오류가 발생하는 경우 등에 발생한다.

    \

* 특징(취약점)\
  IOException은 보안에 직접적인 영향을 미치지 않지만, 파일 또는 네트워크 상태와 관련하여 예기치 않은 동작을 유발할 수 있으므로 프로그램 안정성에 영향을 미칠 수 있다.\

*   사용예시\
    파일오류가 발생하면 위와 같은 취약점에 노출 될 수 있는데 이에 대한 솔루션이 있다.\


    <pre class="language-bash"><code class="lang-bash"><strong>// 솔루션 1: 파일의 존재 여부를 먼저 확인
    </strong><strong>File file = new File("nonexistent.txt");
    </strong><strong>if (file.exists()) {   
    </strong><strong> // 파일이 존재하는 경우에만 파일 읽기/쓰기 작업 수행    
    </strong><strong>try { FileReader fileReader = new FileReader(file);
    </strong><strong>} catch (IOException e) {        
    </strong><strong>e.printStackTrace();    }
    </strong><strong>} else {    System.out.println("File not found.");}
    </strong><strong>
    </strong><strong>// 솔루션 2: try-catch로 예외 처리
    </strong><strong>try {    FileReader fileReader = new FileReader("nonexistent.txt");} 
    </strong><strong>catch (IOException e) {    
    </strong><strong>// 예외 처리 또는 기본값으로 대체    
    </strong><strong>e.printStackTrace();}
    </strong>
    <strong>솔루션 설명
    </strong>1.파일을 열기 전에 먼저 파일의 존재 여부를 확인하여 파일이 존재하는 경우에만 
    <strong>파일 읽기/쓰기 작업을 수행한다.
    </strong><strong>2. try-catch 블록을 사용하여 IOException이 발생하면 catch 블록에서 해당 예외를 처리한다. 
    </strong><strong>예외가 발생하면 예외 처리 또는 기본값으로 대체하도록 한다.
    </strong></code></pre>

    출처: [https://yourusername.tistory.com/418](https://yourusername.tistory.com/418) \[가비엘:티스토리]\

* 레퍼런스 모음\
  [https://yourusername.tistory.com/418](https://yourusername.tistory.com/418)

## `FileOutputStream`

* 정의 \
  파일에 데이터를 쓰는 데 사용되는 출력 스트림, 원시 자료형 값을 파일에 써야 하는 경우 이 클래스를 사용한다. 이 클래스를 통해 바이트 지향 및 문자 중심 데이터를 작성할 수 있다. 문자 지향 데이터의 경우 FileWriter를 쓰는 것이 좋다. 이미지 데이터와 같은 원시 바이트 스트림을 쓰는 데 사용된다. PDF, 엑셀, 이미지 파일 등 텍스트로 표현할 수 없는 바이트 단위의 데이터와 같이 쓰는 게 좋다.\

* 사용예시
  1. FileOutputStream(File file) : 지정된 파일 객체가 나타내는 파일에 쓸 파일 출력 스트림을 만든다. 파일이 있지만 디렉토리인 경우, 존재하지 않지만 작성할 수 없거나 다른 이유로 열 수 없는 경우 FileNotFoundException 발생
  2. FileOutputStream(File file, boolean append) : 지정된 파일 객체가 나타내는 파일에 쓸 파일 출력 스트림을 만든다. 2번 인수가 true라면 바이트가 파일의 끝에 기록된다. 마찬가지로 파일이 있지만 디렉토리인 경우, 파일이 존재하지 않지만 작성할 수 없거나 다른 이유로 열 수 없는 경우 FileNotFoundException 발생
  3. FileOutputStream(FileDescriptor fdObj) : 파일 시스템의 실제 파일에 대한 기존 연결을 나타내는 지정된 파일 디스크립터에 쓸 파일 출력 스트림을 작성한다.
  4. FileOutputStream(String name) : 지정된 이름으로 파일에 쓸 파일 출력 스트림을 만든다.
  5. FileOutputStream(String name, boolean append) : 2번과 같음. 예외 이름과 예외가 발생하는 원인도 같음.\

* 레퍼런스 모음\
  [https://onlyfor-me-blog.tistory.com/193](https://onlyfor-me-blog.tistory.com/193)

## Mockito `verify()`

*   정의 \
    `verify()`: mock 객체에 대해 원하는 메서드가 특정 조건으로 실행되었는지 여부를 검증할 수 있다.\


    &#x20;**시그니쳐 : verify(T mock, VerificationMode mode)**\
    &#x20;\- mock: 행위를 검증하고자 하는 mock 객체\
    &#x20;\- mode: 검증할 값을 정의하는 메소드. 옵션이다.\

*   기본 예시

    메서드가 호출 되었는지 호출되지 않았는지 검증

    ```java
    // mock 객체
    List mockedList = mock(List.class);

    ...

    verify(mockedList).add("one");    //mockedList에 대해 .add("one")이 호출되었는지 검증
    verify(mockedList).clear();       //mockedList에 대해 .clear()이 호출되었는지 검증
    ```

    💡 매개변수를 요구하는 메서드의 경우, 어떤 매개변수가 오든 검증하고 싶다면 when() 메서드에서와 같이 파라미터로 any() 또는 anyString(), anyLong(), … 등을 넘겨주면 된다.

    ```java
    verify(mockedList).add(anyString());

    ```
*   횟수검증 예시

    : `verify()`의 매개변수(옵션)로 다음과 같은 메서드를 넣어주면 된다

    `1) time(int n)` : 호출 횟수 검증

    `2) atLeastOnce()` : 최소 한번 이상 호출되었는지

    `3) atLeast(int n)` : 최소 n번 이상 호출되었는지

    `4) atMost(int n)` : 최대 n번 이하로 호출되었는지

    `5) never()` : 호출되지 않았는지 여부

    ```java
    // add()가 최소한 1번 이상 호출되었는지 검증
    verify(testMock, atLeastOnce()).add(anyString());

    // add()가 최소한 3번 이상 호출되었는지 검증
    verify(testMock, atLeast(3)).add(anyString());

    // add()가 최대한 3번 이하 호출되었는지 검증
    verify(testMock, atMost(3)).add(anyString());

    // add()가 3번 호출되었는지 검증
    verify(testMock, times(3)).add(anyString());

    verify(testMock, times(1)).add("1"); // add("1")가 1번 호출되었는지 검증

    verify(testMock, times(1)).add("2"); // add("2")가 1번 호출되었는지 검증

    verify(testMock, times(1)).add("3"); // add("3")가 1번 호출되었는지 검증

    verify(testMock, never()).add("4");  // add("4")가 수행되지 않았는지를 검증

    ```
*   순서검증 예시\
    InOrder 객체를 inOrder(”mock 객체명”)으로 생성한 후, 검증하고 싶은 순서에 맞게 verify()를 작성해주면 된다.

    ```java
    InOrder inOrder = inOrder(testMock); //mock 메서드를 호출하는 순서와 다르게 verify를 정의하면 오류가 발생한다.

    inOrder.verify(testMock).add("1");
    inOrder.verify(testMock).add("2");
    inOrder.verify(testMock).add("3");
    ```

    위와 같이 코드를 작성했을 때, 아래와 같은 순서로 메서드를 호출하면 검증이 실패한다.

    ```java
    testMock.add("1");
    testMock.add("3");
    testMock.add("2");
    ```

    1\) InOrder를 사용할 경우, 옵션으로 `calls()` 메서드를 줄 수 있다.

    ```java
    inOrder.verify(testMock, calls(2)).add("1");
    inOrder.verify(testMock).add("2");
    ```

    &#x20;  아래와 같은 순서로 실행되지 않는다면 검증이 실패한다.

    ```java
    testMock.add("1");
    testMock.add("1");
    testMock.add("2");
    ```

    `2) verifyNoMoreInteractions(T mock)` : 선언한 verify 후 해당 mock을 실행하면 검증          이 실패한다.

    ```java
    InOrder inOrder = inOrder(userService);
    inOrder.verify(userService).getUser();
    verifyNoMoreInteractions(userService); //앞의 verify 이후 userService의 메서드를 더 호출하면 fail
    ```

    `3) verifyNoInteractions(T mock)` : 테스트 내에서 mock을 실행하면 검증이 실패한다.

    ```java
    verifyNoMoreInteractions(userService); //userService의 메서드를 호출하면 fail

    ```

    여러 mock 객체가 존재하고, 그 중의 특정 객체들에 대해서만 메서드가 호출될 때 호출되지 않는 다른 mock 객체에 대해 검증하기 위해 사용한다.


*   #### 그 외 옵션들 <a href="#undefined" id="undefined"></a>



    `1) only()` : 해당 검증 메서드만 실행됐는지 검증

    `2) timeout(long mills)` : n ms 이상 걸리면 검증이 실패하고 바로 검증이 종료된다.

    `3) after(long mills)` : n ms 이상 걸리는지 확인. timeout과 달리 시간이 지나도 검증이 종료    \
    &#x20;       되지 않는다.

    `4) description` : 실패할 경우 나올 문구를 설정할 수 있다.\

* 레퍼런스 모음\
  [https://amaran-th.github.io/Java/\[Mockito\]%20verify()%EB%A1%9C%20%ED%96%89%EC%9C%84%20%EA%B2%80%EC%A6%9D%ED%95%98%EA%B8%B0/](https://amaran-th.github.io/Java/\[Mockito]%20verify\(\)%EB%A1%9C%20%ED%96%89%EC%9C%84%20%EA%B2%80%EC%A6%9D%ED%95%98%EA%B8%B0/)

## `@SpyBean`과 `@MockBean` 차이

* 정의 (차이점)\
  @MockBean과 @SpyBean은 둘다 스프링 부트 테스트에서 제공하는 어노테이션이다.\
  먼저, @MockBean은 스프링이 관리하는 bean들 중에서, 하나 이상을 mock객체로 활용하고 싶을 때 사용한다. 스프링 컨텍스트에 mock객체를 등록하게 되고, 스프링 컨텍스트에 의해 @Autowired가 동작할 때 등록된 mock 객체를 사용할 수 있도록 동작한다. 그리고 given에서 선언한 코드외에는 전부 사용할 수 없다.\
  \
  @SpyBean은 가짜객체를 만들어서 임의로 코드를 작성하는 @MockBean과 달리,  given에서 임의로 코드를 작성한 메서드 외에는 그 객체의 실제 메서드를 사용할 수 있다.\
  즉, @SpyBean은 given에서 선언한 코드외에는 전부 실제 객체의 것을 사용한다.\
  마치 실제 객체의 메서드들 중, 우리가 지정한 특정 메서드만 의도되로 작동되게 하는 것이 그 객체의 스파이를 하나 심는다고 생각하면 된다. \
  특정 객체의 일부 메서드만 임의로 코드를 작성하고, 나머지는 실제 메서드를 사용하고 싶을 때 @SpyBean을 사용한다.\

* 왜 필요한가?\
  둘다 테스트를 원활하고 효율적으로 하기 위해서 사용한다.\

* 레퍼런스 모음\
  [https://hyeri0903.tistory.com/238](https://hyeri0903.tistory.com/238)

## 환경변수(환경변수를 다루는 법)

*   cloudinary 사용예시\


    코드에서 환경변수를 사용하기 위해 `application.yml` 파일에 다음을 추가한다.

    ```yaml
    cloudinary:
      url: ${CLOUDINARY_URL}
    ```

    테스트에서 진짜 환경 변수를 쓰려면 이미지 파일이 실제로 올라가기 때문에, 의미 없는 기본 값을 지정할 수도 있다.

    ```yaml
    cloudinary:
      url: ${CLOUDINARY_URL:cloudinary://key:secret@cloud}

    ```
* 레퍼런스 모음\
  [https://class.megaptera.kr/courses/backend-survival/lectures/11/textbook?programId=backend-10](https://class.megaptera.kr/courses/backend-survival/lectures/11/textbook?programId=backend-10)\
