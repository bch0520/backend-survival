# 🔸 12-2 Redis

## Redis

* 정의 \
  Redis는 세계에서 가장 빠른 인메모리 데이터베이스이다. \

* 왜 필요한가?\
  간단하게 말하게 속도가 빠른 앱을 간단하게 구축, 확장 및 배포할 수 있다.\

* 특징\
  1\) Redis는  [문자열](https://redis.io/resources/data-types/strings/) ,  [해시](https://redis.io/resources/data-types/hashes/) ,  [목록](https://redis.io/resources/data-types/lists/) ,  [세트](https://redis.io/resources/data-types/sets/) ,  ​​범위 쿼리가 포함된 [정렬된 세트](https://redis.io/resources/data-types/sorted-sets/)  ,  [비트맵](https://redis.io/resources/data-types/bitmaps/) ,  [하이퍼로그 로그](https://redis.io/resources/data-types/hyperloglogs/) ,  [지리공간 인덱스](https://redis.io/resources/data-types/geospatial/) 및  [스트림](https://redis.io/resources/data-types/streams/) 과  같은  [데이터 구조를](https://redis.io/resources/data-types/) 제공한다 . Redis에는 [복제](https://redis.io/topics/replication) ,  [Lua 스크립팅](https://redis.io/commands/eval) ,  [LRU 제거](https://redis.io/resources/reference/eviction/) ,  [트랜잭션](https://redis.io/topics/transactions) 및 다양한 수준의  [온디스크 지속성이](https://redis.io/topics/persistence) 내장되어  있으며 [Redis Sentinel 및 ](https://redis.io/topics/sentinel)[Redis 클러스터를](https://redis.io/topics/cluster-tutorial)  통한 자동 파티셔닝을  통해 고가용성을 제공한다.\
  \
  2\) [문자열에 추가하는](https://redis.io/commands/append)  것과 같이 이러한 유형에 대해  **원자적 작업을** 실행할 수 있다  .  [해시의 값을 증가시킨다](https://redis.io/commands/hincrby) .  [요소를 목록에 푸시](https://redis.io/commands/lpush) ;  [집합 교집합](https://redis.io/commands/sinter) ,  [합집합](https://redis.io/commands/sunion)  ,  [차이 계산](https://redis.io/commands/sdiff) ; 또는  [정렬된 집합에서 가장 높은 순위를 가진 구성원을 가져온다](https://redis.io/commands/zrange) .\
  \
  3\) 최고의 성능을 달성하기 위해 Redis는  **인메모리 데이터 세트를** 사용하여 작업한다 . 사용 사례에 따라 Redis는  [데이터 세트를 주기적으로 디스크에 덤프 하거나 ](https://redis.io/topics/persistence#snapshotting)[각 명령을 디스크 기반 로그에 추가하여](https://redis.io/topics/persistence#append-only-file)  데이터 를 유지할 수 있다 . 기능이 풍부하고 네트워크로 연결된 인메모리 캐시가 필요한 경우 지속성을 비활성화할 수도 있다.\
  \
  4\) Redis는  빠른 비차단 동기화와 넷 분할 시 부분 재동기화를 통한 자동 재연결을 통해 [비동기식 복제를 지원](https://redis.io/topics/replication)한다.\

* 레퍼런스 모음\
  [https://redis.io/about/](https://redis.io/about/)

## in-memory

* 정의 \
  디스크가 아닌 내부 메모리 혹은 주 메모리에 데이터를 보유하고 있는 데이터베이스로 디스크 검색보다 자료접근이 훨씬 빠르다.\

* 왜 필요한가?\
  잃어버려도 되는 데이터를 저장하거나 테스트 DB를 사용할때 빠르고 간편하게 이용할 수 있다.\

* 특징\
  단점으로는 RAM에 데이터를 저장하기 때문에, 전원이 갑자기 꺼지게 된다면 모든 데이터는 소멸된다. 즉 영속성(persistence)가 보장되지 않는다.\

* 인메모리 데이터베이스 예시\
  mysql, mariaDB도 옵션을 추가하여 인메모리 데이터베이스로 사용가능하며,\
  대표적으로는 아래와 같다.\
  &#x20;Amazon ElastiCache (미국), Redis (미국), 알티베이스 (Altibase) (한국), Kairos (한국), SAP HANA (독일), SunDB - (한국), TimesTen (미국, 오라클), Memcached (미국)\

* 레퍼런스 모음\
  [https://velog.io/@gwon7210/%EC%9D%B8%EB%A9%94%EB%AA%A8%EB%A6%AC-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4%EB%9E%80](https://velog.io/@gwon7210/%EC%9D%B8%EB%A9%94%EB%AA%A8%EB%A6%AC-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4%EB%9E%80)

## NoSQL

* 정의 \
  NoSQL이라는 용어는 비관계형 데이터베이스 유형을 가리키며 이 데이터베이스는 관계형 테이블과는 다른 형식으로 데이터를 저장한다. 그러나 NoSQL 데이터베이스는 언어마다 관습화된 API, 선언적 구조의 쿼리 언어, 쿼리별 언어를 사용하여 질의할 수 있다. 이 데이터베이스가 not only SQL 데이터베이스라고 불리는 이유가 바로 이것이다.\

* 필요한 이유\
  높은 확장성과 가용성이 주요 장점인 NoSQL 데이터베이스는 실시간 웹 애플리케이션 및 빅 데이터에 널리 사용된다. 변화하는 요구 사항에 빠르게 적응함으로써 민첩한 개발 패러다임에 자연스럽게 활용되는 이점 때문에 개발자들 역시 NoSQL을 선호한다. NoSQL 데이터베이스를 사용하면 데이터는 보다 직관적이고 이해하기 쉬운 방식 또는 애플리케이션이 사용하는 것에 가까운 방식으로 저장되며, NoSQL 스타일의 API를 사용하면 저장 또는 검색 시 데이터 변환의 필요성이 줄어든다. 또한 NoSQL 데이터베이스는 다운타임이 없는 클라우드의 이점을 완전히 누릴 수 있다.\

* 특징(장점)
  *   **유연성**

      SQL 데이터베이스를 사용하면 데이터는 훨씬 더 엄격한 사전 정의된 구조 안에 저장됩니다. 하지만 NoSQL을 사용하면 데이터는 엄격한 스키마 없이도 훨씬 더 자유로운 형식으로 저장될 수 있습니다. 이와 같은 설계 덕분에 혁신과 빠른 애플리케이션 개발이 가능해집니다. 개발자들 역시 스키마 걱정 없이 고객들에게 더 나은 서비스를 제공하기 위한 시스템 개발에만 몰두할 수 있죠. NoSQL 데이터베이스는 하나의 데이터 저장소에서 구조적, 반구조적, 비구조적 데이터 등 모든 형식의 데이터를 손쉽게 처리할 수 있다.
  *   **확장성**

      NoSQL 데이터베이스는 서버를 증설해 확장하는 대신 상업용 하드웨어를 사용해 확장할 수 있다. 덕분에 증가한 트래픽을 지원하고 다운타임 없이 수요를 충족시킬 수 있다. NoSQL 데이터베이스는 확장을 통해 더 큰 용량과 성능을 갖출 수 있다. 이와 같은 이유로 데이터 세트 확장을 위한 옵션으로서 NoSQL 데이터베이스에 대한 선호도가 높다.
  *   **고성능**

      NoSQL 데이터베이스의 확장 아키텍처는 데이터 양이나 트래픽이 증가할 때 그 진가를 발휘합니다. 아래 그래픽에서 볼 수 있듯이 이 아키텍처는 빠르고 예측 가능한 10밀리초 미만의 응답 시간을 보장한다. 또한 NoSQL 데이터베이스는 데이터를 수집하여 이를 빠르고 안정적으로 제공한다. NoSQL 데이터베이스가 매일 테라바이트 규모의 데이터를 수집하는 동시에 고도의 대화식 사용자 경험을 제공하는 애플리케이션에 활용되는 이유가 바로 이것이다. 아래 그래픽은 3-4ms 범위 내 95번째 대기시간을 제공하는 초당 300회의 읽기 송신율(파란색 선)과 4-5ms 범위 내 95번째 대기시간을 제공하는 초당 140회의 쓰기 송신률(초록색 선)을 보여준다.
  *   **가용성**

      NoSQL 데이터베이스는 여러 서버, 데이터 센터, 클라우드 리소스 전반의 데이터를 자동으로 복제합니다. 그 결과 사용자의 위치와 상관없이 사용자 대기시간이 최소화된다. 이 기능은 데이터베이스 관리 부담을 줄이는 데에도 효과적이다. 덕분에 더 많은 시간을 우선 순위에 할애할 수 있다.
  *   **고도의 기능성**

      NoSQL 데이터베이스는 데이터 저장 수요가 엄청나게 큰 분산형 데이터 저장소를 위해 설계되었다. 이와 같은 특성 덕분에 NoSQL은 빅 데이터, 실시간 웹 앱, 360도 고객 정보, 온라인 쇼핑, 온라인 게이밍, 사물인터넷, 소셜 네트워크, 온라인 광고 애플리케이션 등을 처리하기에 이상적인 데이터베이스 옵션이다.\

* 사용예시\
  &#x20;
* 레퍼런스 모음\
  [https://www.oracle.com/kr/database/nosql/what-is-nosql/](https://www.oracle.com/kr/database/nosql/what-is-nosql/)
