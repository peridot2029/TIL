# 📄 Redux Reducers, Store

## 1. Reducers 정의

리듀서 \(reducer\)는 변화를 일으키는 함수로 `action, state` 두 개의 매개변수를 받는다.  `dispathch`에서 전달된 action type를 확인하고, 그에 맞는 동작을 한다.

### \(1\) Root Reducer 

하나로 합쳐진 reducers를 **root reducer** 라고 부른다.

### \(2\) Sub Ruducer

여러 개 나뉘어진 reducers를 **sub reducer** 라고 부른다.

✍ **Exmple**

```jsx
function reducer(state, action){
	// state update logic
	return alteredState;
}
```

## 2. Store

스토어 \(store\)는 한 애플케이션 단 하나의 스토어를 만든다.

store 안에는 `state`와 `reducer` 가 들어가 있다.

### \(1\) Store method - dispatch\(action\)

**state를 업데이트 하기 위한 방법,**  dispath method는 매개변수로 action를 받는다.

action creater로 return 해준 action 객체를 매개변수로 받아와서 store의 reducer에게 넘겨주는 역할이다.

✍ **Syntax**

```jsx
dispatch(action)
```

### \(2\) Store method - subscribe\(listener\)

{% hint style="warning" %}
리스너\(lister\)는  사용자 액션에 응답하기 위해서 특정 조건 안에서만 dispatch\(\)를 호출해야 한다.  아무런 조건 없이 리스너를 사용하면 무한 루프에 빠질수도 있다. 
{% endhint %}

변경사항에 대한 리스너\(listener\)를 추가한다. 리스너는 액션이 보내져서 상태의 일부가 변경 될 수 있때 마다 호출된다.  이 안에서 현재 상태의 값을 읽으려면  `getState()`를 사용한다.

액션이 보내져서 상태의 값이 바뀔 때 마다, 호출할 콜백 함수 이다.  store의 리듀서는 순수 함수 이므로 상태 트리의 값이 변경되었는지 확인하기 위해, 레퍼런스를 비교할 수 있다.

### \(3\) Store method - getState\(\)

애플리케이션의 현재 상태 트리를 반환한다. store의 리듀서가 마지막으로 반환값과 동일하다.







### Reference <a id="reference"></a>

Redux\(reducers\) [→\(SITE\)](https://redux.js.org/recipes/reducing-boilerplate#actions)

Redux\(store\) [→\(SITE\)](https://lunit.gitbook.io/redux-in-korean/api/store#undefined-5)

[﻿](https://redux.js.org/recipes/reducing-boilerplate#actions)



