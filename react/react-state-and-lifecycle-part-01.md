# 📄 React - state, setState, Life Cycle - Mounting

## 1. state 

state는 **불변 객체\(lmmutable object\)**이며, 컴포넌트의 데이터를 state에 넣을 수 있다. state의 데이터는 변경 가능하며, 변경 할 때에는 setState\(\)를 사용한다.  

 ✋ class component의 state를 사용할 때에는 `this.state`로 사용한다.

### \(1\). state 와 props의 차이점

`props`와 `state`는 JavaScript의 객체이다. 두 객체 모두 렌더링 결과물에 영향을 주는 정보를 갖고 있다. `props`는 함수의 매개변수 처럼 컴포넌트에 전달된다.  반면에 `state`는 함수 내에서 선언된 변수 처럼 컴포넌트 안에서 관리된다.

### \(2\). this.state와 useState의 차이점

함수형 컴포넌트에서 `state`의 상태를 변경할 때에는 `setState()`로 개별적으로 요구된다. 반면에 클래스 컴포넌트에서 사용하는 `this.state`는`this.setState()`를 사용함으로써 상태의 일부 데이터를 변경하고 합친다 점이 다르다.

## 2.[ setState\(\)](https://ko.reactjs.org/docs/react-component.html#setstate)

> **동기 \(Synchronous\) -** 동시에 일어나는 뜻을 의미, 요청과 그 결과가 동시에 일어난다.
>
> **비동기 \(Asynchronous\) -** 동시에 일어나지 않는  뜻을 의미, 요청과 그 결과가 동시에 일어나지 않는다.

state를 변경하기 위해서는`setState()`를 사용하고 이는 **비동기**적으로 작동한다.  즉, `setState()`는 컴포넌트를 갱신 하는데 있어서 **즉각적인 명령이 아니라 요청을 보냄으로써 여러 컴포넌트를 한 번에 갱신 시킬 수 있다.**  

 🤚 React는 state 변화가 즉시 적용되는 것을 보장하지 않는다.  ****

```jsx
setState(updater, [callback])
```

## 3. Life Cycle API

컴포넌트는 프로세스의 특정 시간에 코드를 실행하는 다양한 Life Cycle API를 제공한다.

**생성 \(Mounting\) →  업데이트 \(Updating\)  → 제거 \(Unmouting\)**  3단계로 분류한다.

![](../.gitbook/assets/screenshot-from-2016-12-10-00-21-26-1.png)

## 4. Mounting 

리액트 컴포넌트가 인스턴스 \(Instance\)로 생성되어 DOM tree 에 삽입되어 브라우저에 나타나는 것을 마운트 \(mount\)라고 한다.

### \(1\). constructor

컴포넌트가 새로 생성 될 때 한 번만 실행하는 생성자 메서, `constructor`는 `this.state`의 초기값 적용, 인스턴스에 이벤트 처리 메서드를 바인딩 하기 위해 사용한다.

### \(2\).[ static getDerivedStateFromProps](https://ko.reactjs.org/docs/react-component.html#static-getderivedstatefromprops)

`getDerivedStateFromProps()`는 React v16.3 이후에 만들어진 라이프 사이클 메서드 이다.

**최초 마운트** 시와 **갱신** 시 모두에서 `render()`메서드를 호출 하기 직전에 호출된다. state 갱신하기 위한 객체를 반환하거나, null 반환하여 아무것도 갱신하지 않을 수 있다.

🤚 이 메서드는  컴포넌트 인스턴스에 접근 할 수 없다. 또한 이 메서드는 부모 컴포넌트가 다시 렌더링을 발생 시켰을 때 실행되고, 해당 컴포넌트 내에서 지역전인 `setState()`가 발생한 경우는 실행 되지 않는다.

```jsx
static getDerivedStateFromProps(props, state)
```

### \(3\). render

클래스 컴포넌트에서  반드시 구현하는 메서드로 최종적으로 컴포넌트에서 작업한 결과물 **UI**를 렌더링 하는 메서드 이다.

### \(4\). componentDidMount

컴포넌트가 마운트된 직후, 즉 DOM  tree 삽입된 직 후 호출된다.

외부에서 데이터를 불러와야 할 때 사용하기 적절하다.

 ✋DOM Node가 있어야 하는 초기화 작업 componentDidMount\(\)에서 이루어지면 안된다.

{% hint style="danger" %}
아래의 메서드는 기존에 사용되었지만 이제는 사용하면 안된다.

[`UNSAFE_componentWillMount()`](https://ko.reactjs.org/docs/react-component.html#unsafe_componentwillmount)
{% endhint %}

### Reference <a id="reference"></a>

React.Component [→\(SITE\)](https://ko.reactjs.org/docs/react-component.html)

