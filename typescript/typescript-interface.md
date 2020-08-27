# 📄 TypeScript Interface

## 1. Interface

### \(1\). Interface 소개

🤚 [`interface`](https://ko.wikipedia.org/wiki/%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4_%28%EC%BB%B4%ED%93%A8%ED%8C%85%29)는 간단하게 어떠한 시스템 두 개의 시스템 사이에 상호작용 할 수 있게 해주는 조건, 규약 

인터페이스는 일반적으로 타입 체크를 위해 사용되며 variable, function,class 등에 사용할 수 있다. 인터페이스는 여러 가지 타입을 갖는 프로퍼티로 이루어진 새로운 타입을 정의하는 것과 유사하다.

인터페이스는 프로퍼티와 메서를 가질 수 있다는 점에서 class와 유사하나, 직접 인스턴스를 생성할 수 없고, 모든 메서드 추상 메서드 이다.

✍ **Exmple**

```typescript
interface Todo {
  id: number;
  content: string;
  completed: boolean;
}

let todos: Todo[] = [];

function addTodo(todo: Todo) {
  todos = [...todos, todo];
}

const newTodo: Todo = { id: 1, content: 'typescript', completed: false };
addTodo(newTodo);

console.log(todos)
```

### \(2\). Variable and Function Interface

✍ **Exmple**

{% tabs %}
{% tab title="variable interface" %}
```typescript
interface Todo {
  id: number;
  content: string;
  completed: boolean;
}

let todos: Todo[] = [];


function addTodo(todo: Todo) {
  todos = [...todos, todo];
}

const newTodo: Todo = { id: 1, content: 'typescript', completed: false };
addTodo(newTodo);
console.log(todos)
```
{% endtab %}

{% tab title="function interface" %}
```typescript
interface SquareFunc {
  (num: number): number;
}


const squareFunc: SquareFunc = function (num: number) {
  return num * num;
}

console.log(squareFunc(10));
```
{% endtab %}
{% endtabs %}

### \(**3**\). Optional Properties

인터페이스의 프로퍼티는 반드시 구현되어야 하는데, 프로퍼티가 선택적으로 필요한 경우에 **선택적 프로퍼티\(Optional Properties\)**를 사용할 수 있다. 이는  프로퍼티명 뒤에 ? 를 붙이며, 생략해도 에러가 발생하지  않는다.

✍ **Exmple**

```typescript
interface UserInfo {
  username: string;
  password: string;
  age?    : number;
  address?: string;
}

const userInfo: UserInfo = {
  username: 'peridot2029@gmail.com',
  password: '123456'
}

console.log(userInfo);
```

### **\(4\). Interpace E**xtends

인터페이스는 `extends`  키워드를 사용하여 인터페이스 또는 클래스를 상속 받을 수 있다.

✍ **Exmple**

{% tabs %}
{% tab title="Single Iterface" %}
```typescript
interface Person {
  name: string;
  age?: number;
}

interface Student extends Person {
  grade: number;
}

const student: Student =  {
  name: 'Lee',
  age: 20,
  grade: 3
}
```
{% endtab %}

{% tab title="Plural Interface" %}
```typescript
interface Person {
  name: string;
  age?: number;
}

interface Developer {
  skills: string[];
}

interface WebDeveloper extends Person, Developer {}

const webDeveloper: WebDeveloper =  {
  name: 'Lee',
  age: 20,
  skills: ['HTML', 'CSS', 'JavaScript']
}
```
{% endtab %}
{% endtabs %}





