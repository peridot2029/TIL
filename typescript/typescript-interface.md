# 📄 TypeScript - Interface, function

## 1. Interface

### \(1\).  Interface 정의

🤚 [`interface`](https://ko.wikipedia.org/wiki/%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4_%28%EC%BB%B4%ED%93%A8%ED%8C%85%29)는 간단하게 어떠한 시스템 두 개의 시스템 사이에 상호작용 할 수 있게 해주는 조건, 규약 

인터페이스는 일반적으로 타입 체크를 위해 사용되며 variable, function,class 등에 사용할 수 있다. 인터페이스는 여러 가지 타입을 갖는 프로퍼티로 이루어진 새로운 타입을 정의하는 것과 유사하다.

인터페이스는 프로퍼티와 메서를 가질 수 있다는 점에서 class와 유사하나, 직접 인스턴스를 생성할 수 없고, 모든 메서드 추상 메서드 이다.



### \(2\). 변수, 함수와 인터페이스 \(Variable, Function Interface\)

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

### \(**3**\). 선택적 프로퍼티 \(Optional Properties\)

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

### **\(4\). 인터페이스의 상속 \(Interpace E**xtends\)

인터페이스는 `extends`  키워드를 사용하여 인터페이스 또는 클래스를 상속 받을 수 있다.

✍ **Exmple**

{% tabs %}
{% tab title="single Iterface" %}
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

{% tab title="plural Interface" %}
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

## 2. Function

### \(1\).  Function 정의

TypeScript는 JavaScript와 마찬가지로 **기명 함수 \(named function\)**와 **익명 함수 \(anonymous function\)**으로 만들 수 있다. 

### \(2\). 함수의 타이핑 \(Typing the function\)

각각 매개변수와 반한 될 타입을 지정해서 명시한다. 이때 반환될 타입을 우측에 명시하면 된다.

✍ **Exmple**

```typescript
// named function
function sum(x: number, y: number): number {
  return x + y;
}
sum(1, 2);

// anonymonus function
let sumAdd = function (x: number, y: number): number {
  return x + y;
};
```

### \(3\). 함수의 타입 작성 \(Writing the function type\)

함수에 타입을 붙힌 뒤, 타입들을 살펴보고 함수 전체의 타입을 작성한다.

✍ **Exmple**

```typescript
let totalAdd: (value: number, incerment: number) => number = function (
  x: number, y: number) {
  return x + y;
}
```

### \(4\). 타입의 추론 \(Inferring the types\)

TypeScript는 컴파일러가 한쪽에만 타입을 명시해도 알아낼 수 있다.

✍ **Exmple**

```typescript
let rectangle: (width: number, height: number) => number = function (x, y) {
  return x * y;
};
```

### \(5\). 선택적 매개변수와 기본 매개변수 \(Optional and Defalut Parameter\)

Typescript 에서 모든 매개변수가 함수에 필요하다고 가정 한다. 이것은 `null` 또는 `undefined`를 의미하는 것은 아니다. 

컴파일러는 각 매개변수에 대해 사용자가 값을 제공했는지 검사한다. 또한 컴파일러는 매개변수들이 함수로 전달된 유일한 매개변수 라고 가정한다.  **즉, 함수에 주어진 인자의 수는 함수가 기대하는 매개변수와 일치해야 한다.**

✍ **Exmple**

```typescript
function buildName(firstName: string, lastName?: string) {
  if (lastName) {
    return firstName + ' ' + lastName;
  } else {
    return firstName;
  }
}

let resultOne = buildName('lee');
let resultTwo = buildName('lee', 'song');
// let resultThree = buildName('lee', 'sone', '~');
```

### **\(6\). 나머지 매개 변수 \(Rest** Parameters\)

때로는 다른 매개 변수를 그룹 지어 작업하기 원하거나, 함수가 최종적으로 얼마나 많은 매개변수를 취할지 모를 때 사용한다.

✍ **Exmple**

```typescript
function buildFullName(firstName: string, ...restOfName: string[]) {
  return firstName + '' + restOfName.join('');
}

let employName = buildFullName('song', 'kim', 'lee', 'jun');

let buildNameFun: (fname: string, ...rest: string[]) => string = buildFullName;
```



