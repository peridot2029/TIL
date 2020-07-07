# 📄 JavaScript for~of, forEach

### 1. for~in 정의

**객체 모든 열거 가능한 속성\(property\)에 대한 반복,** 즉 모든 객체에 사용 가능하다.

단, **key** 값에 접근할 수 있지만, **value** 값에 **접근할 수 있는 방법은 제공하지 않는다.**

✍ **Exmple - for ~ in**

```javascript
const cafeMenu = {
    name: "Green_Grape_Slush",
    kcal: 224.51,
    text: "트로피칼 레볼루션 청포도 슬러쉬",
  };

  let { name, kcal, text } = cafeMenu;

  console.log(name); // Green_Grape_Slush
  console.log(kcal); // 224.51
  console.log(text); // 트로피칼 레볼루션 청포도 슬러쉬
```

### 2. for~of

Symbol.iterator 속성을 가지는 컬렉션 전용

### 3. forEach

오직 Array 객체에서만 사용 가능한 method

배열의 요소들을 반복항여 작업을 수행할 수 있다.

