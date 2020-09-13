# 📄 React - Controlled Component, Ref

## 1 . Controlled Component 

{% hint style="info" %}
**uncontrolled component**  :  사용자가 상태를 제어하지 않는 컴포넌트
{% endhint %}

HTML 에서`<input>,<select>`와 같은 **form element**를  사용자 입력을 기반을 state를 관리 및 갱신한다.

state는 일반적으로 component의 state 속성에 유지 되고, `setState()`에 의해 갱신한다.

react component는 form에 발생하는 사용자가 입력값을 제어 한다.  이러한 방식으로 react에 의해 값이 제어되어는 **form element**를 **제어 컴포넌트 \(controlled component\)** 라고 부른다.

{% code title="Example : single input" %}
```jsx
import React, { Component } from "react";

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
{% endcode %}

{% code title="Example : single input" %}
```jsx
import React, { Component } from "react";

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
{% endcode %}

`<input>` 여러 개 일 때는, **name** 값을 통하여 각 `<input>`을 구분.

`setState()`내부에는 [c**omputed property names**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Computed_property_names) 문법을 사용



{% code title=" Example : Multi input" %}
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
```
{% endcode %}

{% code title="Example : Multi input" %}
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
{% endcode %}

{% code title=" Example : Multi input" %}
```jsx
import React, { Component } from "react";

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
{% endcode %}

## 2. Ref

실제 DOM Node를 **참조\(ref**\)할 경우 사용하며, 참조 대상의 변경이 필요할 경우 `.current` 속성을 사용한다. 

### \(1\).  Ref 생성 및 접근

클래스 컴포넌트에서 ref를 사용할 경우 실제  ref를 할당할 변수를 만든 후,  render\(\)에서 요소에 참조 설정

한다.  설정한 ref 요소는 `.current`속성을 사용한다.

### \(2\).  Ref 사용의 경우

* DOM Node에 접근해서 포커스, 미디어 재생 등을 제어 하거나 사이즈를 얻을 경우
* 애니메이션을 직접 실행 시킬 경우
* 그 외 추가적으로는 자식의 state에 부모가 접근할 경우, state로 제어하지 않는 비제어 컴포넌트를 사용할 경우로 나뉜다.

### Reference <a id="reference"></a>

컴포넌트 제대로 만들기 [→\(SITE\)﻿](https://hyunseob.github.io/2019/06/02/react-component-the-right-way/)

리액트 성능 향상 시키기 \(PureComponent\) [→\(SITE\)﻿](https://wonism.github.io/react-pure-component/)

 React.memo\(\) 현명하게 사용하기 [→\(SITE\)](https://ui.toast.com/weekly-pick/ko_20190731/)



### Result Code 

React Controlled Component [→\(CodeSandbox\)](https://codesandbox.io/s/react-lifecycle-o8ezm?file=/src/components/Counter.jsx)





