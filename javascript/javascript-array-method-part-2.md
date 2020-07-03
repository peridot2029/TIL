# 📄 JavaScript Array method part 2

### 1. array.forEach\(\)

배열 전체 순환, 해당 배열의 요소에 직접 어떤 작업을 수행하고 싶을 때 적합하다.

`forEach()`는 배열을 변형하지 않는다. 그러나 **callback**이 변형할 수는 있다.

**method** 수행 후에는 `map(), filter()` 와 다르게 `undefined`를 반환한다.

✍ **Syntax**

```javascript
array.forEach(callback(currentvalue[, index[, array]])[, thisArg])
```

### 2. array.map\(\)

배열 전체 순환, 배열값을 사용해서 **새로운 배열**을 만들고 싶을 때 적합하다.

`map()`은 호출한 배열의 값을 변형하지 않는다. 단, **callback** 함수에 의해서 변형될 수 있다.

**method** 수행 후에는 `forEach()` 와 다르게 새로운 배열을 반환한다.

✍ **Syntax**

```javascript
array.map(callback(currentValue[, index[, array]])[, thisArg])
```

### 3. array.filter\(\)

배열 전체 순환, 배열에서 특정 요소만 모아 새로운 배열을 만들고 싶을 때 적합하다.

`filter()` 호출되는 배열을 변화\(mutate\) 시키지 않는다.

**method** 수행 중 **callback** 에서 `true`를 반환하면, 배열 요소를 추출해서 새로운 배열에 추가하고

**method** 가 종료될 때 추출된 배열 요소만으로 이루어진 새로운 배열을 반환한다.

✍ **Syntax**

```javascript
array.filter(callback(element[, index[, array]])[, thisArg])
```

### 4. array.reduce\(\)

배열 전체 순환, 하나의 결과를 반환, 왼쪽에서 오른쪽 방향으로 진행한다.

reduce 함수의 반환 값은 **누산기\(accumulator\)**에 할당된다.

누산기는 순회 중 유지되므로 결국 최종 결과는 하나의 결과 값이 된다.

✍ **Syntax**

```javascript
array.reduce(callback[, initialValue])
```

📄 **accumulator**

**누산기**는 **callback**의 반환 값을 누적한다. **콜백 이전 반환 값** 또는 **첫 번째 호출**이면서, `initialValue` 설정된 값

📄 **currentValue**

처리할 현재 요소

📄 **array**

reduce 호출한 배열

**📄 initialValue**

**callback**의 처음 호출에서 첫 번째 인수에 되는 제공 값, 그렇지 않으면 빈 배열\(\[ \]\),

**빈 배열**에서 초기값 없이 `reduce()`를 호출 하면 오류가 발생

```javascript
const arr =[1,2,3,4,5];

const product = arr.reduce((x,y) => {
	return x * y;
},2);

// x(2)  * y(1) = 2
// x(2)  * y(2) = 4
// x(4)  * y(3) = 12
// x(12) * y(4) = 48
// x(48) * y(5) = 240
```

