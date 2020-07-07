# 📄 JavaScript Function - call, apply, bind

### 1. call 정의

함수를 호출 할 때, 첫 번째 인자에 `this`키워드 설정, 두 번째 부터는 **배열이 아닌 각 인자**로 받는다.

✍ **Syntax**

```javascript
func.call(thisArg[, arg1[, arg2[, ...]]])
```

### 2. apply 정의

함수를 호출 할 때,  첫 번째 인자 `this` 키워드 설정, 두 번째 인자로는 배열이 받는다.

✍ **Syntax**

```javascript
func.apply(thisArg, [argsArray])
```

### 3. bind 정의

`bind`  method가 호출되면 새로운 함수를 생성, 첫 번째 인자 `this` 키워드 설정, 나머지 인자들은 `bind`된 함수의 인수로 제공된다.

✍ **Syntax**

```javascript
func.bind(thisArg[, arg1[, arg2[, ...]]])
```

### Reference <a id="reference"></a>

bind [→\(MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)\)

