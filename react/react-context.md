# 📄 React Context

### 1. Props 전달의 문제점

 React App의 일반적인 데이터 송/수신 구조는 '**위에서 아래로 prop를 전달**'하도록 구성되어 있다. 문제는 ㅊComponet 중첩 단계가 복잡해지면 **props ⇌ callback 문제**가 발생하므로 React app 관리가 매우 어려워진다.

### 2.  [Context](https://ko.reactjs.org/docs/context.html)를 사용한 데이터 공유

  Context는 React Components Tree 안에서 데이터를 **글로벌\(Global\)**하게 공유할 수 있도록 고안된 방법.

Context를 사용하여 Components Tree에 데이터를 **공급 \(Provider\)** 하거나, **수요\(Consumer\)** 할 수 있도록 설정하여 데이터 관리를 보다 수월하게 할 수 있다.

 **✍ Exmple - Context application**

```javascript
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

  
 **✍ Exmple - Context separation and application of individual components**

```javascript
// Create as an "AuthContext" individual file with credentials and change methods
export const authContext = {
  isAuth: false,
  signIn = () => { ... }
}

export default React.createContext(authContext);
```

 **✍ Exmple - Component tree start point Set provider in parent component and forward to value**

```javascript
import AuthContext from "./context/AuthContext";

class App extends React.Component {
  state = {
    authentification: true
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

**✍ Exmple - To receive the data supplied from the parent component, the "AuthContext" file is called up, and the data is received and processed by the Consumer.**

```javascript
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

### **3. Context Type 활용**

{% hint style="warning" %}
 컨텍스트 타입을 사용하면 단 하나의 컨텍스트 객체만 사용 가능하다. 

하나 이상의 context object 사용 하려면, 위에서 언급한 `context.sonsumer`를 중첩해 사용해야 한다.  

자세한 내용은 [여러 cotext 구독하기](https://ko.reactjs.org/docs/context.html#consuming-multiple-contexts) 참고하기를...
{% endhint %}

 ContextType은 Context Object를 클래스 컴포넌트의 **Context Type Static** 속성으로 지정해 활용하는 방법이다. 이 방법을 사용하면 `this.context`를 통해 Context object에 접근해 값을 읽고 사용할 수 있다.  


Functional componet에서는 `useContext()` **Hook**를 사용한다.

 **✍ Exmple - ContextType  application**

```javascript
import AuthContext from "../context/AuthContext";

class SignIn extends Component {
  static contextType = AuthContext
  render() {
    const { isAuth, signIn } = this.context
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









