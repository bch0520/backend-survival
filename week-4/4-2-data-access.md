# 🔸 4-2 Data Access

## DAO(Data Access Object)

1. 정의\
   Data Access Object의 약자로, 데이터베이스의 데이터에 접근하기 위해 생성하는 객체이다.
2. 역사 / 왜 필요한가?\
   데이터베이스에 접근하기 위한 로직과 비즈니스 로직을 분리하기 위해 사용한다
3. 특징(장점)\
   1\) 코드의 간결화 및 모듈화\
   2\) 유지보수가 쉬워짐
4. 사용방법 / 사용경험
5. 개인적인 생각(추가적인 질문 또는 인사이트)
6. 레퍼런스 모음\
   [https://iri-kang.tistory.com/5](https://iri-kang.tistory.com/5)

## List

1. 정의\
   리스트 자료구조는 데이터를 순서대로 저장하고, 중복된 데이터의 저장을 막지 않는 자료구조이다.
2. &#x20;왜 필요한가?\
   인덱스를 통해 저장 데이터에 효율적으로 접근하기 위해 필요하다.
3. 특징(장/단점)\
   1\) 인덱스값이 있기 때문에 데이터 참조가 쉽다.\
   2\) 데이터 양이 많을때 찾는데 시간이 오래 걸린다.\
   3\) 삭제의 과정에서 데이터의 이동이 너무 빈번하다.

<figure><img src="https://velog.velcdn.com/images/yyj8771/post/af62967d-40b3-4582-b8ac-d7d6682af196/image.png" alt=""><figcaption></figcaption></figure>

4. 사용방법(주요 구현체)\
   1\) ArrayList\
   단반향 포인터 구조 데이터 순차적 접근(조회)가 빠름\
   2\) LingkedList\
   양방향 포인터 구조 데이터 삽입, 삭제가 빠름
5. 개인적인 생각(추가적인 질문 또는 인사이트)
6. 레퍼런스 모음\
   [https://hahahoho5915.tistory.com/35](https://hahahoho5915.tistory.com/35)\
   [https://velog.io/@yyj8771/%EB%A6%AC%EC%8A%A4%ED%8A%B8-List-%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0](https://velog.io/@yyj8771/%EB%A6%AC%EC%8A%A4%ED%8A%B8-List-%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0)

## SET

1. 정의\
   자료구조의 하나로, 입력순서를 유지하지 않으며 데이터 중복을 허용하지 않는다.
2. 왜 필요한가?\
   인덱스는 없지만 중복값을 허용하지 않기 때문에, 빠른 탐색이 가능하다.
3. 특징\
   1\) 데이터에 Null 입력가능하나, 한번만 저장하고 중복저장 허용x\
   2\) 인덱스가 따로 존재하지 않기 때문에 iterator를 사용하여 조회.
4. 사용방법(주요 구현체)\
   1\) HashSet\
   입력순서를 보장하지 않으며, 데이터의 중복을 허용하지 않음\
   2\) LinkedHashSet\
   입력순서를 보장하며,  데이터 중복을 허용하지 않음\
   3\) TreeSet\
   입력한 데이터의 크기가 비교가능한 경우 오름차순으로 정렬되며, 데이터의 중복을 하용하지 않음\
   입력하는 데이터가 사용자 정의 객체인 경우 Comparable을 구현하여, 정렬기준 설정 가능
5. 개인적인 생각(추가적인 질문 또는 인사이트)
6. 레퍼런스 모음\
   [https://hahahoho5915.tistory.com/35](https://hahahoho5915.tistory.com/35)

## Map

1. 정의\
   자료구조의 하나로, key와 value로 이루어졌다.
2. 왜 필요한가?\
   순서보다는 정의된 이름(key)과 상응하는 데이터를 효율적으로 찾기위해 필요하다.
3. 특징\
   1\) 키값은 입력순서를 유지하지 않으며 중복을 허용하지 않지만, 밸류값은 중복은 허용한다.\
   2\) 인덱스가 별도로 없기 때문에 iterator를 통해 조회
4.  사용방법(주요 구현체)\
    1\) HashMap\
    키에 대한 입력순서를 보장하지 않으며, 중복을 허용하지 않는다.\
    2\) LinkedHashMap\
    키에 대한 입력순서를 보장하며(인덱스존재), 중복을 허용하지 않는다.\
    3\) TreeMap\
    key의 값을 이용해 순서대로 정렬하여 데이터를 저장하는 자료구조\
    key값을 통한 탐색 뿐 아니라 key값의 정렬을 통한 탐색 등을 하기에 용이하다.


5. 개인적인 생각(추가적인 질문 또는 인사이트)
6. 레퍼런스 모음\
   [https://hahahoho5915.tistory.com/35](https://hahahoho5915.tistory.com/35)\
   [https://blog-of-gon.tistory.com/187](https://blog-of-gon.tistory.com/187)
