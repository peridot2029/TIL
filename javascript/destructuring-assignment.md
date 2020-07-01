# 📄 Destructuring assignment

### 1. Destructuring assignment 정의

비구조화 할당 구문은 **배열** 또는 **객체 속성**을 **별개 변수**로 추출할 수 있게 하는 JavaScript **식\(expression\)** 이다

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

