# 📄 JavaScript Iteration protocol part2

**ES6**에서 도입된 **이터레이션 프로토콜\(Iteration protocol\)**은 데이터 컬렉션을 순회하기 위한 **프로트콜\(미리 약속된 규칙\)**이다. 이터레이션 프로트콜은 준수한 객체는 `for ~ of` 문으로 순회가 가능하다.

**이터레이션 프로토콜**에는 **이터러블 프로토콜\(Iterable protocol\)**과 **이터레이터 프로토콜\(Iterator protocol\)**이 있다.

### 1. for ~ of 문 정의

`for ~ of` 문은 내부적으로 **Iterator next method** 를 호출하여 **Iterable**을 순회하며 **next method**가 반환한 **Iterator Iresult object** **value property value** 을 `for ~ of`문의 변수에 할당한다.

**Iterator Iresult object**의 **done** 프로퍼티 값이 `false`이면 **Iterable**의 순회를 계속하고 , `true`이면 **Iterable**의 순회를 중단한다.

✍ **Exmple - for ~ of**

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

