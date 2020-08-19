# 📄 React List and Key

## 1. List and Key 

{% hint style="info" %}
Key는 React가 어떤 항목을 변경, 추가 또는 삭제할지 식별하는 것을 돕는다.
{% endhint %}

**key element**에 안정적인 고유성 부여하기 위해 배열 내부의 **element**에 지정해야 한다.

key를 다른 항목들 사이에서 해당 항목을 **고유하게 식별하기 할 수 있는 문자열**을 사용하는게 좋다

대부분의 경우에는 **id**를 **key**로 사용한다.

렌더링 한 항목에 대한 안정적인 **id**가 없다면 [최후의 수단](https://medium.com/@robinpokorny/index-as-a-key-is-an-anti-pattern-e0349aece318)으로 항목의 인덱스를 **key**로 사용.

## 2. List and Key 만들기

**list Item component**를 추출한 경우 **List Item** 안에 있는 `<li>` **element**가 아니라 배열의 `<ListItem/>` **element**가 **key**를 가져와야 한다.

* `map()` 함수 내부에 있는 **element**에 **key**를 넣어주는게 좋다.
* `map()` 함수가 너무 중첩된다면 **compontent**로 추출하는게 좋다.

✍ **Example - Not List and Key**

```jsx
function ListItem(props) {
  const value = props.value;
	// Not key - There is no need to specify a key here.
  return <li key={value.toString()}>{value}</li>;
}

function NumberList(props) {
  const numbers = props.numbers;
	// Assign a key here - The key must be specified here.
  const listItems = numbers.map((number) => <ListItem value={number} />);
  return <ul>{listItems}</ul>;
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render( <NumberList numbers={numbers} />, document.getElementById("root"));
```

✍ **Example - Goog List and Key**

```jsx
function ListItem(props) {
  return <li>{props.value}</li>;
}

function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) => (
    <ListItem key={number.toString()} value={number} />
  ));
  return <ul>{listItems}</ul>;
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render( <NumberList numbers={numbers} />, document.getElementById("root"));
```

