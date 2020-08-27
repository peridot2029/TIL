# 📄 TypeScript - Generics

## 1.Generics

### \(1\). Generics 정의

제네릭은 TypeScript의 `function`, `class`, `interface`, `type` 을 사용하게 될 때 여러 종류의 타입에 대하여 호환을 맞춰야 하는 상황에서 사용하는 문법이다.

### \(2\). 함수에서 Generics

아래의 코드를 보면 `merge` 안에서 `a`, `b`는 어떤 타입을 올지 모르기 때문에 `any`타입을 사용한다. 결과가 `any` 라면 즉, 타입이 추론이 깨짐을 의미한다. 그 이유는 `merged` 안에 무엇이 있는지 알 수 있기 때문이다.

✍ **Exmple**

```typescript
function merge(a: any, b: any): any {
  return {
    ...a,
    ...b,
  };
}
```

제네릭을 사용할 때에는 &lt;T&gt; 처럼 꺽쇠 안에 타입의 이름을 넣어서 사용한다. 이렇게 설정하면 제네릭은 해당 하는 타입이 뭐든지 들어올 수 있게 되면서, 사용할 때 타입이 깨지지 않는다.

✍ **Exmple**

```typescript
function wrap<T>(param: T) {
  return {
    param,
  };
}
const wrapped = wrap(10);
```

### \(2\). Interface에서 Generics

✍ **Exmple**

```typescript
interface Items<T> {
  list: T[];
}

const items: Items<string> = {
  list: ['a', 'b', 'c'],
};

```

### \(3\). Type align 에 Generics

✍ **Exmple**

```typescript
type ItemOne<T> = {
  list: T[];
};

const itemOne: ItemOne<string> = {
  list: ['a', 'b', 'c'],
};
```



