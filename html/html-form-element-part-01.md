# 📄 HTML - Form Element part 01

## 1. `<form>` Element

웹 페이지의 컴포넌트를 말하며 사용자와 인터랙션을 수행한 결과를 서버로 보낼 수 있다.

즉, 사용자 정보를 서버로 제출하기 위한 **대화형 컨트롤**을 포함하는 문서 구획을 나타낸다.

### \(1\). `<form>`  Element Attributes 

| attribute | description |
| :--- | :--- |
|  `accept-charset` | 폼 데이터가 서버로 제출될때 사용되는 문자 인코딩 방식을 명시한다 |
| `action` | 폼 데이터가 서버로 제출될 때 해당 데이터가 도착할 URL을 명시한다. |
| `autocomplete` | `<form>` 요소의 자동 완성 기능을 사용하지 여부를 명시한다. |
| `enctype` | 폼 데이터가 서버로 제출될 때 해당 데이터가 인코딩 되는 방법을 명시한다. \(단, `<form>`요소의 method 속성값이 POST인 경우에만 사용할 수 있다.\) |
| `method` | 폼 데이터가 서버로 제출될 때 사용되는 HTTP method를 명시한다. |
| `novaildate` | 폼 데이터가 서버로 제출될 때 해당 데이터의 유효성을 검사하지 않음을 명시한다. |
| `target` | 폼 데이터를 서버로 제출한 후 받는 응답이 열릴 위치를 명시한다. |

## 2. `<input>` Element

`<input>` 요소는 사용자로 부터 입력을 받을 수 있는 입력 필력\(input fileld\)를 정의할 때 사용한다.

`<input>`요소는 사용자가 데이터를 입력할 수 있는 입력 필드를 선언하기 위해 &lt;form&gt; 요소 내부에서 사용된다.

### \(1\). `<input>` Type

 `<input>` 요소의 `type` 속성값을 달리함으로써 여러가지 모양으로 나타낼 수 있다.

| type | description |
| :--- | :--- |
| `button` | 기본 행동이 없으며, 클릭 했을 때 아무런 일도 발생하지 않는다. |
| `checkbox` | 체크박스는 사용자 여러 선택사항 중에서 하나 이상의 값을 선택할 수 있게 한다. |
| `color` | 색상을 선택할 수 있는 입력 필드를 정의한다. |
| `date` | 날짜를 선택할 수 있는 입력 필드를 정의한다. |
| `datetime-local` | 날짜와 시간을 선택할 수 있는 입력 필드를 정의한다. |
| `email` | 이메일 주소를 입력할 수 있는 입력 필드를 정의한다. |
| `file` | 업로드할 파일을 선택할 수 있는 입력 필드와 "파일선택" 버튼을 정의한다. |
| `hidden` | 사용자에게는 보이지 않는 숨겨진 입력 필드를 정의한다. |
| `image` | 제출 버튼으로 사용될 이미지를 정의한다.   이 속성값은 텍스트가 아닌 이미지 형태로 된 제출 버튼을 생성한다. |
| `month` | 날짜를 직접 입력하거나, 날짜를 선택할 수 있는 입력 필드를 정의한다.   입력 결과는 년도와 월을 나타내는 "YYYY-MM" 형식으로 문자열이 되며, 일과 시간은 포함하지 않는다. |
| `number` | 숫자를 입력할 수 있는 입력 필드를 정의한다. |
| `password` | 비밀번호를 입력할 수 있는 입력 필드를 정의한다. |
| `radio` | 라디오 버튼을 정의한다. |
| `range` | 슬라이드 바를 조정하여 범위 내의 숫자를 선택할 수 있는 입력 필드를 정의한다. |
| reset | 모든 폼 요소의 값을 초기값으로 되돌리는 리셋 버튼을 정의한다. |
| `search` | 검색어를 입력할 수 있는 텍스트 필드를 정의한다. |
| `submit` | 서버의 폼 핸들러로 폼 데이터를 전송하는 제출 버튼을 정의한다. |
| `tel` | 전화번호를 입력할 수 있는 입력 필드를 정의한다. |
| `text` | `type` 속성의 기본 값으로 한 줄로 된 텍스트 필드를 정의한다. |
| time | 시간을 선택할 수 있는 입력 필드를 정의한다. |
| `url` | URL 주소를 입력할 수 있는 입력 필드를 정의한다. |
| `week` | 날짜를 직접 입력하거나, 날짜를 선택할 수 있는 입력 필드를 정의한다.   입력 결과는 년도와 주가 포홤되며 이때 주 앞에는 "W" 문자가 추가되어 제출된다. |

### \(2\). `<input>`  Element Attributes

`<input>` 요소의 다양한 속성은 다음과 같다.

| attribute | type or types | description |
| :--- | :--- | :--- |
| `accept` | file | 서버의 업로드할 수 있는 파일의 타입을 명시한다. |
| `alt` | image | 이미지를 위한 대체 텍스트를 명시한다. |
| `autocomplete` | all | `<input>` 요소에 입력된 정보를 저장할지 안 할지를 명시한다. |
| `autofocus` | all | 웹 페이지가 로드 될 때, 속성이 적용된 `<inpnt>` 요소에 자동으로 포커스가 가도록 해준다. |
| `capture` | image | 모바일 디바이스에 적용되는 속성으로 어떤 카메라를 이용할지 지정한다. |
| `checked` | all | 페이지 로드될 때 미리 선택될 `<input>` 요소를 명시한다. |
| `dirname` | text, search | 폼 데이터가 서버로 제출될 때 서버로 보낼 입력 필드의 텍스트 방향성을 저장할 이름을 명시한다. |
| `disabled` | all | 사용자가 입력 필드를 아예 사용할 수 없도록 설정한다.   `disabled` 속성의 초기값은 전송 버튼을 눌러도 전송 되지 않는다. |
| `form` | all | `<input>` 요소가 하나 이상의 포함될 `<form>` 요소를 명시한다.   이 속성 값은 같은 문서 내에 위치하는 `<form>` 요소의 `id` 값과 일치해야 한다. |
| `formaction` | image, submit | 폼 데이터가 서버로 제출될 때 입력 데이터를 처리할 파일의 URL을 명시한다.   `formaction` 속성은 `<form>` 요소의 `action` 속성값을 재정의\(overrriding\) 한다. |
| `formenctype` | image, submit | 폼 데이터가 서버로 제출될 때 해당 데이터가 인코딩\(encoding\) 되는 방식을 명시한다.   `<form>` 요소의 `method` 속성 값이 `POST` 인 경우에만 사용할 수 있다.   `formenctype` 속성은 `<form>` 요소의 `formenctype` 속성값을 재정의 한다. |
| `formmethod` | image, submit | 폼 데이터가 서버로 제출될 때 사용할 HTTP 메서드를 명시한다.   `formmethod` 속성값으로 `GET`,`POST` 두 가지 중 하나를 선택할 수 있다. |
| `formnovalidate` | image, submit | 폼 데이터가 서버로 제출할 때 해당 데이터의 유효성 검사하지 않음을 명시한다. |
| `formtarget` | image, submit | 폼 데이터가 서버로 제출된 후 받는 응답\(reponse\) 데이터를 어디에 표시할 지를 명시한다. |
| `height` | image | `<input type="image">` 일 경우에는 이미지의 높이를 명시한다. |
| `list` | almost all | `<input>` 요소에 대한 미리 정의된 옵션 리스트를 설정하는 `<datalist>` 요소와 연결하여 사용한다.   `<input>` 요소의 `list` 속성값은 `<datalist>` 요소의 `id` 속성 값과 일치해야 된다. |
| `max` | number, range, date, time, datetime-local, month, week | `<input>` 요소의 입력할 수 있는 최댓값을 명시한다. |
| `maxlength` | password, search, tel, text, url | 입력 필드에 입력할 수 있는 문자의 최대 길이를 설정한다. |
| `min` | number, range, date, time, datetime-local, month, week | `<input>` 요소의 입력할 수 있는 최소값을 명시한다. |
| `minlength` | password, search, tel, text, url | 입력 필드에 입력할 수 있는 문자의 최소 길이를 설정한다. |
| `multiple` | email, file | `<input>` 요소의 값을 두 개 이상 입력하는 것을 허용한다. |
| `name` | all | `<input>` 요소의 이름을 명시한다.   `name` 속성은 폼이 제출된 후 서버에서 폼 데이터를 참조하기 위해 사용된다. |
| `pattern` | password, tel, text | `<input>` 요소의 입력된 값을 검사하기 위한 정규 표현식을 명시한다. |
| `placeholder` | password, search, tel, text, url | `<input>` 요소의 입력되어야 할 값에 대한 힌트를 제공한다. |
| `readonly` | almost all | 사용자가 입력 필드를 볼 수 있으나, 수정할 수 없도록 설정한다.   `disabled` 속성과 다르게 전송 버튼을 누르면 초기값이 서버로 전송된다. |
| `required` | almost all | `<input>` 요소의 입력되어야 할 필수 `<inpnt>` 요소를 명시한다. |
| `size` | email, password, tel, text | 입력 필드에 보여지는 `<input>` 요소의 크기를 설정한다. |
| `src` | image | 제출 버튼으로 사용될 이미지의 URL를 명시한다. |
| `step` | number, range, date, time, datetime-local, month, week | `<input>` 요소의 입력할 수 있도록 허용된 숫자 간격을 명시한다. |
| `type` | all | `<input>` 요소가 나타낼 타입을 명시한다. |
| `value` | all | `<input>` 요소의 입력 필드에 나타나는 초기값을 설정한다. |
| `width` | image | `<input type="image">` 일 경우에는 이미지의 너비를 명시한다. |

### 3. `<label>` Element

사용자 인터페이스 항목의 설명을 나타낸다.

### \(1\). `<label>` → `<input>` Element 연결

label 텍스트는 입력과 시각적으로 관련이 있을뿐만 아니라, 프로그래밍적 으로도 관련이 있다.

회면 리더기\(screenreader\)는 폼 입력\(form input\)에서 label를 읽어서 보조기술\(assistive technology\) 사용자가 입력해야 하는 텍스트가 무엇인지 더 쉽게 이해할 수 있게 한다.

관련 label를 클릭해서 input 자체에 초점을 맞추거나 활성화 시킬 수 있다.

`<label>`를 `<input>` 요소와 연결 시키려면, `<input>`에 id 속성을 넣어야 한다. 그런 다음에 `<label>` 에 **id**와 같은 값의 **for** 속성을 넣어야 한다.

{% code title=" Exmple : label - input 암시적 연결" %}
```markup
<!-- label 안에 input 중첩 시킬 경우, for 및 id 속성은 필요 없다. -->
<label>Do you like peas?
  <input type="checkbox" name="peas">
</label>
```
{% endcode %}

#### 📝other usage notes

label이 붙여진 양식 컨트롤\(form control\)은 **labeled control** 라고 불린다.

연관된 양식\(form control\)이 있는 `<label>`이 클릭 또는 터치 되면, 이벤트 연관된 control를 동작 시킨다.

### \(2\). `<label>` CSS Styling

`<label>`요소는 특별한 고려사항은 없다. 구조적으로 단순한 인라인 요소 이므로 `<span>` 또는 `<a>` 요소와 같은 방식으로 스타일링 할 수 있다.

### \(3\). `<label>` 접근성 고려사항

#### 📝**Interactive content** 

`<label/>` 안에 `<a>` 또는 `<button>`와 같은 인터랙티브 요소를 배치하면, label과 관련된 양식을 입력하기 어렵다.

{% code title="Example : Bad" %}
```markup
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions">
  I agree to the <a href="terms-and-conditions.html">Terms and Conditions</a>
</label>
```
{% endcode %}

{% code title="Example : Good" %}
```markup
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions">
  I agree to the Terms and Conditions
</label>
<p>
  <a href="terms-and-conditions.html">Read our Terms and Conditions</a>
</p>
```
{% endcode %}

#### 📝**title \(제목\)**

제목은 일반적으로 탐색 목적의 보조 도구로 사용되므로 `<label>` 내에 제목 요소를 배치하면 많은 종류의 보조 기술을 방핸한다.

label의 텍스트를 시각적으로 조정해야하는 경우,  `<label>` 요소에 적용된 CSS 클래스를 사용하는게 옳다.

{% code title="Example : Bad" %}
```markup
<label for="your-name">
  <h3>Your name</h3>
  <input id="your-name" name="your-name" type="text">
</label>
```
{% endcode %}

{% code title="Example : Good" %}
```markup
<label class="large-label" for="your-name">
  Your name
  <input id="your-name" name="your-name" type="text">
</label>
```
{% endcode %}

### Reference  <a id="reference"></a>

form  element [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/form)

input  element [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/input)

label  element [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/label)

Forms [→HTML5.2 표준 기술 사양](https://html.spec.whatwg.org/multipage/forms.html#sec-forms)

Formspress - 폼 전송 test [→\(SITE\)](https://formspree.io/)

