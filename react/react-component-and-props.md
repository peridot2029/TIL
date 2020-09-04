# 📄 React - Component and Props

## 1. Component

 **컴포넌트**는 UI를 구성하는 조각\(piece\)에 해당되며, 독립적으로 분리되어 **재사용을 됨을 목적으로 사용**된다. React App에서 컴포넌트는 **개별적인 파일로 분리되어 관리**한다.

## 2. Class Component and Functional Component

React를 사용할 때에는 컴포넌트를 `class component` 또는 `functional component` 두 가지로 나눌 수 있다.

### \(1\). Class Component

React  컴포넌트를 class를 정의 하려면 `React.Component`를 상속 받아야 한다.

`render()`는 `React.Component`의 하위 class 에서 반드시 정의해야 하는 API 이다. 

```jsx
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        <h1>Hello, React Component</h1>
      </div>
    );
  }
}

export default App;
```

### \(2\). Functional Component

JavaScript 함수와 유사하다. 컴포넌트 외부로부터 props을 전달 받아 어떻게 UI를 구성해야 할지 설정하여 React 요소\(JSX를 Babel이 변환 처리\)로 반환한다.

```jsx
import React from 'react';

function App() {
  return (
    <div>
      <h1>Hello, React Component</h1>
    </div>
  );
}

export default App;
```

### \(3\). Class ComponentVS Functional Component

React의 세계관에서 함수형 컴포넌트와 클래스형 컴포넌트는 유사하다. 하지만 함수형 컴포넌트에 없는 기능을 추가적으로 클래스형에서 컴포넌트에서 사용할 수 있다.

간단히 정리하면 this, state, LifeCycle Hoop를 클래스형 컴포넌트에서 사용할 수 있다.

## 2. props

컴포넌트에 설정된 임의의 JSX 속성\(type, children 등\)은 React에 의해 컴포넌트에 속성\(props\) 객체로 전달한다.

전달된 전달된 값은 props 객체의 각 **속성**으로 설정된다.

전달된 컴포넌트 속성 객체 props는 컴포넌트 내부에서 컴파일에 활용된다.

### \(1\). props는 읽기 전용 속성이다.

컴포넌트에 전달된 속성\(props\) 객체는 **읽기 전용\(readonly\)**이다. 다시 말해 전달 받은 속성 값을 수정하면 안된다는 말이다. 전달 받은 속성 값을 수정하는 대신 컴포넌트 상태\(state\)를 활용해야 한다.

### Reference

컴포넌트 제대로 만들기 [→\(SITE\)﻿](https://hyunseob.github.io/2019/06/02/react-component-the-right-way/)

