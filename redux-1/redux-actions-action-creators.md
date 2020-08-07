# 📄 Redux Actions, Action Creators

## 1. Actions 정의

상태에 어떠한 변화가 필요하게 될 땐, 액션을 발생시킨다. 이는 객체로 표현된다.

액션 객체는 `type`를 필수로 필요하다.

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

## 2. Action Creators 정의

**action creators는 redux의 기능은 아니고, 액션을 만드는 순수 함수 이다.** 

 dispatach에게 action를 전달해줘야 하기 보내야하는데, dispath에 inline으로 action을 사용하는 것은 불편해서,  action 객체를 return 해주는 함수로 만든다.

 아래의 작성한 addTodo는 함수이다. addTodo 자체가 action creators로는 될 수 없다.

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

### Reference <a id="reference"></a>

Redux\(action, action creators\) [→\(SITE\)](https://redux.js.org/recipes/reducing-boilerplate#actions)

[﻿](https://redux.js.org/recipes/reducing-boilerplate#actions)react-redux 정리 [→\(SITE\)](https://redux.js.org/recipes/reducing-boilerplate#actions)





