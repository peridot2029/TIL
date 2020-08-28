# 📄 React - state, setState,Life Cycle \(Mounting\)

## 1. state 

`state`는 **불변 객체\(Immutable object\)**이다.

새롭게 교체하는 방법은 `setState()`를 사용해서 업데이트및 교체한다.

`state`는 **sub component**에 `props`로 전달할 수 있다.



 ✋ class component `state`는 class 안에서만 접근 가능하다.

## 2. setState\(\) 

**인지 성능 \(perceived performance\)**의 향상을 위해 React는 API의 실행을 지연 시키고 여러 컴포넌를 한 번에 갱신 시킬 수 있다.

React는 `state` 변화가 즉시 적용되는 것을 보장하지 않는다.



 ✋ setState\(\)는 compoent를 갱신하는 데 있어서 즉각적인 명령이 아니라 요청을 보낸다.

즉, 컴포넌트 항상 즉각적으로 업데이트 되지 않는다.

## 3. Life Cycle API

컴포넌트는 프로세스의 특정 시간에 코드를 실행하는 다양한 Life Cycle API를 제공한다.

**생성 \(Mounting\) →  업데이트 \(Updating\)  → 제거 \(Unmouting\)**  3단계로 분류한다.

![](../.gitbook/assets/screenshot-from-2016-12-10-00-21-26-1.png)

## 4. Mounting 

컴포넌트가 새롭게 생성되는 시점,  결과물로 나온 요가 **Virital DOM**에 삽입되고 실제 DOM 업데이트 하기 과정.

### \(1\). constructor\(\)

생성자 메서드로 컴포넌트가 생성 될 때 단 한 번만 실행한다.

주된 역할은 `state`를 선언 및 초기화 그리고 각 종 이벤트를 바인딩\(bing\) 처리한다.

### \(2\). componentWillMount\(\)

{% hint style="warning" %}
React v16.3 이후 부터는 `UNSAFE_componentWillMount()`라는 이름으로 사용된다.
{% endhint %}

React element를 실제 DOM Node에 추가하기 직전에 호출되는 API

### \(2\). render\(\)

최종적으로 컴포넌트에서 작업한 결과물을 반환하는 API

결과물로 나온 요소들은 **Virital DOM**에 마운트 되고, 실제 DOM 업데이트 된다

배열 또는 여러개의 요소를 반환 하고 싶을 때는, **fragments**를 사용할 수 있다.



 ✋ `render()`API 안에서는 `setState()`를 작업해서는 안된다.

### \(3\). componentDidMount\(\)

컴포넌트 결과물이 실제 DOM 에 마운트 된 후 직후, 실행되는 API

외부 라이브러리를 연동하거나, 해당 컴포넌트에서 필요로 하는 데이터 요청을 하기 위해

axios, fetch 등을 통하여 ajax 요청을 하거나, DOM의 속성을 읽거나 직접 변경하는 작업을 진행한다.



 ✋`componentDidMount()` 에서 바로 `setState()`를 실행할 경우, 렌더링이 완료되고 다시 업데이트 하여 또 다시 렌더링 하게 된다. 이 경우에는 사용자는 2번 실행되는 렌더링 과정을 볼 수 없다. 

 그 이유는 브라우저에 화면을 갱신하기 전 실행되기 때문이다.  

2번 렌더링 되는 과정은 성능상 문제를 일으킬 수 있으므로 주의해야 된다.  






