# 📄 React - Context

## 1. Context  정의

일반적인 React 애플리케이션에서 데이터는 위에서 아래로 즉, 부모로 부터 자식에게 `props`를 통해 전달 되지만, 애플리케이션 안의 여러 컴포넌트를 전해줘야 하는 `props`의 경우 이 과정이 번거로울 수 있다. 그러므로 **context**를 이용하면 트리 단계 마다 명시적으로 `props`를 넘겨주지 않아도 많은 컴포넌트가 이러한 값을 공유하도록 할 수 있다.

### \(1\). Context를 사용한 데이터 공유

**context**는 React 컴포넌트 트리 안에서 **전역적 \(global\)**하게 공유할 수 있도록 고안된 방법이다.

**context**를 사용하여 컴포넌트 트리에 데이터를 **공급 \(provider\)** 하거나, **수요 \(consumer\)** 할 수 있도록 설정하여 데이터 관리를 보다 수월하게 할 수 있다. 

🤚 **context**의 주된 용도는 많은 컴포넌트에게 데이터를 전달하는 것이다. **context** 사용하면 컴포넌트를 재사용하기가 어려워지므로 꼭 필요할때만 써야 한다.

## 2. Conext API

### \(1\). React.createContext

context 객체를 만든다. context는 구독하고 있는 컴포넌트를 렌더링 할 때 React 트리 상위에서 가장 가까이 있는 공급자 \(provider\)로 부터 현재값을 읽는다.

```jsx
const myContext = React.createContext(defaultValue);
```

📝 **defaultValue**

`defaultValue`는 트리 안에서 적절한 provider 를 찾지 못했을때만 쓰이는 값이다. 만약에 provider를 통해

`undefined` 값을 보낸다고해도 `defaultValue`를 읽지 않는다.

### \(2\).Context.Provider

**context 객체에 포함된 React 컴포넌트인 provider는 context를 구독하는 컴포넌트들에게 context 변화를 알려준다.** 

provider는 value `prop`를 받아서 하위에 있는 컴포넌트에게 전달한다. provider 하위에서 context를 구독하고 있는 모든 컴포넌트는 provider의 value `prop`가 바뀔 때마다 다시 리렌더링 된다.

```jsx
<mythContext.Provider value={/* ... */}>
```

### \(3\). Class.contextType

`React.createContext()`로 생성한 context 객체 원하는 클래스의  `contextType` 프로퍼로 지정할 수 있다.

`this.context`를 통해서 context 객에 접근해 값을 읽고 사용할 수 있다.이 값은 render를 포함한 모든 컴포넌트 생명주기에서 사용할 수 있다.

🤚 functional component  에서 `useContext()` **Hook**를 사용한다.

### \(4\). Context.Consumer

context 변화를 구독하는 React 컴포넌트 이다. 함수 컴포넌트 안에서 context를 읽이 위해서 쓸 수 있다.

```jsx
<MyContext.Consumer>
  {value => /* context 값을 이용한 렌더링 */}
</MyContext.Consumer>
```

## 3. Result 

{% code title=" Exmple : Context application" %}
```jsx
// Create context with credential value and set initial value
const AuthContext = React.createContext(false);

// AuthContext.Provider set credentials to value using element
class App extends React.Component {
  state = {
    authentification: true
  };
  render() {
    return (
      <AuthContext.Provider value={this.state.authentification}>
        <MenuBar />
      </AuthContext.Provider>
    )
  }
}

// A(MenuBar)does not require a delivery process
const MenuBar = () => (
  <SignIn />
)

// Render using values received through AuthContext.Consumer
const SignIn = () => (
  <AuthContext.Consumer>
    {
      (context) => context ? 
        <div className="signed">Logged in</div> : 
        <div className="un-signed">Login Required</div>
    }
  </AuthContext.Consumer>
)
```
{% endcode %}

{% code title=" Exmple : Context separation and application of individual components" %}
```jsx
// Create as an "AuthContext" individual file with credentials and change methods
export const authContext = {
  isAuth: false
  signIn = () => { ... }
}

export default React.createContext(authContext);
```
{% endcode %}

```jsx
import AuthContext from "./context/AuthContext";

class App extends React.Component {
  state = {
    authentification: true,
  }
  logIn = () => {
    // Login... 
  }
  render() {
    return (
      <AuthContext.Provider 
        value={{ isAuth: this.state.authentification, signIn: this.logIn }}
      >
        <MenuBar />
      </AuthContext.Provider>
    )
  }
}
```

{% code title=" Exmple : To receive the data supplied from the parent component, the \"AuthContext\" file is called up, and the data is received and processed by the Consumer." %}
```jsx
import AuthContext from "../context/AuthContext";

const SignIn = () => (
  <AuthContext.Consumer>
    {
      ({isAuth, signIn}) => isAuth ? 
        <div className="signed">Logged in</div> : 
        <button type="button" onClick={() => signIn}>Login</button>
    }
  </AuthContext.Consumer>
);
```
{% endcode %}

\*\*\*\*

{% code title="Exmple : ContextType  application" %}
```jsx
import AuthContext from "../context/AuthContext";

class SignIn extends Component {
  static contextType = AuthContext;
  render() {
    const { isAuth, signIn } = this.context;
    return (
      {
        isAuth ? 
          <div className="signed">Logged in</div> : 
          <button type="button" onClick={() => signIn}>Login</button>
      }
    );
  }
}
```
{% endcode %}







