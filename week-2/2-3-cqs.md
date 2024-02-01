# 🔸 2-3 CQS

## CQS(Command Query Separation)란?

디자인 패턴 중 하나이며, CRUD를 중요한 특징에 따라 두가지로 나눈 것이다.

1. Command : Create, Delete, Update(상태가 변함, 불안전)
2. Query : Read(상태 불변, 안전, 분산/캐시 등이 수월함)

## CQS의 원칙

CQS 패턴을 사용할때는 하나의 메소드에 Command와 Query를 동시에 구현하지 않아야 한다.

## CQS의 장점

읽기와 쓰기 로직을 분리하기 때문에 유지보수가 편리하고 가독성이 좋아진다.

## CQS의 단점

하나의 메소드에 불가피하게 읽기와 쓰기를 구현해야 하는 경우에는 오히려 간단한 코드가 복잡해질 수 있다.
