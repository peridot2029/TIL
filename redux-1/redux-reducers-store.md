# 📄 Redux Reducers, Store

## 1. Reducers 정의

리듀서\(Reducer\)는 변화를 일으키는 함수로 action, state  두 개의 매개변수를 받는다.  dispathch에서 전달된 action type를 확인하고, 그에 맞는 동작을 한다.

### \(1\) Root Reducer 

하나로 합쳐진 reducers를 Root Reducer 라고 부른다.

### \(2\) Sub Ruducer

여러개 나뉘어진 reducers를 Sub Reducer 라고 부른다.

✍ **Exmple**

```jsx
function reducer(state, action){
	// state update logic
	return alteredState;
}
```

## 2. Store

스토어\(Store\)는 한 애플케이션 단 하나의 스토어를 만든다.

Store 안에는 state와 reducer 가 들어가 있다.

Store의 API로는 \(dispath, subscribe, getState\)가 있다.

### \(1\) Store API - dispatch\(action\)

store API 중 하나로,  state를 업데이트 하기 위해서, dispath method는 매개변수로 action를 받는다.

action creater로 return 해준 action를 매개변수로 받아와서 store의 reducer에게 넘겨주는 역할이다.

✍ **Syntax**

```jsx
dispatch(action)
```

### \(2\) Store API - subscribe\(listener\)

store API 중 하나로,  함수 형태의 값을 파라미터로 받아온다.

subscribe 함수에 특정 함수를 전달해주면, 액션이 디스패치 되었을 때 마다 전달해준 함수가 호출된다.

react app에서 redux를 사용하게 될 때, 보통은 이 함수를 직접 사용하는 일은 별로 없다.

그 대신 react-redux 라이브러리에서 제공되는 `connect`함수또는 `useSelector`Hook를 사용하여 redux store의 상태를 구독한다.

### \(3\) Store API - getState\(\)







### Reference <a id="reference"></a>

Redux\(reducers\) [→\(SITE\)](https://redux.js.org/recipes/reducing-boilerplate#actions)

Redux\(store\) [→\(SITE\)](https://redux.js.org/recipes/configuring-your-store#creating-the-store)

[﻿](https://redux.js.org/recipes/reducing-boilerplate#actions)



