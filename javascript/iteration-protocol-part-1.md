# 📄 Iteration protocol part 1

### 1. Iteration protocol 정의

**ES6**에서 도입된 **이터레이션 프로토콜\(Iteration protocol\)**은 데이터 컬렉션을 순회하기 위한 **프로트콜\(미리 약속된 규칙\)**이다. 이터레이션 프로트콜은 준수한 객체는 `for ~ of`문으로 순회가 가능하다.

**이터레이션 프로토콜**에는 **이터러블 프로토콜\(Iterable protocol\)과 이터레이터 프로토콜\(Iterator protocol\)**이 있다.

### 2. It**erable 정의**

**Iterable protocol** 을 준수한 객체를 부르는 명칭이다.

**Symbol.iterator** **method** 구현, **prototype chain**에 의해 **상속한 객체**를 말한다.

**Symbol.iterator** **method** 는 **iterator**를 반환한다.

**array** 는 **Symbol.iterator** **method**를 소유한다.

Object\(일반 객체\)는 **Symbol.iterator** **method 소유하지 않는다.**

```text
// Compliant iterable protocol

const myArray = [1, 2, 3];

console.log(Symbol.iterator in myArray); // true

for (const item of myArray) {
	console.log(item); // 1 2 3
}
```

```text
// Noncompliant iterable protocol
const myObject = { name: "firstObject", value: null };

console.log(Symbol.iterator in myObject); // false

// Uncaught TypeError: myObject is not iterable
for(const item of myObject) {
	console.log(item);
}
```

### 3. I**terator 정의**

**Iterable protocol** 을 준수한 **Iterable**은 **Symbol.iterator method를 소유한다.**

**Iterator protocol** 을 준수한 **Iterator**는 **next method**를 가진다.

**Iterator**의 **next method**를 호출하면 **value, done property**를 갖는**Iterator Iresult object**를 반환한다.

```text
// Compliant iterable protocol
const myArray = [1, 2, 3];

const iterator = myArray[Symbol.iterator]();

console.log("next" in iterator); // true

const iteratorResult = iterator.next();

console.log(iteratorResult);  // {value : 1, done : false }
console.log(iterator.next()); // {value : 2, done : false}
console.log(iterator.next()); // {value : 3, done : false}
console.log(iterator.next()); // {value : undefined, done : true}
```

### 4 . ES6 에서 제공되는 Bulit in **Iterable**

* `Array, String, Map, Set, Arguments`
* `DOM data structure(NodeList, HTMLCollection)`
* `TypedArray`

### 5. Iteration protocol 필요성

* **데이터 소비자 \(Data consumer\)**인 `for ~ of`문 , spread 문법 등은 다양한 데이터 소스를 사용한다.
* **Iteration protocol**을 준수하는 **Iterable** 이다.
* **Iterable 은 데이터 공급자 \(Data** **provider**\) 역할을 한다.
* 다양한 데이터 소스가 **Iteration protocol**을 준수하도록 규정하면 데이터 소비자는 **Iteration protocol** 만을 지원하도록 구현하면 된다.
* 즉, **Iteration protocol**은 다양한 데이터 소스가 하나의 순회 방식을 갖도록 규정하여 **데이터 소비자가 효율적으로 다양한 데이터 소스를 연결하는 인터페이스 역할을 한다.**

