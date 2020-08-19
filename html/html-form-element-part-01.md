# 📄 HTML Form Element part 01

## 1. `<form>` Element

`<form>` 요소는 정보를 제출하기 위한 대화형 컨트롤을 포함하는 문구 구획을 나타낸다.

### \(1\). `<form>`  Element Attributes 

#### **action**

양식 데이터를 처리할 프로그램의 URL

#### **method**

* `post` : 양식 데이터를 요청 본문으로 전송 
* `get`  : `action` URL과 ? 구문자 뒤에 이어 붙여서 전송

## 2. `<input>` Element

웹 기반 양식에서 사용자의 데이터를 받을 수 있는 대화형 컨트롤 생성한다.

### \(1\). `<input>` Types\(유형\)

| 유형 | 설명 |
| :--- | :--- |
| `button` | 기본 행동을 가지지 않음, **value를 label로 사용**하는 push button |
| `checkbox` | 단일 값을 선택하거나, 선택 해제할 수 있는 체크박스 |
| `date` | 날짜\(연,월,일\)지정할 수 있는 컨트롤 |
| `radio` | 단일 값을 동일한 이름 값 으로 **여러 선택 항목 중**에서 선택할 수있는 라디오 버튼 |
| `search` | 검색 문자열 입력하기 위한 텍스트 필드 |
| `submit` | 양식을 제출하는 버 |

### \(2\). `<input>`  Element Attributes

| 유형 | 유형 또는 유형 | 설명 |
| :--- | :--- | :--- |
| `checked` | radio, checkbox | 명령 또는 제어 확인 여부 |
| `disabled` | all | 양식 컨트롤 비활성화 여부 |
| `form` | all | 컨트롤을 폼요소와 연결 |
| `formaction` | image, submit | 양식 제출에 사용할 URL |
| `formenctype` | image, sumbit | 양식 제출에 사용할 양식 데이터 세트 인코딩 유형 |
| `formmethod` | image, submit | 양식 제출에 사용할 HTTP 메서드 |
| `formnovalidate` | image, submit | 양식 제출을 위한 양식 컨트롤 유효성 검사 |
| `formtarget` | image, submit | 양식 제출을 위한 찾아보기 컨텍스트 |
| `max` | numeric types | 최대값 |
| `maxlength` | password, search, tel, text, url | 최대 길이\(문자 수\)value |
| `min` | numeric types | 최소값 |
| `minlength` | password, search, tel, text, url | 최소 길이\(문자 수\) value |
| `multiple` | email, file | Boolean, 여러 값 허용 여부 |
| `placeholder` | password,search,tel,text,url | 값이 설정이 되지 않는 경우 양식 컨트롤에 표시되는 텍스트 |
| `readonly` | almost all | Boolean, 값은 편집할 수 없다 |
| `required` | almost all | Boolean, 값이 필요하거나 제출 가능하도록 양식을 확인 |
| `size` | email, password, tel, text | 컨트롤의 크기 |
| `type` | all | 양식의 제어 유형 |
| `value` | all | 양식 컨트롤의 현재 ,  name/value 쌍의 일부로 양식과 함께 제출 |
| `name` | all | 양식 컨트롤의 이름,  name/value로 양식과 함께 제출 |

### 3. `<label>` Element

사용자 인터페이스 항목의 설명을 나타낸다.

### \(1\). `<label>` → `<input>` Element 연결

label 텍스트는 입력과 시각적으로 관련이 있을뿐만 아니라, 프로그래밍적 으로도 관련이 있다.

회면 리더기\(screenreader\)는 폼 입력\(form input\)에서 label를 읽어서 보조기술\(assistive technology\) 사용자가 입력해야 하는 텍스트가 무엇인지 더 쉽게 이해할 수 있게 한다.

관련 label를 클릭해서 input 자체에 초점을 맞추거나 활성화 시킬 수 있다.

`<label>`를 `<input>` 요소와 연결 시키려면, `<input>`에 id 속성을 넣어야 한다. 그런 다음에 `<label>` 에 **id**와 같은 값의 **for** 속성을 넣어야 한다.

✍ **Exmple - 암시적 연결**

```markup
<!-- label 안에 input 중첩 시킬 경우, for 및 id 속성은 필요 없다. -->
<label>Do you like peas?
  <input type="checkbox" name="peas">
</label>
```

### Other usage notes

label이 붙여진 양식 컨트롤\(form control\)은 **labeled control** 라고 불린다.

연관된 양식\(form control\)이 있는 `<label>`이 클릭 또는 터치 되면, 이벤트 연관된 control를 동작 시킨다.

### \(2\). `<label>` CSS Styling

`<label>`요소는 특별한 고려사항은 없다. 구조적으로 단순한 인라인 요소 이므로 `<span>` 또는 `<a>` 요소와 같은 방식으로 스타일링 할 수 있다.

### \(3\). `<label>` 접근성 고려사항

#### **Interactive content** 

`<label/>` 안에 `<a>` 또는 `<button>`와 같은 인터랙티브 요소를 배치하면, label과 관련된 양식을 입력하기 어렵다.

✍ **Exmple** 

{% tabs %}
{% tab title=" Bad " %}
```markup
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions">
  I agree to the <a href="terms-and-conditions.html">Terms and Conditions</a>
</label>
```
{% endtab %}

{% tab title=" Good " %}
```markup
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions">
  I agree to the Terms and Conditions
</label>
<p>
  <a href="terms-and-conditions.html">Read our Terms and Conditions</a>
</p>
```
{% endtab %}
{% endtabs %}



#### **title \(제목\)**

제목은 일반적으로 탐색 목적의 보조 도구로 사용되므로 `<label>` 내에 제목 요소를 배치하면 많은 종류의 보조 기술을 방핸한다.

label의 텍스트를 시각적으로 조정해야하는 경우,  `<label>` 요소에 적용된 CSS 클래스를 사용하는게 옳다.

{% tabs %}
{% tab title="Bad " %}
```markup
<label for="your-name">
  <h3>Your name</h3>
  <input id="your-name" name="your-name" type="text">
</label>
```
{% endtab %}

{% tab title="Good" %}
```markup
<label class="large-label" for="your-name">
  Your name
  <input id="your-name" name="your-name" type="text">
</label>
```
{% endtab %}
{% endtabs %}

### Reference  <a id="reference"></a>

form - 폼 요소 [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/form)

input - 인풋 요소 [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/input)

label - 레이블 요소 [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/label)

Forms [→HTML5.2 표준 기술 사양](https://html.spec.whatwg.org/multipage/forms.html#sec-forms)

Formspress - 폼 전송 test [→\(SITE\)](https://formspree.io/)

