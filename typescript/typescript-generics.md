# 📄 TypeScript - Generics

## 1.Generics

### \(1\). Generics 정의

Java, C\# 같은 정적 타입의 언어의 경우, function 또는 class 정의 하는 시점에 매개변수나 반환 값의 타입을 선언해야 한다. TypeScript 또한 정적 타입의 언어 이기 때문에 fuction 또는 class 정의 하는 시점에 반환 값을 타입을 선언해야 한다.

✍ **Exmple**

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

위의 예제와 같이 `number` 타입 전용으로 `NumberQueue` 클래스를 정의하면 `number` 타입  이외에 다른 요소를 추가 할 때, 런타임 이전에 에러를 사전 감지 할 수 있다. 

하지만 다양한 타입을 지원해야 한다면 타입 별로 클래스를 상속 받아 추가해야 하므로 좋은 방법은 아니다. 이 경우에 제네릭을 사용하면 한 번의 선언으로 다양한 타입에 재사용 가능하다.

✍ **Exmple**

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



### \(2\). 함수에서 Generics

제네릭을 사용할 때에는 &lt;T&gt; 처럼 꺽쇠 안에 타입의 이름을 넣어서 사용한다. 이렇게 설정하면 제네릭은 해당 하는 타입이 뭐든지 들어올 수 있게 되면서, 사용할 때 타입이 깨지지 않는다.

✍ **Exmple**

{% tabs %}
{% tab title="JavaScript" %}
```typescript
function getItemArray(arr, index) {
  return arr[index];
}

function pushItemArray(arr, item) {
  arr.push(item)
}
```
{% endtab %}

{% tab title="TypeScript" %}
```typescript
function getItemArray(arr:any[], index:number):any {
  return arr[index];
}

function pushItemArray(arr:any[], item:any):void {
  arr.push(item);
}
```
{% endtab %}

{% tab title="Generics" %}
```typescript
function getItemArray<T>(arr:T[], index:number):T {
  return arr[index];
}

function pushItemArray<T>(arr:T[], item:T):void {
  arr.push(item);
}


const potatoChip_materials = ['어니언'];

getItemArray(potatoChip_materials, 0);
pushItemArray<string>(potatoChip_materials, '사워크림');


```
{% endtab %}
{% endtabs %}



### \(2\). Interface에서 Generics

✍ **Exmple**

```typescript
interface Items<T> {
  list: T[];
}

const items: Items<string> = {
  list: ['a', 'b', 'c'],
};

```

### \(3\). Type align 에 Generics

✍ **Exmple**

```typescript
type ItemOne<T> = {
  list: T[];
};

const itemOne: ItemOne<string> = {
  list: ['a', 'b', 'c'],
};
```



