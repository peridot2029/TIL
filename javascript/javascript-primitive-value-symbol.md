# 📄 JavaScript Primitive value - Symbol

### 1. Primitive Value

JavaScript primitive value

### 2. Symbol의 정의

**Primitve value** , 유일무이 하고 고유한 존재이다.

`Symbol()`로 부터 반환되는 **모든 심볼 값은 고유**하다

**비공개 멤버 \(Private Member\)**로 열거 대상에서 제외된다.

`Symbol()` 암묵적 형변환이 불가능 하다.

✍ **Syntax**

```javascript
Symbol([description])
```

### 3. Symbol의 생성

* **Symbol\(\[string\]**\) - 문자열이 아닌 타입은 자동으로 `toString()` 처리.

✍ **Exmple**

```javascript
const sb1 = Symbol();
const sb2 = Symbol();
const sb3 = Symbol(33);

console.log(sb1 === sb2); // false
console.log(sb3 === 33); // fasle

const obj = { a : 1 };
const sb4 = Symbol(obj);

console.log(sb4); // Symbol([object Object])
console.log(obj.toString()); // [object Object]

const sb5 = Symbol(null);
console.log(sb5); // Symbol(null);
console.log(typeof sb5); symbol 
```

```javascript
const obj = {
    [Symbol("1")]: true,
    "02": true,
    "10": false,
    [Symbol("2")]: true,
};

const keys = [];
for (const key in obj) {
	keys.push(key);
}

console.log(keys); // ["10", "02"]
```

```javascript
const sym3 = Symbol();

// Uncaught TypeError: Cannot convert a Symbol value to a string
console.log(sym3 + "a");
```

### 4. Symbol 객체 프로퍼티 활용

✍ **Exmple**

```javascript
const x = () => {
	const a = Symbol("a");
    return {
      [a]: 10
			 a: a 
	};
};

const y = x();
console.log(y); // {Symbol(a):10}

console.log(y.a); // undefined
console.log(y["a"]); // undefined
console.log(y[Symbol("a")]; // undefined
```

```javascript
const NAME = Symbol("이름");
const GENDER = Symbol("성별");

const songs = {
	[NAME]: "song",
  [GENDER]: "female",
	age: 29,
};

const juns = {
	[NAME]: "jun",
	[GENDER]: "male",
	age: 2,
};

console.log(songs); // {age: 29, Symbol(이름): "song", Symbol(성별): "female"}
console.log(juns); // {age: 2, Symbol(이름): "jun", Symbol(성별): "male"}

console.log(songs[NAME], juns[NAME]); //song, jun 
```

### 5. Symbol 프로퍼티 키로 할당한 심볼 탐색\(접근\)

```javascript
const NAME = Symbol("이름");
const GENDER = Symbol("성별");

const songs = {
	[NAME]: "song",
  [GENDER]: "female",
	age: 29,
};

const juns = {
	[NAME]: "jun",
	[GENDER]: "male",
	age: 2,
};

console.log(songs); // {age: 29, Symbol(이름): "song", Symbol(성별): "female"}
console.log(juns); // {age: 2, Symbol(이름): "jun", Symbol(성별): "male"}

console.log(songs[NAME], juns[NAME]); //song, jun 

for(const prop in juns) {
	console.log(prop, juns[prop]); // age 2
}

Object.keys(juns).forEach((key) => {
 console.log(key, juns[key]); // age 2
});

Object.getOwnPropertyNames(juns).forEach((key) => {
	console.log(key, juns[key]); // age 2
});

Object.getOwnPropertySymbols(juns).forEach((key) => {
	console.log(key, jun[key]); // Symbol(이름) "jun", Symbol(성별) "male"
});

Reflect.ownKeys(jun).forEach((key) => {
	console.log(key, jun[key]); // age 2, Symbol(이름) "jun", Symbol(성별) "male"
});
```

### 6. Symbol.for\(\)

`Symbol.for()` 사용하는 이유는 어떤 한 곳에서 `Symbo()`을 만들고 다른 곳 에서 `Symbol()`에 접근하기 위함이다.

`Symbol()`과 다르게 , **심볼 레지스트리 리스트**에 심볼을 만든다.

`Symbol.for()`는 또한 매 호출 마다 새로운 심볼을 만들지 않는다.

**현재 레지스트리**에서 해당 키를 가진 `Symbol()`이 있는 먼저 검사한다.

있다면 그 `Symbol()`을 반환한다. 없다면 **새로운 전역 심볼** 만든다.

✍ **Syntax**

```javascript
Symbol.for(key)
```

✍ **Exmple**

```javascript
const sb1 = Symbol.for("Symbol"); // create a new global symbol
const sb2 = Symbol.for("Symbol"); // return the sb1 symbol
const sb3 = Symbol.for("Sybol Name");

console.log(sb1 === sb2); // true 
console.log(sb1 === sb3); // false
```

