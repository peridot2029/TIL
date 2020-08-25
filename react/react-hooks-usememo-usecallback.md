# 📄 React Hooks - useMemo, useCallback

## 1. React.useMemo\(\)

> \*\*\*\*[**메모이제션 \(Memoization\)**](https://en.wikipedia.org/wiki/Memoization)\*\*\*\*
>
> 메모제이션은 기존에 연산의 결과 값을 어딘가에 저장해두고, 동일한 입력이 들어오면 재활용 하는 프로그램 기법을 의미한다. ****

**메모이제이션된 값을 반환한다**. 하위 컴포넌트는 상위 컴포넌트로 부터 `A` 와 `B` 라는 두 개의 `props`를 전달 받는다. 

하위 컴포넌트는 `props`로 전달 받은 `A` 와 `B` 중에서 하나라도 변경될 때 마다 리렌더링 된다. 만약에 전달 받은 `A`의 값만 변경되고 `B`의 경우는 이전값과 동일한 경우, 다시 함수를 호출하는 대신 기존에 메모제이션 기법을 사용해서 로직을 구현할 수 있다.  즉, **특정 결과 값을 재사용하고 싶을 때 `useMemo()`를 사용한다.**

✍ **Syntax**

```jsx
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

## 2. React.useCallback\(\)

**메모이제이션된 콜백을 반환한다.** React에서는 컴포넌트가 다시 리렌더링 될 때, 컴포넌트 안에 선언된 함수들도 새로 생성한다. 즉,`useCallback()` 은 특정 함수를 새로 만들지 않고 재사용 하고 싶을 때 사용한다.

✋ `useCallback(fn, deps)`은`useMemo(() =>fn, deps)`와 같다.













### Reference <a id="reference"></a>

 React.memo\(\) 현명하게 사용하기 [→\(SITE\)](https://ui.toast.com/weekly-pick/ko_20190731/)

