# 📄 React Hooks - useState,useEffect,useRef

## 1. HOOK 정의

**HOOK**을 사용하면 functional component에서도 state와 React의 여러 기능을 사용할 수 있다.

**HOOK**를 사용하는 이유는 class component의 코드의 재사용과 코드 구성을 어렵게 만들 뿐만 아니라,   
React를 배우는데 큰 진입 장벽이라고 판단했기 때문이다.

### \(1\). HOOK 사용 시  규칙

React functional component 안에서만 사용해야 된다.

 컴포넌트 안의 반복문, 조건문, 중첩된 함수 안에서는 **HOOK**를 사용할 수 없다.

## 2. useState\(\)

`useState()`를 사용하면 함수형 컴포넌트에서도 상태\(state\)를 설정할 수 있다.

`useState()`는 전달 받는 인자로 state의 초기 값을 설정한다.

초기 값은 함수형 컴포넌트가 첫 렌더링 될 때 딱 한 번만 사용된다

{% code title="Syntax" %}
```jsx
const [state, setState] = React.useState(initialValue);
```
{% endcode %}

```jsx
import React, { useState } from 'react';

const Counter = props => {
  const [count, setCount] = useState(0);
  return (
    <div className="counter">
      <p>{count} click.</p>
      <button 
        type="button" 
        onClick={() => setCount(count + 1)}
      >
        click 
      </button>
    </div>
  )
}
```

### \(2\). 하나의 이상의 state 설정

필요하다면 functional component 에서 1개 이상의 state를 설정해 사용할 수 있다.

```jsx
const Counter = props => {
  const [count, setCount] = useState(0);
  const [userInfo, updateUserInfo] = useState(props.userInfo || null);
  return (...)
}
```

### \(3\). this.state와 useState\(\)의 차이

**functional componen**t의 `useState()`는 state의 상태를 변경할 때 마다 `setState()`로 개별적으로 요구된다.

반면, **class component**의 `this.state` 는 `this.setState()`는 상태의 일부 데이터를 변경하고 합친다는 점이 다르다.

## 3. useEffect\(\) 

{% hint style="info" %}
**class component**의 생명주기\(LifeCylcle\)과 같은 동일한 의미이다.
{% endhint %}

`useEffect()`는 **functional componet**의 Lifecycle 이다.

### \(1\). Component Mount 될 때에만 실행할 경우

`useEffect()` 에서  설정한 함수가 컴포넌트가 화면에 가장 처음 렌더링 될 때만 실행되고, 업데이트 할 경우에는 실행할 필요가 없는 경우엔 함수의 **두 번째 파라미터로 비어 있는 배열을 넣어주면 된다.**

{% code title=" Example : Only Run Once, on Mount" %}
```jsx
import React, { useState, useEffect } from 'react';

useEffect(() => {
    console.log('Run only when component are mount');
}, []);
```
{% endcode %}

### \(2\)  특정 값이 업데이트 될 때에만 실행하고 싶을 경우

`useEffect()` 사용할 때 특정 값이 변경될 때만 호출하고 싶을 경우에 사용한다.

**props** 안에 들어 있는 **value**의 값이 바뀔 때에만 특정 작업을 수행하고 싶을 경우,  `useEffect()` 의  두 번째 매개변수로 전달되는 **배열 안에 검사하고 싶을 값을 넣어주면 된다.**

{% code title=" Example : Run useEffect on State Change" %}
```jsx
useEffect(() => {
    console.log('Outputs only when the value of the name changes.');
    console.log('name')
}, [name]);
```
{% endcode %}

### \(3\). Component Unmount, Update 되기 직전에 작업을 실행하고 싶을 경우

`useEffect()`는 기본적으로 렌더링 되고난 후 직후마다 실행되며, 배열에 무엇을 넣느냐에 따라서 실행 되는 조건이 달라진다.

컴포넌트가 **unmount** 되기 전, 또는 **update** 되기 전에 어떠한 작업을 수행하고 싶다면 **cleanup function**를 반환 해주어야 한다.

{% code title="Example : Performs the component before it is unmount or update" %}
```jsx
useEffect(() => {
    console.log('Outputs only when the value of the name changes.');
    console.log('name')
    
    return () => {
        console.log('It is performed immediately before the component is update.');
        console.log('name');
    };
}, [name]);
```
{% endcode %}

### \(4\) useEffct 정리 <a id="reference"></a>

1.  화면이 처음 떴을 때만 실행
   * deps\[ \] 빈 배열을 넣을 때, componentDidmount 처럼 실행한다.  
2.  화면이 사라질 때
   * componentWillUnmount\(\) 처럼 실행한다.
3.   deps에 넣은 의존값이 업데이트 되었을 때 실행

   * componentDitUpdate\(\) 처럼 실행한다.

## 4. useRef\(\)

 `useRef()`는 실제 DOM 노드를 참조\(ref\)할 경우 사용하며, 참조 대상의 변경이 필요할 경우 `.current` 속성을 사용한다.

 `useRef()`를 사용해 실제 DOM Node를 조작한 경우, 컴포넌트가 다시 그려지지 않으므 주의해야된다. \(state, props가 변경되어야 업데이트 된다.\)  


```jsx
import React, { useRef } from 'react';

function FileInput(props) {
  // 실제 DOM NODE 참조(Ref)
  const domFileInputEl = useRef(null);
  const domButtonEl = useRef(null);
  // event listener
  function handleSubmit(e) {
    e.preventDefault();
    console.log(`선택된 파일: ${domFileInputEl.current.files[0].name}`);
    domButtonEl.current.setAttribute('disabled', 'disabled');
    domButtonEl.current.innerText = '전송 됨';
  }
  // render
  return (
    <form onSubmit={handleSubmit}>
      <label>
        업로드:
        <input type="file" ref={domFileInputEl} />
      </label>
      <br />
      <button type="submit" ref={domButtonEl}>전송</button>
    </form>
  );
}
```



##  

### Reference <a id="reference"></a>

 useEffect 완벽가이드\(번역\) [→\(SITE\)﻿](https://www.daleseo.com/react-router-basic/)







\_\_



