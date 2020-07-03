# 📄 JavaScript Arrow function expression

### 1. Arrow function expression 정의

화살표 함수 표현식\(Arrow Function Expression\)은 function 표현에 비해 구문이 짧다.

화살표 함수는 항상 **익명** 이다.

화살표 함수 표현은 **method 가 아닌 곳에 적합**하다. 그래서 **생성자**로 사용할 수 없다.

`this, arguments, super` 또는 `new.target`을 바인딩\(`bind`\) 하지 않는다.

```javascript
// 다음과 동일:  => { return expression; }
(param1, param2, …, paramN) => { statements }
(param1, param2, …, paramN) => expression

// 매개변수가 하나뿐인 경우 괄호는 선택사항:
(singleParam) => { statements }
singleParam => { statements }

// 매개변수가 없는 함수는 괄호가 필요:
() => { statements }
```

