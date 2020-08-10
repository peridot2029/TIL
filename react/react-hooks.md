# 📄 React Hooks

## 

## 2. useEffect\(\) 정의

{% hint style="info" %}
**class component**의 생명주기\(LifeCylcle\)과 같은 동일한 의미이다.
{% endhint %}

`useEffect()`는 **functional componet**의 Lifecycle 이다.

### \(1\) Component Mount 될 때에만 실행할 경우

`useEffect()` 에서  설정한 함수가 컴포넌트가 화면에 가장 처음 렌더링 될 때만 실행되고, 업데이트 할 경우에는 실행할 필요가 없는 경우엔 함수의 **두 번째 파라미터로 비어 있는 배열을 넣어주면 된다.**

✍ **Example -Only Run Once, on Mount**

```jsx
import React, { useState, useEffect } from 'react';

useEffect(() => {
    console.log('Run only when component are mount');
}, []);
```

### \(2\)  특정 값이 업데이트 될 때에만 실행하고 싶을 경우

`useEffect()` 사용할 때 특정 값이 변경될 때만 호출하고 싶을 경우에 사용한다.

**props** 안에 들어 있는 **value**의 값이 바뀔 때에만 특정 작업을 수행하고 싶을 경우,  `useEffect()` 의  두 번째 매개변수로 전달되는 **배열 안에 검사하고 싶을 값을 넣어주면 된다.**

✍ **Example - Run useEffect on State Change**

```jsx
useEffect(() => {
    console.log('Outputs only when the value of the name changes.');
    console.log('name')
}, [name]);
```

### \(3\) Component Unmount, Update 되기 직전에 작업을 실행하고 싶을 경우

`useEffect()`는 기본적으로 렌더링 되고난 후 직후마다 실행되며, 배열에 무엇을 넣느냐에 따라서 실행 되는 조건이 달라진다.

컴포넌트가 **Unmount** 되기 전, 또는 **Update** 되기 전에 어떠한 작업을 수행하고 싶다면 c**leanup function**를 반환 해주어야 한다.

✍ **Example - Performs the component before it is unmount or update**

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

### \(4\) useEffct 정리 <a id="reference"></a>

1.  화면이 처음 떴을 때만 실행
   * deps\[ \] 빈 배열을 넣을 때, componentDidmount 처럼 실행한다.  
2.  화면이 사라질 때
   * componentWillUnmount\(\) 처럼 실행한다.
3.   deps에 넣은 의존값이 업데이트 되었을 때 실행

   * componentDitUpdate\(\) 처럼 실행한다.

### Reference <a id="reference"></a>

 useEffect 완벽가이드\(번역\) [→\(SITE\)﻿](https://www.daleseo.com/react-router-basic/)







\_\_



