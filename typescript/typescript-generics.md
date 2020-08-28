# 📄 TypeScript - Generics

## 1.Generics

### \(1\). Generics 정의

**제네릭 \(Generics\)**은 클래스 또는 함수에서 사용할 타입 \(Type\)을, 그 클래스나 함수를 사용할 때 결정하는 프로그래밍 기법이다.  JavaScript와 같은 동적 타입 언어만 다루던 개발자에게는 생소한 개념이다. 하지만 **TypeScript는 정적 타입 언어라서 제네릭을 원한다.**

아래의 코드를 보면 `merge` 안에서 `a`, `b`는 어떤 타입을 올지 모르기 때문에 `any`타입을 사용한다. 결과가 `any` 라면 즉, 타입이 추론이 깨짐을 의미한다. 그 이유는 `merged` 안에 무엇이 있는지 알 수 있기 때문이다.

아래의 코드를 보면 `merge`안에서 `a`, `b`는 어떤 타입을 올지 모르기 때문에 `any`타입을 사용한다. 결과가 `any` 라면 즉, 타입이 추론이 깨짐을 의미한다. 그 이유는 `merged` 안에 무엇이 있는지 알 수 있기 때문이다.

제네릭이 필요한 이유는 TypeScript로 구현한 Model  클래스는 일반적으로 데이터 타입을 규정하지 않고, 어떤 타입이든 아이템으로 추가 하거나, 추출 할 수 있다. 

✍ **Exmple**

```typescript
// class Model
class Model {
  
  private _data: any[] = [];
  
  constructor(data:any[]) {
    this._data = data;
  }
  
  get data():any { 
    return this._data; 
  }
  
  add(item:any):void { 
    this._data.push(item); 
  }
  
  remove(index:number):void { 
    this._data.splice(index, 1); 
  }
  
  item(index:number):any { 
    return this._data[index]; 
  }
  
  clear():void { 
    this._data = []; 
  }
}

// clas Model extends ObjectModel
class ObjectModel extends Model {
​
  constructor(data:object[]=[]) { 
    super(data); 
  }
  
  add(item:object):void { 
    super.add(item); 
  }
​
}
```

위의 코드 처럼 클래스를 상속하면 별도의 자료 타입을 받고자 하는 클래스를 추가해야 되고,  중복되는 코드를 양산하기 때문에 불편하다. 이런 경우 유용하게 사용할 수 있는게 **제네릭** 이다.

✍ **Exmple**

```typescript
class Model<T> {
  
  private _data:T[] = [];
  
  constructor(data:T[]=[]) {
    this._data = data;
  }
  
  get data():T[] { 
    return this._data; 
  }
  
  add(item:T):void { 
    this._data.push(item); 
  }
  
  remove(index:number):void { 
    this._data.splice(index, 1); 
  }
  
  item(index:number):T { 
    return this._data[index]; 
  }
  
  clear():void { 
    this._data = []; 
  }
  
}
```

TypeScript 프로그래밍 과정에서 부득이하게 정해진 타입이 아닌 경우를 사용해야 경우가 종종 발생한다.이런 경우 타입이 **어설션 문법**을 사용해 컴파일 과정의 타입 검사를 우회할 수 도 있다. 꼭 필요한 경우에만 사용하는 것이 좋다.

✍ **Exmple**

```typescript
const stringModel = new Model<string>();
​
stringModel.add('흔들의자');
// stringModel.add(2018);

// as 문
stringModel.add(2018 as any);
stringModel.add(<any>2018);
```



### \(2\). 함수에서 Generics

제네릭을 사용할 때에는 &lt;T&gt; 처럼 꺽쇠 안에 타입의 이름을 넣어서 사용한다. 이렇게 설정하면 제네릭은 해당 하는 타입이 뭐든지 들어올 수 있게 되면서, 사용할 때 타입이 깨지지 않는다.

✍ **Exmple**

{% tabs %}
{% tab title="JavaScript" %}
```typescript
function getItemArray(arr, index) {
  return arr[index];
}

function pushItemArray(arr, item) {
  arr.push(item)
}
```
{% endtab %}

{% tab title="TypeScript" %}
```typescript
function getItemArray(arr:any[], index:number):any {
  return arr[index];
}

function pushItemArray(arr:any[], item:any):void {
  arr.push(item);
}
```
{% endtab %}

{% tab title="Generics" %}
```typescript
function getItemArray<T>(arr:T[], index:number):T {
  return arr[index];
}

function pushItemArray<T>(arr:T[], item:T):void {
  arr.push(item);
}


const potatoChip_materials = ['어니언'];

getItemArray(potatoChip_materials, 0);
pushItemArray<string>(potatoChip_materials, '사워크림');


```
{% endtab %}
{% endtabs %}



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



