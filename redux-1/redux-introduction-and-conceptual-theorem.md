# 📄 Redux Introduction and Conceptual theorem

## 1. Redux 정의

브라우저에서 하나의 페이지로 어플리케이션을 구현하려면 라우팅 뿐만 아니라 데이터도 다루어야 하는데redux 를 많이 사용한다.

redux는 react에 종속되어 있지 않다. 그러므로 실제 UI 라이브 러리나 프레임워크에 함께 사용할 수 있다.

##  2. Redux 사용되는 키워드

redux 사용되는 키워드 단어 정리

### \(1\)  Action

상태에 어떠한 변화가 필요하게 될 때에는, 사용자는 액션\(Action\)을 발생 시킨다. 이는 하나의 객체로 표현한다.

✍ **Exmple**

```jsx
{
	type : "ADD_TODO",
	data : { 
		id : 1,
		text : "redux start"
	}
}
```

### \(2\) Action creator

액션 생성함수\(Action creator\)는 액션을 만드는 함수 이다. 파라미터를 받아와서 액션 객체 형태로 만든다.

✍ **Exmple**

```jsx
function addTodo(data){
	return{
		type:"ADD_TODO",
		data
	};
}

// Arrow function Action creator
const changeInput = (text) => ({
	type: "CHANGE_INPUT",
	text,
});
```

### \(3\) Reducer

리듀서\(Reducer\)는 변화를 일으키는 함수 이다. 리듀서는 두 가지의 파라미터를 받는다.

redux를 사용할 때, 여러 개의 reducer를 만들고 이를 합쳐서 **root reducer**를 만들 수 있다.

**root reducer** 안의 작은 리듀서들은 **sub reducer** 라고 부른다.

✍ **Exmple**

```jsx
function reducer(state, action){
	// state update logic
	return alteredState;
}

```

### \(4\) Store

스토어\(Store\)는 한 애플케이션 단 하나의 스토어를 만든다.

스토어 안에는 App 의 상태와 리듀서가 들어가 있고, 추가적인 몇가지 내장 함수가 있다.

### \(5\) Dispatch

디스패치\(Dispatch\)는 스토어의 내장 함수 중 하나 이다.

디스 패치는 액션 발생 시키는 곳 이다. 그러므로 디스패치 함수에 액션을 파라미터를 전달한다.

✍ **Syntax**

```jsx
dispatch(action)
```

### \(6\) Subscribe

구독\(Subscribe\) 또한 스토어의 내장 함수 이다.

subscribe 함수는, 함수 형태의 값을 파라미터를 받아 온다. 

subscribe 함수에 특정 함수를 전달해주면, 액션이 디스패치 되었을 때 마다 전달해준 함수가 호출된다.

react app에서 redux를 사용하게 될 때, 보통은 이 함수를 직접 사용하는 일은 별로 없다.

그 대신 react-redux 라이브러리에서 제공되는 `connect`함수또는 `useSelector`Hook를 사용하여 redux store의 상태를 구독한다.



