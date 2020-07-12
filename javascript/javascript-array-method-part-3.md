# 📄 JavaScript Array method part 3

### 1. array.every\(\)

배열 안의 **모든 요소**가 주어진 판별 함수를 통과하는지 테스트 한다.

빈 배열\(\[ \]\) 호출하면 무조건 `true`를 반환한다.

✍ **Syntax**

```javascript
array.every(callback[, thisArg])
```

✍ **Exmple**

```javascript
const arr = [1,2,3,4,5];
const product = arr.every((x,y) => x < 10); // true, All values less than 10
```

### 2. array.some\(\)

배열 안의 **어떤 요소**라도 주어진 판별 함수를 통과하는지 테스트한다.

빈 배열 \(\[ \]\) 호출하면 무조건 `false`를 반환한다.

✍ **Syntax**

```javascript
array.some(callback[, thisArg])
```

✍ **Exmple**

```javascript
const arr = [1,2,3,4,5];
const product = arr.some((x) => x % 2 === 0); // true, There is an even number in the element.
```

### 3. array.includes\(\)

배열이 특정 요소를 포함하고 있는지 판별한다.

✍ **Syntax**

```javascript
array.includes(valueToFind[, fromIndex])
```

✍ **Exmple**

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const isOrange = fruits.includes("Orange", 1); // true
const isApple = fruits.includes("Apple", 0); // false
```

### 4. array.indexOf\(\)

배열에서 지정된 요소를 검색하고, 해당 첫 번째 인덱스를 반환한다.

시작 위치가 지정되지 않은 경우, 시작에서 시작하고 배열의 끝에서 검색을 종료한다.

만약 존재하지 않으면 -1를 반환한다.

✍ **Syntax**

```javascript
array.indexOf(searchElement[, fromIndex])
```

✍ **Exmple**

```javascript
const dataType =["NaN", "String", "Number", "Boolean", "String"];

console.log(dataType.indexOf("NaN")); // 0
console.log(dataType.indexOf("String", 2)); // 4, start from index 2
console.log(dataType.indexOf("Boolean", 3)); // 3, start from index 3
```

### 5. array.lastIndexOf\(\)

배열에서 주어진 값을 발견할수 있는 마지막 인덱스를 반환한다.

만약 존재하지 않으면 -1를 반환한다.

✍ **Syntax**

```javascript
array.lastIndexOf(searchElement[, fromIndex])
```

### 5. array.findIndex\(\)

주어진 판별 함수를 만족하는 배열의 첫 번째 요소에 대한 index를 반환한다.

만약 존재하지 않으면 -1를 반환한다.

✍ **Syntax**

```javascript
array.findIndex(callback(element[, index[, array]])[, thisArg])
```

