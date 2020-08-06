# 📄 Redux Using

## 1. Redux 3가지 규칙

redux 프로젝트에서 사용하게 될 때 알아둬야할 3가지 규칙 정리

### \(1\) 하나의 애플리케이션 안에는 하나의 스토어가 있다.

하나의 애플리케이션 안에는 단 한개의 스토어를 만들어서 사용한다.

여러 개의 스토어를 만든 것은 가능하기는 하나, 권장 하지는 않는다.

### \(2\) 상태는 읽기 전용이다.

react에서 배열 데이터를 업데이트 할 때, 배열 자체에 push를 직접하지 않고,

기존의 배열은 수정하지 않고, 새로운 배열을 만들어서 교체하는 방식으로 업데이트 한다.

redux도 마찬가지다. 기존의 상태는 건들이지 않고, 새로운 상태를 생성 하여 업데이트 하는 방식으로 한다.

### \(3\) 변화를 일으키는 함수, 리듀서는 순수 함수 이여야 한다.

reducer 함수는 이전 상태와, 액션 객체를 파라미터로 받는다.

이전 상태는 건들이지 않고, 변화를 일으킨 새로운 상태 객체를 만들어서 반환한다.

똑같은 파라미터로 호출된 리듀서 함수는 언제나 똑같은 결과값을 반환해야 한다.

## 2. React Project - Redux 설치 밎 적용

redux-counter 프로젝트 생성 후, react-redux 설치 

✍ **setting** 

```text
$ create-react-app redux-counter
```

✍ **setting**

```text
$ yarn add redux react-redux
```

### \(1\)  Modules 생성

특정 기능을 구현하기 위하여 필요한 액션, 액션 생성 함수, 초기값, 리듀서 함수가 들어가 있는 파일을

**모듈\(Module\)**이라고 부른다.

✍ **store/modules/counter.js**

```jsx
// action type
const INCREMENT = 'counter/INCREMENT';
const DECREMENT = 'counter/DECREMENT';

// action creator function
export const increment = () => ({ type: INCREMENT });
export const decrement = () => ({ type: DECREMENT });

// initialState 
const initialState = 0;

// reducer
function counter(state = initialState, action) {
  switch (action.type) {
    case INCREMENT:
      return {
        ...state,
        number: state.number + 1,
      };
    case DECREMENT:
      return {
        ...state,
        number: state.number - 1,
      };
    default:
      return state;
  }
}
export default counter;
```

### \(2\) combineReducers 로 리듀서 합치기

reducer가 여러개 일때 redux 내장 함수 중 `combineReducers`  를 사용하여 reducer를 하나로 합치는 작업을 한다. 

여러개로 나뉘어진 reducers를 **Sub Reducer** 라고 부른다.

하나로 합쳐진 reducers를 **Root Reducer** 라고 부른다.

✍ **store/modules/index.js** 

```jsx
import { combineReducers } from 'redux';
import counter from './counter';

export default combineReducers({
  counter,
});
```

### \(3\) Store 생성, Provider 를 사용하여 프로젝트에 Store 연결

`store`는 app 시작 되는**src/index.js** 에서 한 번만 만들면 된다.

react 프로젝트에 store를 연동할 때에는 **react-redux** 라이브 러리 안에 있는 `Provider`를 사용한다.

기존 JSX를 `Provider`로 감싸고, store는 props로 `Provider`를 넣어주면 된다.

✍ **index.js** 

```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import { createStore } from 'redux';
import rootReducer from './store/modules';
import { Provider } from 'react-redux';
import registerServiceWorker from './registerServiceWorker';
import App from './App';

const devTools =
  window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__();
const store = createStore(rootReducer, devTools);

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);

registerServiceWorker();
```

### \(4\) connect function 를 사용해서 component store 연동

컨테이너 컴포넌트를 만들때, react-redux 라이브러리에서 connect 함수를 사용한다.

함수의 파라미터에 전달해주는  `mapStateToProps` 는 store 안에 들어있는 값을 prop로 전달해준다.

 `mapDispatchToProps` 함수는 액션을 생성 함수들을 props로 전달해준다.

 **`mapDispatchToProps` 액션 생성 함수는 호출한다고 해서, 상태에 변화가 일어나지는 않는다.** 

**그 대신에 액센 객체를 생성한다. 생성한 액션 객체를 store에게 전달 해주어야 상태에 변화가 발생한다.**

✍ **containers/CounterContainer.js**

```jsx
import React, { Component } from 'react';
import { connect } from 'react-redux';
import Counter from '../components/Counter';
import { increment, decrement } from '../store/modules/counter';

class CounterContainer extends Component {
  handleIncrement = () => {
    this.props.increment();
  };
  handleDecrement = () => {
    this.props.decrement();
  };
  render() {
    const { number } = this.props;
    return (
      <Counter
        value={number}
        onIncrement={this.handleIncrement}
        onDecrement={this.handleDecrement}
      />
    );
  }
}

// props - store state value
const mapStateToProps = ({ counter }) => ({
  number: counter.number,
});

// props - action creatorfunction
const mapDispatchToProps = { increment, decrement };

// component redux connect function
export default connect(
  mapStateToProps,
  mapDispatchToProps
)(CounterContainer);
```

✍ **components/Counter.js**

```jsx
import React from 'react';

const Counter = ({ value, color, onIncrement, onDecrement }) => {
  return (
    <div className='Counter'>
      <h1 style={{ color }}>{value}</h1>
      <button onClick={onIncrement}>+</button>
      <button onClick={onDecrement}>-</button>
    </div>
  );
};

export default Counter;
```

✍ **App.js**

```jsx
import React from 'react';
import CounterContainer from './containers/CounterContainer';

function App() {
  return (
    <>
      <h2>Counter</h2>
      <CounterContainer/>
    </>
  );
}

export default App;
```

###  <a id="reference"></a>

### Reference <a id="reference"></a>

Redux React 함께 사용하 [→\(SITE\)﻿](https://velog.io/@velopert/Redux-3-%EB%A6%AC%EB%8D%95%EC%8A%A4%EB%A5%BC-%EB%A6%AC%EC%95%A1%ED%8A%B8%EC%99%80-%ED%95%A8%EA%BB%98-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0-nvjltahf5e)

React Counter Project [→\(StackBlitz\)﻿](https://stackblitz.com/edit/react-conuter)

