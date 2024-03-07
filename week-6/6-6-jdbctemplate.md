# 🔸 6-6 JdbcTemplate

## JdbcTemplate

* 정의\
  Jdbc 코어패키지의 중앙클래스로, Jdbc 사용을 단순화하고 일반적인 오류을 방지하는데 도움이 된다. \
  즉, 개발자가 Jdbc 기술을 손쉽게 사용할 수 있도록 도와주는 클래스이다.\

* 왜 필요한가?\
  다음과 같은 반복작업을 대신 처리해 준다.\
  1\. Statement를 준비하고 실행\
  2\. 결과를 반복하도록 루프를 실행\
  3\. 커넥션 종료, statement 및 resultset 종료\
  4\. 트랜잭션을 다루기 위한 커넥션 동기화\
  5\. 예외 발생시 스프링 예외 변환기 실행\

* 사용방법\
  1\. JdbcTemplate 설정\
  먼저 build.gradle에  jdbc 라이브러리를 추가해준다.\
  implenmentation 'org.springframework.boot:spring-boot-starther-jdbc'\
  \
  2\. DataSource 주입\
  `private final JdbcTemplate jdbcTemplate;`\
  `public JdbcTemplateItemRepository(DataSource dataSource) {`\
  &#x20;           `this.jdbcTemplate = new JdbcTemplate(dataSource);`\
  `}`\
  JdbcTemplate은 DateSource를 필요로한다. 이렇게 JdbcTemplate을 사용할때 DataSource 의존관계 주입받는 방법과, JdbcTemplate을 스프링 빈으로 직접 등록하고 주입 받는 방법이 있는데 전자를 더 많이 사용한다.\
  \
  3\. 쿼리 작성 및 실행\
  1\) queryForObject()\
  queryForObject() 인터페이스의 정의는 다음과 같다.\
  \<T> T queryForObject(String sql, RowMapper\<T> rowMapper, Object... args) \
  throw Data AccessException;\
  \
  sql : 실행할 sql문\
  rowMapper: 조회대상\
  args: 파라미터들\
  \
  queryForObject() 메서드를 사용하면 단건 조회를 할 수 있다.  이때 조회 대상이 객체가 아닌 데이터라면 타입을 아래와 같이 지정해줄 수 있다.\
  int rowCount = jdbcTemplate.queryForObject("select count(\*) from t\_actor" ,Integer.class);\
  \
  preparedStatement ("?")를 이용해 파라미터 바인딩도 할 수 있다. ?에 순서대로 파라미터가 들어가게 된다.\
  int countOfActorsNamedJoe = jdbcTemplate.queryForObject("select count(\*) from t\_actor where first\_name = ?", Interger.class, "Joe");\
  \
  String을 조회할 때는 아래와 같이 사용할 수도 있다.\
  String lastName = jdbcTemplate.queryForObject("select last\_name from t\_actor where id = ?", String.class, 1212L);\
  \
  이때 단순 데이터 타입이 아닌 객체를 조회하려면 RowMapper를 활용하면 된다.\
  **RowMapper는 데이터베이스의 반환 결과인 ResultSet을 객체를 변환해주는 클래스이다.**\
  \
  순수 JDBC를 사용할 때는 객체를 조회할 때 다음과 같이 했다.\
  // 쿼리 날리기\
  &#x20;ResultSet rs = stat.excuteQuery("SELECT  \* From Item"); \
  \
  //결과값 가져오기\
  while(rs.next()) {\
  // Item 객체에 값 저장\
  item = new Item(); \
  item.setId(rs.getInt(1));\
  item.setItemName(rs.getString(2));\
  item.setPrice(rs.getInt(3));\
  &#x20;//리스트에 추가\
  itemList.add(item);}\
  \
  ResultSet의 결과를 개발자가 직접 꺼내 객체에 담아 저장하였다.\
  하지만 RowMapper를 사용하면 이러한 반복 작업을 자동화해준다.\
  \
  RowMapper의 mapRow()라는 메서드는 아래와 같이 정의되어 있다.\
  T mapRow(ResultSet rs, int rowNum) throws SQLException;\
  \
  ResultSet rs에 결과값을 담아와 사용자가 원하는 객체에 담는다. rowNum은 반복되는 루프 중 현재 행의 번호를 나타낸다.\
  \
  즉 아래와 같이 동작한다.\
  public Item mapRow(ResultSet rs, int rowNum) throws SQLExeption { \
  //ResultSet 값을 Item 객체에 저장\
  Item item = new Item();\
  item.setId(rs.getLong("id"));\
  item.setItemName(rs.getString("item\_name"))\
  item.setPrice(rs.getInt("price"));\
  //item 반환\
  return item;\
  };\
  \
  이것을 람다식으로 더 간단하게 만들고, queryForObject() 메서드에서 객체를 조회하도록 할 수 있다.\
  String sql = "select id, item\_name, price from item where id= ?";\
  Item item = jdbcTemplate.queryForObject(sql, itemRowMapper(), id);\
  private RowMapper\<Item> itemRowMapper() {\
  return (rs, rowNum) -> {\
  Item item = new Item();\
  item.setId(rs.getLong("id));\
  item.setItemName(rs.getString("item\_name"));\
  item.setPrice(rs.getInt("price"));        \
  item.setQuantity(rs.getInt("quantity"));        \
  return item;    \
  &#x20;   };\
  }\
  \
  2\) query() 메서드\
  query()  메서드를 사용하면 여러 건을 조회할 수 있다. 이때도 역시 RowMapper를 이용할 수 있다.\
  private final RowMapper\<Actor> actorRowMapper = (resultSet, rowNum) -> {\
  Actor actor = new Actor();\
  actor.setFirstName(resultSet.getString("first\_name"));\
  actor.setLastName(resultSet.getString("last\_name"));\
  return actor;\
  };\
  \
  public List\<Actor> findAllActors() {\
  return this.jdbcTemplate.query("select first\_name, last\_name from t\_actor", actorRowMapper);\
  \
  3\) update() 메서드\
  INSERT,  UPDATE, DELETE 등 데이터를 변경하고 싶을 때는 update() 메서드를 사용할 수 있다. \
  SQL 실행 결과에 영향받은 로우 수를  int로 반환한다.\
  \
  **등록**\
  jdbcTemplate.update("insert into t\_actor (first\_name, last\_name) values (?, ?)", "Leonor", "Watling");\
  \
  **수정**\
  jdbcTemplate.update("update t\_actor set last\_name = ? where id = ?", "Banjo", 5276L);\
  \
  **삭제**\
  jdbcTemplate.update("delete from t\_actor where id = ?", Long.valueOf(actorId));\
  \
  4\) execute() 메서드\
  이외에 임의의 SQL을 실행할 때는 execute() 메서드를 사용할 수 있다. 테이블을 생성하는 DDL 등에 사용할 수 있다.\
  jdbcTemplate.execute("create table mytable (id integer, name varchar(100))");\

* 추가적인 생각\

* 리퍼런스 모음\
  [https://code-lab1.tistory.com/277](https://code-lab1.tistory.com/277)
