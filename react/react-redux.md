# 📄 React Redux

### 1. Redux 정의

{% hint style="warning" %}
redux는 react에 종속되어 있지 않다. 그러므로 실제 UI 라이브 러리나 프레임워크에 함께 사용할 수 있다.
{% endhint %}

브라우저에서 하나의 페이지로 어플리케이션을 구현하려면 라우팅 뿐만 아니라 데이터도 다루어야 하는데 리덕스\(Redux\)를 많이 사용한다.



###  2. Redex 개념 정리

리덕스 대략적인 개념만 간략하게 정

### 2-1.  Action

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

### 2-2.  Action creator

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

### 2-3.  Reducer

리듀서\(Reducer\)는 변화를 일으키는 함수 이다. 리듀서는 두 가지의 파라미터를 받는다.

✍ **Exmple**

```jsx
function reducer(state, action){
	// state update logic
	return alteredState;
}

```

### 2-4. Store

스토어\(Store\)는 한 애플케이션 단 하나의 스토어를 만든다.

스토어 안에는 App 의 상태와 리듀서가 들어가 있고, 추가적인 몇가지 내장 함수가 있다.

### 2-5. Dispatch

디스패치\(Dispatch\)는 스토어의 내장 함수 중 하나 이다.

디스 패치는 액션 발생 시키는 곳 이다. 그러므로 디스패치 함수에 액션을 파라미터를 전달한다.

✍ **Syntax**

```jsx
dispatch(action)
```

### 2-6. Subscribe

구독\(Subscribe\) 또한 스토어의 내장 함수 이다.

subscribe 함수는, 함수 형태의 값을 파라미터를 받아 온다. 

subscribe 함수에 특정 함수를 전달해주면, 액션이 디스패치 되었을 때 마다 전달해준 함수가 호출된다.

