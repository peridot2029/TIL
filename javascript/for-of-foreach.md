# 📄 JavaScript for~in, for~of, forEach

### 1. for~in 정의

**객체 모든 열거 가능한 속성\(property\)에 대한 반복,** 즉 모든 객체에 사용 가능하다.

단, **key** 값에 접근할 수 있지만, **value** 값에 **접근할 수 있는 방법은 제공하지 않는다.**

✍ **Exmple**

```javascript
const cafeMenu = {
    name: "Green_Grape_Slush",
    kcal: 224.51,
    text: "Tropic Revolution Green Grape Slush",
  };

  let { name, kcal, text } = cafeMenu;

  console.log(name); // Green_Grape_Slush
  console.log(kcal); // 224.51
  console.log(text); // Tropic Revolution Green Grape Slush
```

### 2. for~of 정

`Symbol.iterator`속성을 가지는 컬렉션 전용

`for ~ of` 문은 내부적으로 **Iterator next method** 를 호출하여 **Iterable**을 순회하며 **next method**가 반환한 **Iterator Iresult object** **value property value** 을 `for ~ of`문의 변수에 할당한다.

**Iterator Iresult object**의 **done** 프로퍼티 값이 `false`이면 **Iterable**의 순회를 계속하고 , `true`이면 **Iterable**의 순회를 중단한다.

✍ **Exmple** 

```javascript
for (const item of ['a', 'b', 'c']) {
  console.log(item);
}

for (const letter of 'abc') {
  console.log(letter);
}

for (const [key, value] of new Map([['a', '1'], ['b', '2'], ['c', '3']])) {
  console.log(`key : ${key} value : ${value}`); // key : a value : 1 ...
}

for (const value of new Set([1, 2, 3])) {
  console.log(valu);
}
```



### 3. forEach 정의

오직 Array 객체에서만 사용 가능한 method, 배열의 요소들을 반복하 작업을 수행할 수 있다.

