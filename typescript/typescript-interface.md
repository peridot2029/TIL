# 📄 TypeScript Interface

## 1. Interface

### \(1\). Interface의 소

🤚 [`interface`](https://ko.wikipedia.org/wiki/%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4_%28%EC%BB%B4%ED%93%A8%ED%8C%85%29)는 간단하게 어떠한 시스템 두 개의 시스템 사이에 상호작용 할 수 있게 해주는 조건, 규약 

인터페이스는 일반적으로 타입 체크를 위해 사용되며 variable, function,class 등에 사용할 수 있다. 인터페이스는 여러 가지 타입을 갖는 프로퍼티로 이루어진 새로운 타입을 정의하는 것과 유사하다.

인터페이스는 프로퍼티와 메서를 가질 수 있다는 점에서 class와 유사하나, 직접 인스턴스를 생성할 수 없고, 모든 메서드 추상 메서드 이다.



✍ **Exmple**

```typescript
interface Todo {
  id: number;
  content: string;
  completed: boolean;
}

let todos: Todo[] = [];

function addTodo(todo: Todo) {
  todos = [...todos, todo];
}

const newTodo: Todo = { id: 1, content: 'typescript', completed: false };
addTodo(newTodo);

console.log(todos)
```





