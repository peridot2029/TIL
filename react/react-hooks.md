# 📄 React Hooks

### 2. useEffect\(\) 정의

functional componet의 Lifecycle, class component의 Lifecycle 와 동일한 의미이다.

### 2-1. useEffect\(\) - Mount, Unmount 관리

\[deps\] 의존 값이 들어이는 배열을 넣는다.

두번 째 매개 변수로 \[\] 배열을 비우게 되면 component가 처음 나타날때만 useEffect\(\)에 등록한 function 를 호출한다.

useEffect\(\) 에서 이 함수를 cleanup function 이라고 부른다.

✍ **Example** 

```jsx
useEffect(() => {
    console.log("Appears on the component screen.");

    return () => {
      console.log("Exit the component screen");
    };
  }, []);
```

### 2-2. useEffect\(\) - \[deps\] 특정 값 삽입

deps에 특정 값을 넣게 된다면, component가 처음 mount 될 때 호출되고, 지정한 값이 바뀔 때도 호출된다.

deps 안에 특정 값이 있다면, unmount 시 호출 되고, 값이 바뀌기 직전에도 호출된다.

useEffect 안에서 사용하는 상태 또는 prop가 있다면, useEffect에 넣어주는게 규칙이다.

만약 useEffect 안에서 상태 또는 prop를 넣지 않게 된다면, useEffect에 등록한 함수가 실행될 때 최신 props/상태를 가르키지 않게 된다.

### 2-3. useEffect\(\) - 매개변수 생략

deps를 생략하면, component 리렌더링 될 때 마다 호출된다.

참고로 부모 컴포넌트가 리렌더링 되면 자식 컴포넌트 또한 리렌더링 된다.

### 2-4. useEffect 축약 정리

> 1. 화면이 처음 떴을 때 실행.
>    * deps\[\] 빈 배열을 넣을 때
>    * LifeCycle 중 componentDidmount 처럼 실행
> 2. 화면이 사라질 때 \(cleup function\)
>    * componentWillUnmount\(\) 처럼 실행
> 3. deps에 넣은 파라미터값이 업데이트 됬을때 실행
>    * componentDidUpdate 처럼 실행





\_\_



