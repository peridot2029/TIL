# 📄 React - state, setState, Life Cycle - Mounting

## 1. state 

`state`는 **불변 객체\(Immutable object\)**이다.

새롭게 교체하는 방법은 `setState()`를 사용해서 업데이트및 교체한다.

`state`는 **sub component**에 `props`로 전달할 수 있다.

 ✋ class component `state`는 class 안에서만 접근 가능하다.

## 2. setState\(\) 

**인지 성능 \(perceived performance\)**의 향상을 위해 React는 API의 실행을 지연 시키고 여러 컴포넌를 한 번에 갱신 시킬 수 있다.

React는 `state` 변화가 즉시 적용되는 것을 보장하지 않는다.

 ✋setState\(\)는 compoent를 갱신하는 데 있어서 즉각적인 명령이 아니라 요청을 보낸다. 즉, 컴포넌트는 항상 즉각적으로 업데이트 되지 않는다.

## 3. Life Cycle API

컴포넌트는 프로세스의 특정 시간에 코드를 실행하는 다양한 Life Cycle API를 제공한다.

**생성 \(Mounting\) →  업데이트 \(Updating\)  → 제거 \(Unmouting\)**  3단계로 분류한다.

![](../.gitbook/assets/screenshot-from-2016-12-10-00-21-26-1.png)

## 4. Mounting 

리액트 컴포넌트가 인스턴스 \(Instance\)로 생성되어 DOM tree 에 삽입되어 브라우저에 나타나는 것을 마운트 \(mount\)라고 한다.

### \(1\). constructor\(\)

컴포넌트가 새로 생성 될 때 한 번만 실행하는 생성자 메서, `constructor`는 `this.state`의 초기값 적용, 인스턴스에 이벤트 처리 메서드를 바인딩 하기 위해 사용한다.

### \(2\).[ static getDerivedStateFromProps\(\)](https://ko.reactjs.org/docs/react-component.html#static-getderivedstatefromprops)

`getDerivedStateFromProps()`는 React v16.3 이후에 만들어진 라이프 사이클 메서드 이다.

**최초 마운트** 시와 **갱신** 시 모두에서 `render()` 메서드를 호출 하기 직전에 호출된다. state 갱신하기 위한 객체를 반환하거나, null 반환하여 아무것도 갱신하지 않을 수 있다.

🤚 이 메서드는  컴포넌트 인스턴스에 접근 할 수 없다. 또한 이 메서드는 부모 컴포넌트가 다시 렌더링을 발생 시켰을 때 실행되고, 해당 컴포넌트 내에서 지역전인 `setState()`가 발생한 경우는 실행 되지 않는다.

```jsx
static getDerivedStateFromProps(props, state)
```

### \(3\). render\(\)

클래스 컴포넌트에서  반드시 구현하는 메서드로 최종적으로 컴포넌트에서 작업한 결과물 **UI**를 렌더링 하는 메서드 이다.

### \(4\). componentDidMount\(\)

컴포넌트가 마운트된 직후, 즉 DOM  tree 삽입된 직 후 호출된다.

외부에서 데이터를 불러와야 할 때 사용하기 적절하다.

 ✋DOM Node가 있어야 하는 초기화 작업 componentDidMount\(\)에서 이루어지면 안된다.

{% hint style="danger" %}
기존에 사용 되었던 메서드 이지만 이제는 사용하면 안되는 메서드

[`UNSAFE_componentWillMount()`](https://ko.reactjs.org/docs/react-component.html#unsafe_componentwillmount)
{% endhint %}



