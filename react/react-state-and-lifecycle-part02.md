# 📄React State and Lifecycle part02

### 1. Lifecycle 정의

> **component는 프로세스의 특정 시간에 코드를 실행하는 다양한 LifeCycle Hook 제공되고 크게 3단계로 진행한다.**

> **생성 \(Mounting\) → 갱신\(Updating\) → 제거 \(Unmounting\)**

![](../.gitbook/assets/screenshot-from-2016-12-10-00-21-26-1%20%281%29.png)

### 2. Update 정의

component state, props가 변경되면 update 진행된다

상위 컴포넌트가 렌더링 되면 하위 컴포넌트도 다시 렌더링 된다.

### 2-1. componentDidUpdate\(\)

update가 이루어지고 render가 완료된 후, 실행되는 method

componentDidUpdate\(\)를 사용할 때, setState\(\)를 주의해야 한다. 그렇지 않으면 무한루프에 빠질수 있다.

```javascript
componentDidUpdate(prevProps, prevState, snapshot)
```

📄 **prevProps**

업데이트 되기 전, prop를 인자로 받을 수 있다. 이전 prop와 변경 여부를 비교하여 확인 후, 추가적인 액션을 설정하는게 유용하다.

📄 **prevState**

업데이트 되기 전, state 정보를 받을 수 있다. 이전 state와 비교하여 실행여부를 결정할 때 주로 사용한다.

📄 **snapshot**

`getSnapshotBeforeUpdate()` 구현시, 세번째 인자로 받을 수 있다

### 3. Umount 정의

해당 되는 Compoent DOM 상에서 제거될 때 실행되는 method

### 3-1. componentWillUnmount\(\)

최종적으로 제거될 때, 실행된다

component 내에서 이루어지는 네트워크 요청, 타이머 이벤트 등 지속적으로 이루어지는 이벤트를 해제하는데 유용하다.

### 4. Error 정의

render\(\) 함수에서 오류가 났을 때 실행할 수 있다.

### 4-1. componentDidCatch\(\)

오류가 발생하면 componentDidCatch\(\) 실행되게 하고, state.error를 true로 설정하게 한다.

render\(\) 에서 state.error의 따라서 오류를 띄어주면 된다.

component는 자신의 함수 안에서 오류가 발생하면 잡을 수 없지만, 그 대신에 자식 컴포넌트 내부에서 발생하는 오류들을 잡을 수 있다.
