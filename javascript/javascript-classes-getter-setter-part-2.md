# 📄 JavaScript Classes getter, setter part 02

### 1. getter 

**getter**는 **method name** 이름 앞에 `get` 키워드를 사용한다.

**getter**는 단어의 의미 그대로 무언가 취득 할 때 사용하므로 반드시 무언가를 반환해야 한다.

**getter**는 **class field**에 **접근**할 때 마다 **class field**의 값을 조작하는 행위가 필요할 때 사용한다.

**getter**는 호출하는 것이 아니라 `property`처럼 참조하는 형식으로 사용하며, 참조 시에는 **method**를 호출된다.

### 2. setter 

**setter**는 **method name** 앞에 `set` 키워드를 사용한다.

**setter**는 **class field**에 값을 **할당** 때 마다 **class field**의 값을 조작하는 행위가 필요할 때 사용한다.

**setter**는 호출하는 것이 아니라 `property`처럼 값을 할당하는 형식으로 사용하며, 할당 시에 **method**가 호출된다.

### 3. static method

**class static method**를 정의할 때 `static`키워드를 사용한다.

**static method**는 **instance**가 아닌 **class name**으로 호출한다.

따라서 **instance**를 생성하지 않아도 호출할 수 있다.

**instance**로 호출 할 수 없다는 의미는 `this`를 사용할 수 없다는 의미이다.

### 4. extends 키워드

**extends** 키워드는 **부모 클래스\(base class\)**를 상속받는 **자식 클래스\(sub class\)**를 정의할 때 사용.

**오버라이딩 \(Overriding\)** 상위 클래스가 가지고 있는 메서드를 하위 클래스가 재정의 사용하는 방식.

**오버로딩 \(Overloading\)** 매개변수의 타입 또는 갯수가 다른, 같은 이름의 메서드를 구현하고 매개변수에 의해 메서드를 구별하여 호출하는 방식

### 5. super 키워드

**super** 키워드는 **base class** 를 참조 할 때 또는 **base class** 의 **constructor** 를 호출할 때 사용.

**super method**는 **sub class**의 **constructor** 내부에서 **base class**의 **constructor**를 호출한다.

즉, 부모 클래스의 인스턴스를 생성한다. 자식 클래스에서`super()` 호출하지 않으면 `this`에 대한 참조 에러가 발생한다.

