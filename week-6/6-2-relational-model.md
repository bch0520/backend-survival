# 🔸 6-2 Relational Model

## 관계 데이터 모델 용어 정리

### 관계(Relation)

* 정의 \
  (속성의 집합, 튜플의 집합) 쌍. 관계 데이터 모델에서 각각의 속성에 대해 데이터를 원자값으로 가지는 이차원 테이블이 존재하며 이것을 릴레이션이라고 부릅니다.

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FyuJva%2FbtqCgRNPWXK%2Fkxn5P1HuCWzIX32bnT2rak%2Fimg.png" alt="" width="563"><figcaption><p>관계 데이터 모델 용어 </p></figcaption></figure>

* 특징\
  1\. 관계는 시간에 따라 변하기 때문에, 관계 변수(Relation Value)란 개념을 구분해서 사용할 수 있다.\
  2\. 대개는 Table로 구현되고, 속성 집합을 Schema로 표현한다.\

* 사용예시\
  ( \
  // Heading (속성의 집합)\
  &#x20;{ 이름/문자열, 나이/정수, 성별/문자 },

<pre><code> // Body (튜플의 집합)
  {
	{ (이름/문자열, 견우), (나이/정수, 13), (성별/문자, 남) },
	{ (이름/문자열,직녀), (나이/정수, 12), (성별/문자, 여) }
<strong>  }
</strong></code></pre>

&#x20;     )

* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://megaptera.notion.site/6-Database-JDBC-646226a206d1438e9cb1710513f1acb1](https://megaptera.notion.site/6-Database-JDBC-646226a206d1438e9cb1710513f1acb1)

### 속성(Attribute)

* 정의 \
  릴레이션의 열을 속성, attribute라고 부른다. 속성은 이름과 타입으로 구성된다. 이름은 집합 안에서 유일해야 한다.\

* 특징\
  대개는 Column으로 구현된다.\

* 사용예시(이름/타입)\
  1\. 이름/문자열\
  2\. 나이/정수\
  3\. 성별/문자
* 개인적인 생각(추가적인 질문 또는 내용)\

* 레퍼런스 모음\
  [https://megaptera.notion.site/6-Database-JDBC-646226a206d1438e9cb1710513f1acb1](https://megaptera.notion.site/6-Database-JDBC-646226a206d1438e9cb1710513f1acb1)

### 튜플

* 정의 \
  릴레이션의 행을 튜플( tuple)이라고 부릅니다. (속성, 값) 쌍의 집합.\

* 특징\
  1\. 하나의 집합에서 속성 이름은 유일하기 때문에, 속성 이름은 겹치지 않는다.\
  2\. 대개는 Row, Record로 구현된다.\
  3\. 튜플은 집합이기 때문에 중복을 허용하지 않지만, 대부분의 RDBMS는 중복을 허용한다. \
  4\. RDBMS는 NULL도 허용한다.\

* 사용예시\
  { (이름/문자열, 견우), (나이/정수, 13), (성별/문자, 남) }\

* 레퍼런스 모음\
  [https://megaptera.notion.site/6-Database-JDBC-646226a206d1438e9cb1710513f1acb1](https://megaptera.notion.site/6-Database-JDBC-646226a206d1438e9cb1710513f1acb1)

###
