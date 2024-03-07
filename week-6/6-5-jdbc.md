# 🔸 6-5 JDBC

## JDBC

* 정의\
  [자바](https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94\_\(%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D\_%EC%96%B8%EC%96%B4\))에서 [데이터베이스](https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4)(RDBMS)에 접속할 수 있도록 하는 [자바 API](https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94\_API)이다. JDBC는 데이터베이스에서 자료를 쿼리하거나 업데이트하는 방법을 제공한다. API는 그냥 인터페이스기 때문에, 각 DBMS 벤더에서 제공하는 JDBC Driver가 있어야 실제로 사용할 수 있다.\

* 기능\
  JDBC는 3가지 기능을 표준 인터페이스로 정의하여 제공한다.\
  1\. java.sql.Connection - 연결\
  2\. java.sql.Statement -  SQL을 담은 내용\
  3\. java.sql.ResultSet - SQL 요청 응답\

* 동작흐름\
  JDBC는 Java 애플리케이션 내에서 API를 사용하여 데이터베이스에 접근하는 단순한 구조이다.\
  JDBC API를 사용하기 위해서는 JDBC 드라이버를 먼저 로딩한 후 데이터베이스와 연결하게 된다.

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbHk4IH%2FbtrR2EZokg5%2FVlsEZPLukP9YKb7tK0paT1%2Fimg.png" alt="" width="563"><figcaption></figcaption></figure>

* 사용방법\
  JDBC API의 구성 요소들의 사용 흐름은 다음과 같다.\
  1\. JDBC 드라이버 로딩 : 사용하고자 하는 JDBC 드라이버를 로딩한다. JDBC 드라이버는 DriverManager 클래스를 통해 로딩된다.\
  \
  2\. Connection 객체 생성 : JDBC 드라이버가 정상적으로 로딩되면 DriverManager를 통해  데이터베이스와 연결되는 세션인 Connection 객체를 생성한다.\
  \
  3\. Statement 객체 생성 : Statement  객체는 작성된 SQL 쿼리문을 실행하기 위한 객체로 정적 SQL 쿼리 문자열을 입력으로 가진다.\
  \
  4\. Query 실행 : 생선된 Statement 객체를 이용하여 입력한 SQL 쿼리를 실행한다.\
  \
  5\. ResultSet 객체로부터 데이터 조회 : 실행된 SQL 쿼리문에 대한 결과 데이터 셋이다.\
  \
  6\. ResultSet, Statement, Connection 객체들의 Close : JDBC API를 통해 사용된 객체들은 생선된 객체들을 사용한 순서의 역순으로 Close 한다.

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FwTyMC%2FbtrR5yww0DA%2Fjwst72s4xtTKhLTtzfJ0mK%2Fimg.png" alt="" width="375"><figcaption></figcaption></figure>

*   추가적인 내용\
    **\[JDBC 드라이버]**\
    데이터베이스와의 통신을 담당하는 인터페이스.\
    Oracle, MS SQL, MySQL 등과 같은 데이터베이스에 알맞은 JDBC 드라이버를 구현하여 제공.\
    JDBC 드라이버의 구현체를 이용해서 특정 벤더의 데이터베이스에 접근할 수 있음.


* 리퍼런스 모음\
  [https://ko.wikipedia.org/wiki/JDBC](https://ko.wikipedia.org/wiki/JDBC)\
  [https://ittrue.tistory.com/250](https://ittrue.tistory.com/250)
