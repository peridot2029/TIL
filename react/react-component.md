# 📄 React Component

### 1. Component 정의

{% hint style="info" %}
React App에서 component가 갖는 의미란 데이터를 입력 받아, DOM Node를 출력하고 하는 함수, 입력 받는 데이터는 [props, state](https://reactjs.org/docs/components-and-props.html) 같은 것들을 의미한다.
{% endhint %}

React App 구성하는 가장 최소한의 단위이다, componets는 개별적인 파일로 분리되어 관리한다.

App을 React로 만든다는 것은 곧 작고 단단한 component 만들고 이 components 유기적으로 연결한다는 것을 뜻한다.

### 2 . Controlled Component 정의

{% hint style="info" %}
**Uncontrolled Component**  :  사용자가 상태를 제어하지 않는 컴포넌트
{% endhint %}

HTML 에서`<input>,<select>`와 같은 **form element**를  사용자 입력을 기반을 state를 관리 및 갱신한다.

state는 일반적으로 component의 state 속성에 유지 되고, `setState()`에 의해 갱신한다.

react component는 form에 발생하는 사용자가 입력값을 제어 한다.  이러한 방식으로 react에 의해 값이 제어되어는 **form element**를 **제어 컴포넌트 \(Controlled Component\)** 라고 부른다.

**✍ Example - single input**

```jsx
class NameForm extends Component {
  state = { value: "" };
  handleChange = (e) => {
    this.setState({ value: e.target.value });
  };
  handleSubmit = (e) => {
    e.preventDefault();
    console.log("A name was submitted : ", this.state.value);
  };
  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input
            type="text"
            value={this.state.value}
            onChange={this.handleChange}
          />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}

```

✍ **Example - Multi input**

`<input>` 여러 개 일 때는, **name** 값을 통하여 각 `<input>`을 구분.

`setState()`내부에는 [**Computed property names**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Computed_property_names) 문법을 사용

```jsx
import React, { Component } from "react";

class PhoneForm extends Component {
  state = {
    name: "",
    phone: "",
  };
  handleChange = (e) => {
    this.setState({ [e.target.name]: e.target.value });
  };
  handleSubmit = (e) => {
    e.preventDefault();
    this.props.onCreate(this.state);

    this.setState({
      name: "",
      phone: "",
    });
  };
  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          <input
            type="text"
						name="name"
            placeholder="name"
            value={this.state.name}
            onChange={this.handleChange}
          />
        </label>
        <label>
          <input
            type="text"
            name="phone"
            placeholder="phone"
            value={this.state.phone}
            onChange={this.handleChange}
          />
        </label>
        <button type="submit">add</button>
      </form>
    );
  }
}

class App extends Component {
  handleCreate = (data) => {
    console.log(data);
  }
  render() {
    return (
      <div>
        <PhoneForm
          onCreate={this.handleCreate}
        />
      </div>
    );
  }
}
```

### 3. PureComponent 정의

PureComponent는 일반 컴포넌트와 유사하지만, react 생명주기 `shouldComponentUpdate()`를 다루는 방식이 다르다.

PureComponent는 `shouldComponentUpdate()` 가 이미 구현되어 있기 때문에, props와 state를 얕은 비교 \(Shallow comparison\) 를 통해 변경된 것이 있을 때만 리렌더링 한다.

PureComponent는 `shouldComponentUpdate()`는 컴포넌트의 하위 트리에 대한 props 갱신 작업을 수행하지 않는다.

✍ **Exmple - When used in the inline function render method, a new function instance is created every time a render is run.**

```javascript
(() => null) === (() => null); // false
```

### 4.  Functional Component 정의

React 16.8 버전이 릴리즈 되면서 **Hooks** 라는 기능으로 React 추가되었다.

Hooks는 Class Component 없이, **Functional componen**t로만 App을 구성할 수 있다.

### 5. react.memo\(\) 정의

component가  react.memo\(\)로 래핑 될 때, react는 component를 렌더링 하고, 결과를 모아서 메모이징 \(memoizing\)한다. 

그리고 다음 렌더링이 일어날 때 props가 같다면, react는 메모이징 된 내용을 재사용한다.

react.memo\(\)는 props 혹은 props의 객체를 비교할 때 **얕은\(Shallow\) 비교**를 한다.

즉, React는 componet를 렌더링 하지 않고 마지막으로 렌더링된 결과를 재사용 한다.

비교 방식을 수정할 때에는 두 번째 매개 변수로 비교함수를 만들어 넘겨주면 된다.

함수형 컴포넌트에 적용되어 같은 props에 같은 렌더링 결과를 제공한다.

함수형 컴포넌트가 같은 props를 자주 렌더링 될거라 예상될 때 사용하는 게 가장 좋다.

  
✍ **Syntax**

```javascript
react.memo(Component, [areEqual(prevProps, nextProps)])
```



### Reference <a id="reference"></a>

컴포넌트 제대로 만들기 [→\(SITE\)﻿](https://hyunseob.github.io/2019/06/02/react-component-the-right-way/)

리액트 성능 향상 시키기 \(PureComponent\) [→\(SITE\)﻿](https://wonism.github.io/react-pure-component/)





