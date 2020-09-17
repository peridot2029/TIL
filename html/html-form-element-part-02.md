# 📄 HTML - Form Element part 02

## 1. `<button>` Element

`<button>` 요소는 클릭한 버튼을 나태낸다.

### \(1\). `<button>` Element Attributes

#### 📝**autofocus**

페이지 로드 후, 버튼에 포커스가 위치해야 하는지 나타낸다.

문서 내에서 **하나의 요소만** `autofocus` 특성을 가질 수 있다.

#### 📝**disabled**

버튼과 사용자의 상호작용, 즉 누르거나 클릭하는 것을 막는다.

#### 📝**form**

버튼을 연결할 `<form>`요소, 같은 문서에 존재하는 `<form>` 요소의 `id` 특성 값을 사용해야 한다

`form` 특성을 정의하지 않았으나, 조상 중에 `<form>` 요소가 존재하면 해당 `<form>` 과 연결된다.

#### 📝**formaction**

`<button>`이 submit 인 경우, 제출할 정보를 URL

지정한 경우, 버튼의 양식 소유자가 가진 `action` 특성 보다 우선 시 한다.

#### 📝**formmethod**

`<button>`이 submit 인 경우, `formmethod` 특성은 양식을 서버로 제출할 때 사용할 HTTP 메서드를 지정한다.

#### 📝**formnovalidate**

`<form>`이 submit 인 경우, `formnovalidate` 특성은 양식을 제출할 때 유효성 검사를 하지 않겠다는 것을 지정한다.

지정한 경우, 버튼의 양식 소유자 가진 `novalidate` 특성 보다 우선시 한다.

#### 📝**name**

버튼의 이름, 제출할때 버튼 value 특성과 함께 양식 데이터의 일부를 구성한다.

#### 📝**type**

* submit : 버튼이 서버로 양식 데이터를 제출한다. 지정하지 않은 경우, 기본 값이며, 유효 하지 않은 값일 때도 사용한다.
* reset : `<input type="reset">` 처럼, 모든 컨트롤 값을 초기값으로 되돌린다.
* button : 기본 행동이 없으며, 클릭 했을 때 아무것도 하지 않는다. 클라이언트 측 스크립트와 연결할 수 있다.

#### 📝**value**

버튼의 초기값, 제출 할 때, `value` 특성과 함께 양식 데이터의 일부를 구성한다.

#### 📝o**ther usage notes**

`<button>` 요소는 `<input>` 보다 스타일을 적용하기 훨씬 수월하다.

`<input>`은 `value` 특성에 text value 밖에 지정할 수 없다.

`<button>`은 내부 HTML 콘텐츠에 \(`<em>,<strong>,<img>`도\) 더 해 `::after`와 `::before` 가상 요소를 사용하는 복잡한 렌더링도 가능하다.

서버에 제출할 버튼이 아니라면, `type` 특성을 `button`으로 반드시 지정해야 한다.

### \(1\). `<button>` 접근성 고려사항

#### 📝**icon button**

아이콘만 사용해 기능을 표현하는 버튼은 접근 가능한 이름을 갖지 않는다.

아이콘 버튼에 접근 가능한 이름을 부여하려면 `<button>` 요소의 **기능을 간략히 묘사하는 텍스트**를 안에 포함 시켜야 한다.

{% code title="Exmple : icon button" %}
```markup
<button name="favorite" type="button">
  <svg aria-hidden="true" viewBox="0 0 10 10">
  <path d="M7 9L5 8 3 9V6L1 4h3l1-3 1 3h3L7 6z"/></svg>
  Add to favorites
</button>
```
{% endcode %}

#### 📝**크기**

버튼과 같은 대화형 요소는 상호작용하기 충분한 크기의 활성화 영역을 가져야 한다.

충분한 크기는 운동 조절 장애를 가진 사용자와, 터치 스크린 처럼 정확하지 입력 도구 사용자 처럼 다양한 사람을 돕는다. **최소 44 x 44** CSS px\(픽셀\) 크기를 권고 한다.

#### 📝**간격**

버튼과 같은 대화형 요소 다수를 시각적으로 가까이 배치할 땐 서로를 분리하는 공간을 둬야 한다.

간격은 운동 조절 장애를 가진 사용자와 우너하지 않는 상호작용을 하는 걸 방지할 수 있다.

간격은 `margin`과 같은 CSS 속성으로 설정할 수 있다.

## 2. `<select>` Element

`<select>` element는 옵션 메뉴를 제공하는 컨트롤을 나타낸다.

`<select>` 는 `<label>`과 연결해 접근성을 향상 시킬 수 있다.

`<option>` 은 자신이 선택 됐을 때 사용할 `value` 특성이 필요하다.

그러나 `value` 특성을 지정하지 않은 경우, 대신 자기 안에 텍스트를 값으로 사용한다.

`<selected>` 특성을 지정하면 해당 옵션을 선택한 상태로 페이지를 불러온다.

`<option>` 요소를 `<optiongroup>` 요소 안에 배치하면 드롭 다운 내에서 옵션 그룹으로 나눌 수 있다.



```markup
<label for="coffe-select">Click Coffee Menu :</label>
<select name="coffes" id="coffe-select">
  <option value="">--Please choose an option--</option>
  <option value="caffe-americano">Caffe Americano</option>
  <option value="caffe-latte">Caffe Latte</option>
  <option value="caramel-macchiato">Caramel Macchiato</option>
  <option value="strawberry-yogurt">Strawberry Yogurt</option>
</select>
```

### Reference  <a id="reference"></a>

button element [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/button)

select  element [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/select)

option  element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/option)

optgroup  element[ →\(MDN\)﻿](https://developer.mozilla.org/ko/docs/Web/HTML/Element/optgroup)

####  <a id="reference"></a>

### 

