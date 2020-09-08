# 📄 React Legacy Lifecycle

## 1. React Legacy Lifecycle

React V17.0 부터는 `componentWillMount()`,`componentWillReceiveProps()`,`componentWillUpdate()` 메서드는 더 이상 사용이 불가능 하다. 위에 메서드 이름  앞에 새로운 `UNSAFE_`를 붙여만 작동한다. 하지만 새로운 코드에서는 사용하지 않는 것을 권장한다.

### \(1\). 변경된 이유

초기 렌더링을 제어하는 방법이 많아져서 혼란이 되고, 오류 처리의 중단 동작이 고려되지 않는 경우가 많으며 메모리 누수가 발생할 수 있다. 또한 React 커뮤니티 내에서 가장 혼란을 일으키는 수명주기이기도 하다.

## 2. React Legacy Lifecycle Methods

### \(1\). UNSAFE\_componentWillMount\(\)

`UNSAFE_componentWillMount()는`마운트가 발생하기 전에 된다. `render()` 실행되기 전에 호출 하므로 이 메서드 내에서 `setState()`를 동기적으로 호출하더라도 추가적인 렌더링은 발생하지 않는다. `state`를 초기화 하려면 `constructor()`를 사용하는 것을 권장한다.

```jsx
UNSAFE_componentWillMount()
```

### \(2\). UNSAFE\_componentWillReceiveProps\(\)

`UNSAFE_componentWillReceiveProps()` 는 마운트된 컴포넌트에 새로운 `props`를 전달 받기 전에 호출된다.  

React는 마운팅 할 때에는`UNSAFE_componentWillReceiveProps()`를 호출하지 않으며, 초기 `props`를 가지지 않는다. 이 메서드가 호출되는 경우는 컴포넌트의 `props`가 변화했을 때 이다.

```jsx
UNSAFE_componentWillReceiveProps(nextProps)
```

### \(3\). UNSAFE\_componentWillUpdate\(\)

`shouldComponentUpdate()`가 불린 이후에 컴포넌트의 렌더링 이루어지기 전에 호출된다. 새로운 `props` 또는 `state` 가 반영되기 직전에 새로운 값을 받는다. 이 메서드는 초기 렌더링에서는 호출되지 않는다.

```jsx
UNSAFE_componentWillUpdate(nextProps, nextState)
```

###  Reference

Component Lifecycle Changes [→\(SITE\)](https://reactjs.org/blog/2018/03/29/react-v-16-3.html#component-lifecycle-changes)

React Legacy Lifecycle Methods [→\(SITE\)](https://reactjs.org/docs/react-component.html)

Update on Async Rendering[ →\(SITE\)](https://reactjs.org/blog/2018/03/27/update-on-async-rendering.html)

