# 📄 React Router

## 1. React Router  정의

특정 URL로 사용자가 접근 했을 때, URL를 해석하여 요청한 URL에 알맞는 component를 렌더링 해서 보여주는 역할

즉, 여러 페이지들이 존재하는 서비스를 만들 때 필요하며, URL 또는 상태에 따라서 view를 나누기 위해서 서 사용한다.

Facebook 공식 라이브러리는 아니지만 React Router 라이브러리 중에서 가장 많은 사용자 보유

react router는 v3과는 다르다고 봐야한다.

## 2.  React Project - Router 설치 및 적용

yarn를 이용해서 **react-rouer-dom** 설치



✍ **setting** 

```bash
$ yarn add react-router-dom
```

### \(1\) **Router Component**

브라우저에서 히스토리를 이용해서 구현할 라우터, 하나의 자식을 가질 수 있다.

다른 `<Link>, <Route>`컴포넌트를 사용하기 위해서 DOM tree 상에서는 항상 `<Router>`를 공통 상위 컴포넌트로 가져야한다. 

`<Router>`에는 여러 종류가 있는데, 일반적인 라우팅을 위해 사용되는 `<BrowserRouter>`를 사용한다.

✍ **Syntax**

```jsx
import { BrowserRouter as Router, Route, Link} from 'react-router-dom'
```

### \(2\) Link Component

HTML `<a/>`tag 와 유사하다. 실제로 동작은 페이지 전체를 리로드 하지 않고 필요한 부분만을 리로드 하게 된다.

✍ **Syntax**

```jsx
<Link to="/abuout">About</Link>
```

### \(3\) Route Componet

현재 주소창의 경로와 매치될 경우 보여줄 컴포넌트를 지정하는데 사용한다.

`path`prop를 통해서 매치시킬 경로를 지정하고, `component`prop를 통해서 매치되었을 때 보여줄 컴포넌트를 할당한다.

✍ **Syntax**

```jsx
<Route path="/about" component={About} />
```

### \(4\) React Router 적용

React Router는 path prop 경로와 현재 브라우저의 주소창 URL 경로\(location.pathname\)와 비교를 한다.

현재 URL 경로 값이`<Route>`의 `path` prop 값과 전체가 아닌 앞부분만 일치해도 매치되는 것으로 간주한다.

`exact`prop이 없으면, 의도치 않게 prop Home 컴포넌트 URL 경로와 상관없이 항상 보여지게 된다.

`exact`prop를 사용하면,  붙여주면 URL 경로 값이 `<Route>`의 path 값과 완벽히 전체가 일치해야 매치되는 것을 처리한다.



✍ **Example** 

```jsx
import React from "react"
import { Link, Route, BrowserRouter as Router } from "react-router-dom"
import Home from "./Home"
import About from "./About"
import NotFound from "./NotFound"

function App() {
  return (
    <Router>
      <header>
        <Link to="/">
          <button>Home</button>
        </Link>
        <Link to="/about">
          <button>About</button>
        </Link>
        <Link to="/users">
          <button>Users</button>
        </Link>
      </header>
      <hr />
      <main>
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
        <Route path="/users" component={NotFound} />
      </main>
    </Router>
  )
}
```



### Reference <a id="reference"></a>

 React Router 라우팅 하기 [→\(SITE\)﻿](https://www.daleseo.com/react-router-basic/)

