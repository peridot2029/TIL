# 📄 TypeScript - Generics

## 1.Generics 정의

Java, C\# 같은 정적 타입의 언어의 경우, `function` 또는 `class`정의 하는 시점에 매개변수나 반환 값의 타입을 선언해야 한다. TypeScript 또한 정적 타입의 언어 이기 때문에 `fuction` 또는 `class`정의 하는 시점에 반환 값을 타입을 선언해야 한다.

```typescript
class Queue { 
  protected data = [];

  push(item) {
    this.data.push(item);
  }

  pop() {
    return this.data.shift();
  }
}
// Queue class extends 
class NumberQueue extends Queue {
  // only number type item push
  push(item: number) {
    super.push(item);
  }

  pop(): number {
    return super.pop();
  }
}

const queue = new NumberQueue();

queue.push(0);
// string type error
// queue.push(+'1'); 

console.log(queue.pop().toFixed()); // 0
console.log(queue.pop().toFixed()); // 1
```

위의 예제와 같이 `number`타입 전용으로 `NumberQueue`클래스를 정의하면 `number` 타입  이외에 다른 요소를 추가 할 때, 런타임 이전에 에러를 사전 감지 할 수 있다. 

하지만 다양한 타입을 지원해야 한다면 타입 별로 클래스를 상속 받아 추가해야 하므로 좋은 방법은 아니다. 이 경우에 제네릭을 사용하면 한 번의 선언으로 다양한 타입에 재사용 가능하다.

```typescript
class Queue<T> {
  protected data: Array<T> = [];
  push(item: T) {
    this.data.push(item);
  }
  pop(): T {
    return this.data.shift();
  }
}

// number 전용 Queue
const numberQueue = new Queue<number>();

numberQueue.push(0);
// numberQueue.push('1'); 
numberQueue.push(+'1');   

console.log(numberQueue.pop().toFixed()); // 0
console.log(numberQueue.pop().toFixed()); // 1

// string 전용 Queue
const stringQueue = new Queue<string>();

stringQueue.push('Hello');
stringQueue.push('World');

console.log(stringQueue.pop().toUpperCase()); // HELLO
console.log(stringQueue.pop().toUpperCase()); // WORLD

// 커스텀 객체 전용 Queue
const myQueue = new Queue<{name: string, age: number}>();
myQueue.push({name: 'Lee', age: 10});
myQueue.push({name: 'Kim', age: 20});

console.log(myQueue.pop()); // { name: 'Lee', age: 10 }
console.log(myQueue.pop()); // { name: 'Kim', age: 20 }
```

🤚 **제네릭은 선언 시점이 아닌 생성 시점에 타입을 명시해야 하나의 타입만 아닌 다양한 타입을 사용할 수 있도록 하는 기법이다. 한 번의 선언으로 다양한 타입에 재사용 가능하다는 장점이 있다.**

🤚**T 는 제네릭은 선언할 때  관용적으로 식별자 타입 파라미터 \(type  parameter\)라 한다.** T는 Type 의 약자로 반드시 T를 사용해야 돠는 것은 아니다.



### \(2\). **Function →** Generics

또한 함수에서도 제네릭을 사용할 수 있다. 제네릭을 사용하면 다양한 타입의 매개변수와 리턴 값을 사용할 수 있다.

`reverse` 함수는 다양한 타입의 요소로 구성된 배열을 인자로 전달 받는다.  예를 들면 `number` 타입의 요소를 갖는 배열을 전달 받으면 타입 매개변수는 `number`가 된다.

{% code title="Example : Generic function " %}
```typescript
function reverse<T>(items: T[]): T[] {
  return items.reverse();
}

const arg = [1, 2, 3, 4, 5];
// 인수에 의해 타입 매개변수가 결정
const reversed = reverse(arg);
console.log(reversed); // [ 5, 4, 3, 2, 1 ]
```
{% endcode %}

만약에 `{name:string}` 타입의 요소를 갖는 배열을 전달 받으면 타입 매개변수는 `{name:string}`이 된다.

{% code title="Example : Generic function " %}
```typescript
function reverse<T>(items: T[]): T[] {
  return items.reverse();
}

const arg = [{ name: 'Lee' }, { name: 'Kim' }];
// 인수에 의해 타입 매개변수가 결정된다.
const reversed = reverse(arg);
console.log(reversed); // [ { name: 'Kim' }, { name: 'Lee' } ]
```
{% endcode %}

### \(2\). Interface → Generics

{% code title="Example : Generic Interface as Type" %}
```typescript
interface KeyPair<T, U> {
    key: T;
    value: U;
}
let kvOne: KeyPair<number, string> = { key:1, value:"String" };
let kvTwo: KeyPair<number, number> = { key:1, value:12345 };
console.log(kvOne); // Object {key: 1, value: "String"}
console.log(kvTwo); // Object {key: 1, value: 12345}

```
{% endcode %}

{% code title="Example : Generic Interface as Function Type" %}
```typescript
interface KeyValueProcessor<T, U> {
  (key: T, val: U): void;
}
function processNumKeyPairs(key: number, value: number): void {
  console.log("processStringKeyPairs: key = " + key + ", value = " + value);
}
let strKVProcessor: KeyValueProcessor<number, number> = processNumKeyPairs;
strKVProcessor(1, 12345); // processStringKeyPairs: key = 1, value = 12345

function processKeyPairs<T, U>(key: T, value: U): void {
  console.log(`processKeyPairs key = ${key}, value = ${value}`);
}

let numKVProcessor: KeyValueProcessor<number, number> = processKeyPairs;
numKVProcessor(1, 12345); // processKeyPairs key = 1, value = 12345
```
{% endcode %}

### \(3\). Type align → Generics

✍ **Exmple**

```typescript
type ItemOne<T> = {
  list: T[];
};

const itemOne: ItemOne<string> = {
  list: ['a', 'b', 'c'],
};
```



