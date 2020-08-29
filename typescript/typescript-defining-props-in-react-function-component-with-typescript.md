---
description: React  - Function Component TypeScript로 작성
---

# 📄 TypeScript - Defining Props in React Function Component with Typescript

## 1. TypeScript → React Project 적용

### \(1\). Create React App→ TypeScript Install

`ts-react-tutorial`  React App 생성 후,  TypeScript 설치.

```bash
# create react project
$ create-react-app ts-react-tutorial

# typescript install
$ yarn add typescript --dev
```

### \(2\).  App.js → App.tsx 

 🤚 꼭 화살표 함수를 사용해서 컴포넌트를 만들 필요는 없다. 보통은 `function` 키워드를 사용하여 함수형 컴포넌트를 사용하는 것이다.  추세이다. 대표적인 예로[ 리액트 공식 메뉴얼](https://reactjs.org/docs/components-and-props.html)에서도 `function` 키워드를 사용하고 있다. 

src 디렉토리 안에  있는 App.js의 확장자를 `APP.tsx`로 변경 후, 화살표 함수로 사용해서 컴포넌트 선언.

{% code title="src/App.tsx" %}
```typescript
import React from 'react';
import logo from './logo.svg';
import './App.css';

const App: React.FC = () => {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.tsx</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```
{% endcode %}

### \(3\). 새로운 컴포넌트 생성

src 디렉토리에 components 폴더를 추가 후에 폴더 안에 `Greetings.tsx` 생성,  컴포넌트의 경우 

`props`에 대한 타입을 선언 할 때 `type`, `interface`를 어떤 것을 써도 상관 없다. 단 프로젝트의 일관성만 유지하면 된다.

{% code title="src/components/Greetings.tsx" %}
```typescript
import React from 'react';

type GreetingsProps = {
  name: string;
};

const Greetings: React.FC<GreetingsProps> = ({ name }) => (
  <div>Hello, {name}</div>
);

export default Greetings;
```
{% endcode %}

### \(4\). React Functional Compoent의 약어 → `React.FC`의 장단점 

1. `props`에 기본적으로 `children`이 들어가 있다. \(장점\)
2. `defaultProps`, `propTypes`, `contextTypes` 를 설정할때 자동완성이 될 수 있다. \(장점\)
3. `children`이 옵션 형태로 있어서,`componet props`에 명백하지 않다. \(단점\)
4. 그러므로 `children`를 사용하는 경우, 안하는 경우 처리를 해야한다. \(단점\)
5. `React.FC`를 사용하면 `defaultProps`가 제대로 작동하지 않을 수 있다. \(단점\)

{% code title="src/componets/Greetings.tsx" %}
```typescript
import React from 'react';

type GreetingsProps = {
  name: string;
  mark: string;
};

const Greetings: React.FC<GreetingsProps> = ({ name, mark }) => (
  <div>
    Hello, {name} {mark}
  </div>
);

Greetings.defaultProps = {
  mark: '!'
};

export default Greetings;

```
{% endcode %}

{% code title="src/App.tsx" %}
```typescript
import React from 'react';
import Greetings from './compontents/Greetings';

const App: React.FC = () => {
  return <Greetings name="Hello" />;
};

export default App;
```
{% endcode %}

예제 코드를 보면 `Greetings.tsx` 에서 `mark`를 `defalutProps`로 넣었음에도 불구하고, `mark` 값은 제대로 작동하지 않는다.  이런 경우에 React.FC를 생략하면 오히려 아주 잘 작동한다. 이러한 이슈 때문에 [React.FC는 사용하지 말라는 글](https://medium.com/@martin_hotell/10-typescript-pro-tips-patterns-with-or-without-react-5799488d6680#78b9)도 존재한다. 그리고 **화살표 함수**를 **일반 함수형 컴포넌트로 변경**하겠다.

### \(5\). Greetings.tsx → Optional  Props,  Function Type Props

컴포넌트의 props 중의 **생략 가능한 props** 설정과 그리고 **특정 함수를 props**로 받아서 타입을 지정한다.

{% code title="src/componets/Greetings.tsx" %}
```typescript
mport React from 'react';

type GreetingsProps = {
  name: string;
  mark: string;
  optinoal?: string; // 생략 할 수 있는 props 설정
  onClick: (name: string) => void; 
};

function Greetings({ name, mark, optinoal, onClick }: GreetingsProps) {
  const hadleClick = () => onClick(name);
  return (
    <div>
      Hello,{name} {mark}
      {optinoal && <p>{optinoal}</p>}
      <div>
        <button type='button' onClick={hadleClick}>
          Click Me
        </button>
      </div>
    </div>
  );
}

Greetings.defaultProps = {
  mark: '!',
};

export default Greetings;
```
{% endcode %}

{% code title="src/App.tsx" %}
```typescript
import React from 'react';
import Greetings from './components/Greetings';

const App: React.FC = () => {
  const onClick = (name: string) => {
    console.log(`${name} says hello`);
  };
  return <Greetings name="Hello" onClick={onClick} />;
};

export default App;
```
{% endcode %}

