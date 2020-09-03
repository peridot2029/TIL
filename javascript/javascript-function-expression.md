# 📄 JavaScript - Function Expression

## 1.  **anonymous function** 

**익명 함수\(anonymous function\)**는 이름이 없는 함수로,  즉시 실행이 필요할 경우 사용한다.

괄호쌍이 익명 함수를 감싸서 함수 선언을 함수 표현식으로 표현될 수 있다. 

그러므로 단순한 익명 함수를 전역 스코프 \(global scope\)에서 선언하지 않고 어디서든 익명 함수 표현식을 가질 수 있다. 또한 익명 함수는 나중에 다시 호출할 수 없다.

**IIFE**를 사용하는 주된 이유는 변수를 전역으로 선언하는 것을 피하기 위해서 이다.

```javascript
(function() {
    console.log("this is anonymous function");
})();

```

## 2. Inline function 정의

**인라인 함수 \(lnline function\)**는 함수명 대신에 변수에 함수를 할당한다.

함수를 할당 받은 객체를 통해 함수를 호출 할 수 있다.

일반 함수의 경우에는 JavaScript engine이 코드 전체를 **파싱 \(parsing\)**하는 단계에서 생성된다.

인라인 함수는 변수에 대입되는 방식 이므로 **런타임 \(runtime\)**시에  생성된다.

인라인 함수는 특정 변수에 할당 되므로, 이 변수를 이용하여 다른 곳에서도 재사용 가능 하다.

하지만 익명 함수의 특정 영역에서 한정되어 정의 되기 때문에 다른 곳에서 재사용이 불가능하다.

```javascript
let funOne = function () {
    console.log("this is lnline function");
}
```

