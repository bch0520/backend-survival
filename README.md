# 📘 보충이 필요한 개념 정리

## 상속 extends vs implements

1. **extends**\
   클래스가 다른 클래스를 상속받을 때 사용.\
   상속은 부모 클래스의 특성을 자식 클래스가 물려받는것.\
   부모클래스의 public 메서드들을 자식클래스에 별도로 작성하지 않고 사용할 수 있다.\
   단일 상속만 가능하므로 하나의 부모 클래스만 가질 수 있음.
2.  **implements**\
    클래스가 인터페이스를 구현할 때 사용한다.\
    인터페이스는 클래스가 특정 메서드를 구현하도록 강제하며, 클래스가 인터페이스를 구현할 때는 인터페이스의 모든 메서드를 오버라이딩(재정의)해야 한다.

    하나의 클래스는 여러 개의 인터페이스를 구현할 수 있다.\
    (개인적인 생각으로는 implements는 잘 사용하지 않을 것 같기도 하고, 꼭 필요한 상황이 있다면 어떤 상황인지 조금 궁금하다.)
3. reperence chat GPT&#x20;

## Class vs Record vs Interface

1. **class**\
   클래스는 일반적으로 코드를 구성할 때 많이 작성하면, 메서드와 필드로 이루어지며, 상속을 통해 다른 클래스로부터 확장할 수 있다.
2. **record**\
   데이터 전용 클래스로 단순 데이터 저장 및 접근을 위해 사용된다. 레코드는 불변하며, 불변성을 지키기 위해서 getter메서드를 자동을 생성한다. 장점은 간결하고 가독성이 높다. 상속 및 객체지향적 기능을 구현할 수 없다.
3. **interface**\
   인터페이스는 구현된 메서드가 없는 추상 메서드의 집합이다. 따라서 인터페이스를 구현하는 클래스는 인터페이스에서 정의된 모든 메서드를 반드시 구현해야 한다.
4. reperence chat GPT&#x20;

## Override vs Overload

1.  **override(메서드 재정의)**\
    메서드 오버라이딩은 상위 클래스에서 이미 정의된 메서드의 동작을 하위 클래스에서 변경하는 것이다.

    오버라이딩은 상속 관계에서 발생하며, 하위 클래스에서 상위 클래스의 메서드 시그니처(이름, 매개변수 유형 및 반환 유형)를 동일하게 재정의해야 한다.

    메서드 시그니처가 동일하면 하위 클래스의 메서드가 호출된다.\

2.  **overload(메서드 중복정의)**\
    메서드 오버로딩은 같은 이름의 메서드가 여러 번 정의되는 것입니다. 이때 메서드의 시그니처가 서로 다르게 구성된다. 시그니처는 매개변수의 개수, 유형 또는 순서를 의미한다.

    오버로딩은 하나의 클래스 내에서 발생할 수 있으며, 다양한 매개변수를 허용하여 메서드를 호출할 수 있다.
3. reperence chat GPT&#x20;
