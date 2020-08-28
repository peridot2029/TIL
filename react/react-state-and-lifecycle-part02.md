# 📄 React - Life Cycle \(Updating, Unmouting\)

## 1. Life Cycle API 

컴포넌트는 프로세스의 특정 시간에 코드를 실행하는 다양한 Life Cycle API를 제공한다.

**생성 \(Mounting\) →  업데이트 \(Updating\)  → 제거 \(Unmouting\)**  3단계로 분류한다.

![](../.gitbook/assets/screenshot-from-2016-12-10-00-21-26-1%20%281%29.png)

## 2. Update 

컴포넌트의 state, props가 변경되면 업데이트 진행된다. 상위 컴포넌트가 렌더링 되면 하위 컴포넌트도 

다시 렌더링 된다.

### \(1\). componentWillReceiveProps\(\)

{% hint style="warning" %}
React v16.3 이후 부터는`UNSAFE_componentWillReceiveProps()`라는 이름으로 사용된다. 

이 기능은 상황에 따라서 새로운 API [`getDerivedStateFromProps()`](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops)로 대체 될 수도 있다.
{% endhint %}

**컴포넌트 생성 후에** 첫 렌더링을 마친 후 호출되는 API로 컴포넌트가 **처음마운트 되는 시점**에서는 호출 되지 않는다.

✍ **Syntax**

```jsx
componentWillReceiveProps(nextProps)
```

### \(1-1\). \[NEW\] [static getDerivedStateFromProps\(\)](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops)

`static getDerivedStateFromProps()`는 React v16.3 이후에 만들어진 라이프 사이클 API이다. 

이 API는 prop로 받아온 값을 state로 동기화 작업을 해줘야 하는 경우에 사용된다.

✍ **Syntax**

```jsx
static getDerivedStateFromProps(nextProps, prevState)
```

### \(2\). shouldComponentUpdate\(\)

컴포넌트가 **업데이트 직전**에 호출되는 API, `prop`또는 `state`를 변경되었을 때 , 재렌더링을 여부를 `return`값으로 결정한다.

✍ **Syntax**

```jsx
shouldComponentUpdate(nextProps, nextState)
```

###  \(**3**\). componentWillUpdate\(\)

{% hint style="warning" %}
React v16.3 이후 부터는 상황에 따라서 새로운  API [`getSnapshotBeforeUpdate()`](https://reactjs.org/docs/react-component.html#getsnapshotbeforeupdate)로 대체 될 수 있다.
{% endhint %}

`shouldComponentUpdate()`가 호출되고 난 후에,  **컴포넌트 업데이트 직전**에 호출 되는  API

새로운 `prop`또는 `state`가 반영되기 직전 새로운 값들을 받는다.



✋ `this.setState()`를 사용하면 무한 루프가 일어나게 되므로 사용하면 안된다.

✍ **Syntax**

```jsx
componentWillUpdate(nextProps, nextState)
```

### \(**3-1**\). \[NEW\] [getSnapshotBeforeUpdate\(\)](https://reactjs.org/docs/react-component.html#getsnapshotbeforeupdate)

 `getSnapshotBeforeUpdate()`API를 통해서 **변화가 일어나기 직전**의 DOM 상태를 가져오고, 여기서 `return` 값은 `componentDidUpdate()`의 세 번째 매개변수로 받아올 수 있게 된다.

✍ **Exmple**

```javascript
 getSnapshotBeforeUpdate(prevProps, prevState) {
    // DOM 업데이트가 일어나기 직전의 시점!
    // 새 데이터가 상단에 추가되어도 스크롤바를 유지하.
    // scrollHeight 는 전,후를 비교해서 스크롤 위치를 설정하기 위함이고,
    // scrollTop 은, 이 기능이 크롬에 이미 구현이 되어있는데, 
    // 이미 구현이 되어있다면 처리하지 않도록 하기 위함이다..
    if (prevState.array !== this.state.array) {
      const {
        scrollTop, scrollHeight
      } = this.list;

      // 여기서 반환 하는 값은 componentDidMount 에서 snapshot 값으로 받아올 수 있다.
      return {
        scrollTop, scrollHeight
      };
    }
  }

  componentDidUpdate(prevProps, prevState, snapshot) {
    if (snapshot) {
      const { scrollTop } = this.list;
      // 기능이 이미 구현되어있다면 처리하지 않는.
      if (scrollTop !== snapshot.scrollTop) return; 
      const diff = this.list.scrollHeight - snapshot.scrollHeight;
      this.list.scrollTop += diff;
    }
  }
```

### \(4\). componentDidUpdate\(\)

 ✋ **업데이트**가 이루어지고 render\(\)가 완료된 후, 실행되는 API

`componentDidUpdate()`를 사용할 때, `setState()`를 주의해야 한다. 그렇지 않으면 무한루프에 빠질수 있다.

```javascript
componentDidUpdate(prevProps, prevState, snapshot)
```

📝 **prevProps**

업데이트 되기 전, prop를 인자로 받을 수 있다. 이전 prop와 변경 여부를 비교하여 확인 후, 추가적인 액션을 설정하는게 유용하다.

📝 **prevState**

업데이트 되기 전, state 정보를 받을 수 있다. 이전 state와 비교하여 실행여부를 결정할 때 주로 사용한다.

📝**snapshot**

`getSnapshotBeforeUpdate()` 구현시, 세번째 인자로 받을 수 있다

## 3. Umount 

해당 되는 컴포넌트의 DOM 상에서 제거될 때 실행되는 API

### \(1\) componentWillUnmount\(\)

최종적으로 **제거**될 때, 실행된다. 컴포넌트 내에서 이루어지는 네트워크 요청, 타이머 이벤트 등 지속적으로 이루어지는 이벤트를 해제하는데 유용하다.

## 4. Error 

### \(1\) componentDidCatch\(\)

{% hint style="warning" %}
React v16.3 이후 부터는 상황에 따라서 에러 발생시 state를 변경하고, render\(\) 에서 해당 처리를 구현하면 된다.
{% endhint %}

render\(\) 함수에서 **오류**가 났을 때 실행할 수 있다.

오류가 발생하면 `componentDidCatch()`실행되게 하고, `state.error()`를 `true`로 설정하게 한다.

render\(\) 에서 `state.error()`의 따라서 오류를 띄어주면 된다.

컴포넌트는 자신의 함수 안에서 오류가 발생하면 잡을 수 없지만, 그 대신에 자식 컴포넌트 내부에서 발생하는 오류들을 잡을 수 있다.

