# 📄 JavaScript Reference value - Set, Map

### 1. Reference value

JavaScript reference value

### 2. Set 정의

Set 객체는 값만 모아서 저장한다. 중복된 값은 허용하지 않는다.

Set 객체는 값을 콜렉션으로, 삽입을 순서대로 한다.

Set 객체는 배열\(array\)와 다르게 index 가 없다.

Set 객체는 key, value 모두 값은 의미이다.

Set 객체는 for ~ of를 사용해서 요소를 순회할 수 있다.

**Set의 사용 목적**

✍ **Syntax**

```javascript
new Set([iterable])
```

### 3. Set의 사용

✍ **Exmple**

```javascript
let myArray = [1, 2, 3, 4, 5, 5, 1];
let mySet = new Set(myArray);

console.log(mySet); // [1, 2, 3, 4, 5]
mySet.add(99.99);
mySet.add(12);
mySet.add("string");
mySet.add({changeName :"JavaScript Mastery"});

console.log(mySet.size); // 9
console.log(mySet.has(12)); // true

mySet.delete(12);

for (let item of mySet){
	console.log(item);
}

for(let item of mySet.values()){
	console.log(item);
}

const uniqueArray = [...mySet];

console.log(myArray[3]); // 4
console.log(mySet[3]); // undefined
```

### 4. WeakSet\(\)

Set 객체와 유사하다.Set 객체와 다르게 객체\(Object\)만 수집할 수 있다.

약한 참조 이루어져 메모리 누수를 예방할 수 있다.

### 5. Map 정의

**반복 가능한 객체\(Iterator Object\)**

**Map Object**는 **\[key, value\]** 형식이루어진 리스트 이다

**Map Object**는 **string, Symbol\(\)** 외에 다른 타입을 **key**로 사용할 수 있다.

**Map Object**는 기본적으로 Symbol.iterator 을 가지고 있다.

**Map Object**는 `for ~ of` 를 사용해서 순회할 수 있다.

### 6. Map VS Object

#### Map

**Map Object**와 다르게 **삽입 순으로 순서가 보장**된다.

**Map** 기본 `size` 속성으로 쉽게 길이를 얻을 수 있다.

**Map key**는 `Object`와 달리 **key**로 어떤 타입이든 사용 가능하다.

**Map**은 **Iterable protocol** 지원해서 바로 순회가 가능하다.

#### Object

**Object**는 **size**를 기본 하지 못하고, 따로 함수를 만들어야 한다.

**Object**는 **key**로 `Symbol, string`만 가능하다.

### 7. Map 사용

✍ **Exmple**

```javascript
let myMap = new Map([
	["name", "songsong"],
	["surname", "Lee"],
]);

let key = {};

myMap.set("a1", "Hello");
myMap.set(keyObj, "keyObj 관련된 값");
myMap.set(NaN, "not a number");

myMap.delete("a1");

console.log(myMap.size); // 3

map.get(NaN); // not a number

for (let [key, value] of myMap) {
	console.log(key + " = " + value); 
}
```

### 8. WeakMap 정의

**WeakMap Object**는 **key**가 약하게 참조되는 **key/value** 쌍의 컬렉션 이다.

**key Object** 여야만 하나 값은 임의 값이 될 수 있다.

✍**Syntax**

```javascript
new WeakMap([iterable])
```

### 9. Garbage Collector 정의

메모리 생존주기, 필요할 때 할당 한다.

사용한다. \(읽기, 쓰기\)

필요없어지면 해제한다. 즉, 할당된 메모리가 더 이상 필요없을 때 해체하기.

