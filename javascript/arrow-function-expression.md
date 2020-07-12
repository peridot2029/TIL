# 📄 JavaScript Arrow function expression

### 1. Arrow function expression 정의

화살표 함수 표현식\(Arrow Function Expression\)은 function 표현에 비해 구문이 짧다.

화살표 함수는 항상 **익명** 이다.

화살표 함수 표현은 **method 가 아닌 곳에 적합**하다. 그래서 **생성자**로 사용할 수 없다.

`this, arguments, super` 또는 `new.target`을 바인딩\(`bind`\) 하지 않는다.

✍ **Exmple**

```javascript
// Same as following :  => { return expression; }
(param1, param2, …, paramN) => { statements }
(param1, param2, …, paramN) => expression

// Parentheses are optional if there is only one parameter
(singleParam) => { statements }
singleParam => { statements }

// Function without parameters requires parentheses
() => { statements }
```

