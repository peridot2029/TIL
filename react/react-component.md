# 📄 React - Controlled Component

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

`<input>` 여러 개 일 때는, **name** 값을 통하여 각 `<input>`을 구분.

`setState()`내부에는 [c**omputed property names**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Computed_property_names) 문법을 사용

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

### Reference <a id="reference"></a>

컴포넌트 제대로 만들기 [→\(SITE\)﻿](https://hyunseob.github.io/2019/06/02/react-component-the-right-way/)

리액트 성능 향상 시키기 \(PureComponent\) [→\(SITE\)﻿](https://wonism.github.io/react-pure-component/)

 React.memo\(\) 현명하게 사용하기 [→\(SITE\)](https://ui.toast.com/weekly-pick/ko_20190731/)





