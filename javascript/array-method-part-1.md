# 📄 Array method part 1

### 1. Array.from\(\)

* **유사 배열 객체 \(array-like object\)** 또는 **반복 가능한 객체**를 얕게 복사해 **새로운 Array** 객체를 만든다.

✍ **Syntax**

```javascript
Array.from(arrayLike[, mapFn[, thisArg]])
```

### 2. array.concat\(\)

* 기존 배열에 `concat()`를 사용하게 되면 **전달 인자**를 추가한 **새로운 배열**을 반환한다.
* 전달인자로 **배열을 전달**하게 되면, 배열 안의 원소들을 꺼내어 반환하는 배열에 추가한다.
* `concat()`은 `this`나 전달인자로 넘겨진 배열의 내용은 변경하지 않는다.
* 대신 주어진 배열을 합친 뒤, 그 얕은 복사본을 반환한다.
* **실제 객체가 아닌 참조 객체**

✍ **Syntax**

```javascript
array.concat([value1[, value2[, ...[, valueN]]]])
```

```javascript
const alpha = ['a', 'b', 'c'];
const numeric = [1, 2, 3];

const result = alpha.concat(numeric); // ['a','b','c', 1, 2, 3]
const result2 = numeric.concat(2, [44, 55]); // [1, 2, 3, 2, 44, 55]
```

### 3. array.copyWithin\(\)

* 배열의 일부를 얕게 복사한 뒤, 동일한 배열의 다른 위치에 덮어쓰고 , 그 배열을 반환한다.
* 이 때 배열의 크기\(배열의 길이\)를 수정하지 않고 반환한다.

✍ **Syntax**

```javascript
array.copyWithin(target[, start[, end]])
```

📄 **target**

* **복사한** 시퀀스\(값\)를 넣을 위치 가리키는 0 index ,이때 음수를 지정하면 배열의 끝에서 부터 계산
* `target`이 `array.length` 보다 크거나 같으면 **아무것도 복사하지 않는다**.
* `target`이 `start` 이후라면 복사한 시퀀스를`array.length`에 맞춰 짜른다.

📄 **start \(Optional\)**

복사를 시작할 위치를 가리키는 0 index, start를 지정하지 않으면 배열의 처음부터 복사한다.

📄 **end \(Optional\)**

* 복사를 끝낼 위치를 가리키는 0 index
* `copyWithin`은 `end` 인덱스 이전까지 복사하므로 `end`인덱스가 가리키는 요소는 제외한다.

### 4. array.slice\(\)

* 어떤 배열의 **begin** 부터 **end** 까지에 대한 얕은 복사본을 **새로운 배열 객체**로 반환한다.
* 원본 배열을 바뀌지 않는다.

✍ **Syntax**

```javascript
array.slice([begin[, end]])
```

📄 **begin \(Optional\)**

* 0으로 시작하는 추출 시작점에 대한 인덱스
* 음수 인덱스는 배열의 끝에서 부터 길이를 나타낸다.

📄 **end \(Optional\)**

추출을 종료 할 0 기준 인덱스, `slice`는 `end` 인덱스를 제외하고 추출한다.

### 4. array.splice\(\)

* 배열의 기존 요소를 **삭제** 또는 **교체**하거나 새 요소를 **추가**하여, **배열의 내용**을 변경한다.

✍ **Syntax**

```javascript
array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
```

**📄 start**

배열의 변경을 시작할 인덱스

📄 **deleteCount**

배열에서 제거할 요소의 수

📄 **item1, item2**

배열에 추가할 요소, 아무 요소도 지정하지 않으면 `splice()`는 요소를 제거하기만 한다

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

### 5. array.fill\(\)

* 배열의 시작 인덱스 부터 끝 인덱스의 이전까지 정적인 값 하나로 채운다.
* **fill method**의 **`value, start, end` 3**개 인자를 가진다.
* **start**, **end** 옵션으로써 기본 값으로 `0` 과, `this` 객체 `length`를 가진다.

✍ **Syntax**

```javascript
arr.fill(value[, start[, end]])
```

```javascript
let list = ["css", "html", "react"];

// List before result
console.log(list); // ["css", "html", "react"]

arr.fill("change");

// List after result 
console.log(list); // ["change", "change", "change"];
```

```javascript
let list = ["css", "html", "react"];

// List before result
console.log(list); // ["css", "html", "react"]

arr = arr.map(() => {
    return {
      name: "change",
      profession: "Software Developer",
	};
});

arr[0].name = "song";

console.log(list);
// {name: "song", profession: "Software Developer"}
// {name: "change", profession: "Software Developer"}
// {name: "change", profession: "Software Developer"}
```

