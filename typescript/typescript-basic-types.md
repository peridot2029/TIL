# 📄 TypeScript - Basic Types

## 1. TypeScript 기본 타입

TypeScript는 JavaScript와 거의 동일한 데이터 타입을 지원하며, 열거 타입을 사용하여 더 편리하게 사용할 수 있다.

### \(1\).  Number

JavaScript 처럼, TypeScript의 모든 숫자는 부동 소수 값이다. 부동 소수에는 `number` 라는 타입이 붙여진다. 이는 16진수, 10진수, 8진수, 2진수 리터럴도 지원한다.

✍ **Exmple**

```typescript
let num: number = 1;
num += 1;
```

### \(2\).  Boolean

✍ **Exmple**

```typescript
const done: boolean = true;
```

### \(3\). String

✍ **Exmple**

```typescript
const message: string = 'hello world';
```

### \(4\). Array

✍ **Exmple**

```typescript
const numbers: number[] = [1, 2, 3];
const messages: string[] = ['hello', 'world'];
```

### \(5\). 튜플 \(Tuple\)

요소의 타입과 개수가 고정된 배열을 표현을 할 수 있다. 단 요소들의 타입이 모두 같을 필요는 없다.

✍ **Exmple**

```typescript
let list: [string, number];

list = ['str', 1];
// list = [1, 'str'];
```

### \(6\).  Enum

C\# 과 같은 언어처럼, `enum`은 값의 집합에 더 나은 이름을 붙여줄 수 있다.

기본적으로 `enum`은 0 부터 시작하여 멤버들의 번호를 매긴다. 멤버 중 하나의 값 또는 모든 값을 수동으로 설정하여 바꿀 수 있다.

✍ **Exmple**

```typescript
enum Color { Red, Green, Blue }
let blueColor: Color = Color.Blue;

enum Info { age = 20, name }
let userAge: string = Info[0];
```

### \(7\). 애니 \(Any\)

`any`는 모든 값을 집어 넣을 수 있는 타입이다. 라이브러리를 넣어할 경우 어떤 값이 들어갈지 모르기 때문에 사용가능 하다.

✍ **Exmple**

```typescript
let notSure: any = 4;
notSure = 'maybe a string instead';
notSure = false;

notSure.ifItExists();
notSure.toFixed(); 
```

### \(**8**\). Void

아무런 타입을 가지지 않아야 할 경우 지정해야 될 타입으로 함수에 변수를 선언할 때 유용하다. 그 이유는 `void`를 사용할 경우 `undefined`  와 `null`를 모두 사용할 수 있기 때문이다.

✍ **Exmple**

```typescript
function warnUse(): void {
  console.log('This is my warning message');
}
```

### \(9\). Null and Undefined

 TypeScript에서 `nudfiend`와 `null`는 둘 다 각 각 자신의 타입으로 사용한다.

✍ **Exmple**

```typescript
let u: undefined = undefined;
let n: null = null;

let mightBeUndefined: string | undefined = undefined;
let nullableNumber: number | null = null;
```

### \(10\).  Never

어떤 다른 타입도 `never`에 사용 불가능하며 오로지 exception과 같이 `throw`되는 함수에 주로 사용한다.

✍ **Exmple**

```typescript
function error(message: string): never {
    throw new Error(message);
}

// 반환 타입이 never로 추론된다.
function fail() {
    return error("Something failed");
}

// never를 반환하는 함수는 함수의 마지막에 도달할 수 없다.
function infiniteLoop(): never {
    while (true) {
    }
}
```

### \(11\). Type Assertions

**타입 단언 \(type assertions\)**은 다른 언어의 타입 변환 \(형 변환\)과 유사하지만, 다른 특별한 검사하거나 재구성 하지는 않는다.

✍ **Exmple**

```typescript
let someValue: any = 'this is a string';
let strLength: number = (<string>someValue).length;

let someValueOne: any = 'this is a string';
let strLengthOne: number = (someValue as string).length;
```

### Reference <a id="reference"></a>

TypeScript 핸드북\(번역\) [→\(SITE\)](https://typescript-kr.github.io/)

