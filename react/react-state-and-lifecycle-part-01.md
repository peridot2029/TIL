# 📄 React State and Lifecycle part 01

## 1. state 

{% hint style="info" %}
**class component**의 상태 정보, `state`는 **class** 안에서만 접근 가능하다.
{% endhint %}

`state`는 **불변 객체\(Immutable object\)**이다.

새롭게 교체하는 방법은 `setState()`를 사용해서 업데이트및 교체한다.

`state`는 **sub component**에 `props`로 전달할 수 있다.

## 2. setState\(\) 

{% hint style="info" %}
`setState()`는 **component**를 갱신하는데 있어, **즉각적인 명령이 아니라 요청**이다.

즉, **compoent**는 항상 즉각적으로 갱신되지 않는다.
{% endhint %}

**인지 성능 \(perceived performance\)**의 향상을 위해 react는 method의 실행을 지연 시키고 여러 **components**를 한 번에 갱신 시킬 수 있다.

react는 `state` 변화가 즉시 적용되는 것을 보장하지 않는다.

## 3. Lifecycle 

{% hint style="info" %}
**component는 프로세스의 특정 시간에 코드를 실행하는 다양한 Lifecycle Hooks 제공되고 크게 3단계로 진행한다.**

**생성 \(mounting\) → 갱신\(updating\) → 제거 \(unmounting\)**
{% endhint %}

![](../.gitbook/assets/screenshot-from-2016-12-10-00-21-26-1.png)

## 4. Mounting 

{% hint style="info" %}
`componentDidMount()`를 제외한 나머지는 **Virital DOM**을 조작한다.
{% endhint %}

**component**가 새롭게 생성되는 시점, 

결과물로 나온 elements가 **Virital DOM**에 삽입되고 실제 DOM 업데이트 하기 과정.

### \(1\). constructor\(\)

생성자 메서드로 컴포넌트가 생성 될 때 단 한 번만 실행한다.

주된 역할은 state를 선언 및 초기화 그리고 각 종 이벤트를 바인딩\(bing\) 처리한다.

### \(2\). componentWillMount\(\)

{% hint style="warning" %}
React v16.3 이후 부터는 `UNSAFE_componentWillMount()`라는 이름으로 사용된다.
{% endhint %}

React Element를 실제 DOM Node에 추가하기 직전에 호출되는 메서드

### \(2\). render\(\)

{% hint style="warning" %}
render method 안에서 setState\(\)를 작업해서는 안된다.
{% endhint %}

최종적으로 컴포넌에서 작업한 결과물을 반환하는 메서

결과물로 나온 elements를 **Virital DOM**에 mount 되고 실제 DOM 업데이트 된다

배열 또는 여러개의 elements를 반환 하고 싶을 때는, **fragments**를 사용할 수 있다

### \(3\) componentDidMount\(\)

{% hint style="warning" %}
`componentDidMount()`에서 바로 `setState()`를 실행할 경우, 렌더링이 완료되고 다시 업데이트 하여 또 다시 렌더링 하게 된다. 이 경우에는 사용자는 2번 실행되는 렌더링 과정을 볼 수 없다. 그 이유는  브라우저에 화면을 갱신하기 전 실행되기 때문이다.

2번 렌더링 되는 과정은 성능상 문제를 일으킬수 있으므로 주의를 해야된다.
{% endhint %}

component 결과물이 DOM에 mount된 후 직후, 실행되는 method

DOM Node를 확인하고, 초기화 해야 하는 작업이 있는 경우 사용한다.

외부의 데이터를 불러오거나, 네트워크 요청을 보내야 하는 경우 사용한다.



