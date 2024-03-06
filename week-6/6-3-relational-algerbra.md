# 🔸 6-3 Relational Algerbra

## 관계대수

*   정의 \
    관계형 데이터베이스 내에서 원하는 정보를 어떻게 찾아 낼 수 있는가를 기술하는 절차적인 언어이다.

    이는 DBMS 내부의 처리 언어로 사용된다.​

    대수 Algebra 를 간단히 방정식이라 생각할 수 있다. 하나의 방정식은 연산자와 피연산자로 이루어지는데, 관계대수에서도 동일하다_._ 관계대수에서의 피연산자는 이전에 공부했던 릴레이션이며, 연산자는 셀렉션, 프로젝션, 디비전 등 수학의 집합개념에 기초한 연산자이다.\

* 관계대수 연산자 종류

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FtWAUY%2FbtqI6ixoWjF%2FXTbQuxlYwbPEoXfBnPfm9K%2Fimg.png" alt="" width="563"><figcaption></figcaption></figure>

* 특징\
  1\. 기존의 릴레이션으로부터 새로운 릴레이션을 생성함.\
  2\. 릴레이션이나 관계 대수식에 연산자들을 적용하여 보다 복잡한 관계 대수식을 점차적으로 만들 수 있음.\
  3\. 기본적인 연산자들의 집합으로 이루어짐.\
  4\. 단일 릴레이션이나 두개의 릴레이션을 입력받아 하나의 결과 릴레이션을 생성함.\
  5\. 결과 릴레이션은 또 다른 관계 연산자의 입력으로 사용될 수 있음.

<figure><img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&#x26;fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdoxgcS%2FbtqI4UxhLuO%2Fsg8F7C7pE4ykW3y4waLh51%2Fimg.png" alt="" width="563"><figcaption></figcaption></figure>

* 프로젝션 연산자\
  원하는 Attribute을 포함하는 Pair로 Tuple을 구성. SQL에선 SELECT절 바로 뒤에 속성 이름을 나열하는 방식으로 표현할 수 있다. \
  ex) SELECT name, age, gender \
  &#x20;      FROM people;
* 설렉션 연산자\
  주어진 술어(거칠게 말하면 “조건”)를 만족하는 Tuple만 선택. SQL에선 SELECT문의 WHERE절로 술어를 표현할 수 있다. \
  ex) SELECT name, age, gender \
  &#x20;      FROM people \
  &#x20;      WHERE age < 13;\

* Cartesian Product\
  Relation의 Cartesian Product는 원래 의미와 다르다. 원래는 각 요소의 쌍을 요소로 취하지만(x와 y가 있다면 (x, y)를 새로운 요소로 사용), 관계 대수에서는 그냥 Tuple을 합친다. SQL에선 그냥 FROM 뒤에 관계(SQL에선 Table) 이름을 나열하면 된다.\
  ex) SELECT \* \
  &#x20;     FROM r1, r2;\
  \
  대부분은 Cartesian Product를 그대로 사용하지 않고 Selection과 함께 사용하는데, 이를 Join이라고 한다. 견우, 직녀 등 사람을 다루는 관계 people이 있고, 각 사람이 소유한 물건을 다루는 관계 items가 있을 때, 사람의 이름(name)을 키로 사용한다면 SQL로 다음과 같이 표현할 수 있다.\
  \
  SELECT people.name, age, gender, items.name AS item\_name, usage \
  FROM people, items \
  WHERE people.name = items.person\_name;\
  \
  SQL에선 SELECT와 WHERE로 표현할 수도 있지만, JOIN을 쓰면 편하다. \
  \
  SELECT people.name, age, gender, items.name AS item\_name, usage \
  FROM people \
  JOIN items ON people.name = items.person\_name;\
  \
  아무 것도 소유하지 않은 사람을 포함시키고 싶다면 OUTER JOIN을 사용하면 된다.\
  아래의 경우에는 사람기준으로 데이터가 출력되고, NULL값도 포함하여 출력된다.\
  만약, RIGHT JOIN을 사용하면 사람이 NULL값으로 나오고, 아이템 기준으로 출력이 된다.(사용X) \
  \
  SELECT people.name, age, gender, items.name AS item\_name, usage \
  FROM people \
  LEFT OUTER JOIN items ON people.name = items.person\_name;\

* 레퍼런스 모음\
  [https://chopby.tistory.com/57](https://chopby.tistory.com/57)\
  [https://m.blog.naver.com/aservmz/221960633361](https://m.blog.naver.com/aservmz/221960633361)\
  [https://megaptera.notion.site/6-Database-JDBC-646226a206d1438e9cb1710513f1acb1](https://megaptera.notion.site/6-Database-JDBC-646226a206d1438e9cb1710513f1acb1)
