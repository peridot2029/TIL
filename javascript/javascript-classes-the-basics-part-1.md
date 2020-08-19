# 📄 JavaScript Classes The Basics part 01

### 1. Class 

JavaScript **프로토타입 기반 프로그래밍 \(prototype-based programming\)이다.**

**class-free** 객체지향에서는 **prototype chain, closure** 등으로 객체 지향 언어의 **상속,  캡슐화\(=정보 은닉\)** 등의 개념을 구현할 수 있다.

ES6 class는 `class`키워드를 사용하여 정의한다.

`class`선언문도 변수 선언, 함수 정의와 마찬가지로 **호이스팅**이 발생한다.

### 2. **Instance 생성**

생성자 함수와 같이 new 연산자와 함께 클래스명 호출하면 클래스의 **인스턴스**가 생성된다.

### 3. constructor 

**constructor**는 **Instance**를 생성하고 **class field** 를 초기화 하기 위한 특수한 메소드

**constructor**는 `class`내에서 한 개만 존재해야 된다. 여러 개는 되지 않는다.

**constructor**는 **Instance**의 생성과 동시에 클래스 필드의 생성과 초기화를 실행한다.

**constructor**는 생략 할 수 있다. 생략하게 되면 `constructor() {}`를 포함한 것과 동일하게 동작한다.

### 4. class field

**class 내부에 캡슐화된 변수, 데이터 멤버 & 멤버 변수, 인스턴스 프로퍼티 & 정적 프로퍼티**

**class body**에는 **method**만 선언할 수 있다. 멤버 변수 선언 시 **문법 에러가 발생**한다.

**constructor** 내부에서 선언한 **class field**는 클래스 생성할 **Instance**를 가리키는 `this`에 **bind**

**class Instance를 통해 외부에서 언제나 참조할 수 있다. 즉 언제나 public 이다.**

ES6의 클래스는 다른 객체지향 언어처럼 **private, public, protected** 키워드와 같은 **접근 제한자\(access modifier\)를 지원하지 않는다.**

