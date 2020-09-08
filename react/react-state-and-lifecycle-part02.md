# 📄 React Lifecycle - Updating, Unmouting

## 1. Lifecycle API 

컴포넌트는 프로세스의 특정 시간에 코드를 실행하는 다양한 Lifecycle API를 제공한다.

**생성 \(Mounting\) →  업데이트 \(Updating\)  → 제거 \(Unmouting\)**  3단계로 분류한다.

![](../.gitbook/assets/screenshot-from-2016-12-10-00-21-26-1%20%281%29.png)

## 2. Updating 

props 또는 state가 변경되면 갱신이 발생한다. 즉, 부모 컴포넌트가 렌더링 되면 자식 컴포넌트도 다시 렌더링 된다. 아래의 메서드들은 다시 렌더링 될때 순서대로 호출한다.

### \(1\).[ static getDerivedStateFromProps\(\)](https://ko.reactjs.org/docs/react-component.html#static-getderivedstatefromprops)

### \(2\). shouldComponentUpdate\(\)

 컴포넌트가 다시 렌더링을 해야 할지 말아야 할지 결정하는 메서드 이다.  초기 렌더링 또는 forceUpdate\(\) 호출 시에 이 메서드는 호출되지 않는다. 이 메서드는 렌더링을 방지하여 성능을 최적화 하는 목적으로 사용된다.

```jsx
shouldComponentUpdate(nextProps, nextState)
```

### \(3\). render\(\)

### \(4\). [getSnapshotBeforeUpdate\(\)](https://reactjs.org/docs/react-component.html#getsnapshotbeforeupdate)

`render()`메서드는 호출 후 DOM 변화를 반영하기 직전에 호출되는 메서드 이다. 이 메서드에서 `return` 하는 값을 `componentDidUpdate()의` 세 번째 매개변수 받아올 수 있다.

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

### \(5\). componentDidUpdate\(\)

 리렌더링을 완료한 후 실행되는 메서드이다. 최초 렌더링에서는 호출되지 않는다. 컴포넌트가 업데이트 되었을 시에 DOM을 조작하기 위해 사용한다.

```javascript
componentDidUpdate(prevProps, prevState, snapshot)
```

📝 **prevProps**

업데이트 되기 전, prop를 인자로 받을 수 있다. 이전 prop와 변경 여부를 비교하여 확인 후, 추가적인 액션을 설정하는게 유용하다.

📝 **prevState**

업데이트 되기 전, state 정보를 받을 수 있다. 이전 state와 비교하여 실행여부를 결정할 때 주로 사용한다.

📝**snapshot**

`getSnapshotBeforeUpdate()` 구현시, 세번째 인자로 받을 수 있다

{% hint style="danger" %}
아래의 메서드는 기존에 사용되었지만 이제는 사용해서는 안된다.

[`UNSAFE_componentWillUpdate()`](https://ko.reactjs.org/docs/react-component.html#unsafe_componentwillupdate)

[`UNSAFE_componentWillReceiveProps()`](https://ko.reactjs.org/docs/react-component.html#unsafe_componentwillreceiveprops)
{% endhint %}

## 3. Umounting

해당 되는 컴포넌트의 DOM 상에서 제거될 때 호출한다.

### \(1\) componentWillUnmount\(\)

컴포넌트가 DOM에서 제거되기 직전에 호출되는 메서드 이다. 타이머 제거하거나 데이터 구독 해제 등의 목적으로 사용한다.

🤚 `componentWillUnmout()`가 호출된 컴포넌트는 다시 렌더링 하지 않으므로 `setState()`를 호출 하면 안된다.

## 4. Error 

아래의 메서드들은 자식 컴포넌트를 렌더링 하거나, 자식 컴포넌트 생명주기 메서드를 호출하거나, 또는 자식 컴포넌트 생성자 메서드를 호출하는 과정에서 오류가 발생했을 때 호출된다.

### \(1\).[ static getDrivedStateFromError\(\)](https://ko.reactjs.org/docs/react-component.html#static-getderivedstatefromerror)

하위의 자 컴포넌트에서 오류가 발생했을 때 호출되는 메서드 이다. 이 메서드는 매개변수로 오류를 전달 받고, 갱신된 `state`값을 반드시 반환해야 한다.

```javascript
static getDerivedStateFromError(error)
```

### \(2\).componentDidCatch\(\)

자손 컴포넌트에서 오류가 발생했을 때 호출되면, 두 개를 매개변수를 전달 받는다.

```jsx
componentDidCatch(error, info)
```

📝 **Error**

 ****발생한 오류

📝**Info**

어떤 컴포넌트가 오류가 발생시켰는지 정보를 포함한 componentStack 키를 갖고 있는 객체

### Reference <a id="reference"></a>

React.Component [→\(SITE\)](https://ko.reactjs.org/docs/react-component.html)

### Result Code 

React Lifecyle [→\(CodeSandbox\)](https://codesandbox.io/s/react-lifecycle-o8ezm?file=/src/components/Counter.jsx)





