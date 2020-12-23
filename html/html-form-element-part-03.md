# 📄 Form Element part 03

### 1. `<textarea>` Element

`<textarea>` 요소는 멀티라인 일반 텍스트 편집 컨트롤을 나타낸다.

#### \(1\). `<textarea>` 요소의 Attribute

#### 📝**autocapitalize**

ios의 webKit에서 지원하는 비표준 속성, 텍스트 값을 입력 또는 편집할 때에 자동으로 대문자 표시할지 여부와 방법을 제어한다.

#### 📝**cols**

평균 문자 너비로 표시되는 텍스트 컨트롤 표시 너비이다. 지정된 경우 양의 정수 여야 한다. 지정되지 않은 경우 기본 값은 `20` 이다.

#### 📝**maxlength**

사용자가 입력할 수 있는 최대 문자 수, 이 값을 지정하지 않으면 사용자는 무제한의 문자를 입력할 수 있다.

#### 📝**minlength**

사용자가 입력해야 하는 최소 문자 수 이다.

#### 📝**name**

컨트롤의 이름

#### 📝**placeholder**

컨트롤 입력 할 수 있는 항목에 표시되는 텍스트

#### 📝**readonly**

Boolean, 사용자가 컨트롤 값을 수정 할 수 없다.

#### 📝**required**

Boolean, 사용자가 양식을 제출 하기 값을 입력해야 한다.

#### 📝**rows**

컨트롤에 표시되는 텍스트 줄 수

#### 📝**wrap**

컨트롤이 텍스트를 래핑하는 방법

#### \(2\). `<textarea>` CSS Styling

`<textarea>`는 기본적 으로 `display` 값은 block 이다.

다른 양식 요소와 비교하여 상자 모델,font, color 등 일반 CSS를 사용하여 쉽게 조작할 수 있다.

#### 📝**기준 불일치**

기준선을 설정하지 않으면 브라우저 마다 설정하는 기준선이 다르다. 그러므로 기준선은 예측할 수 없기  때문에 사용하지 않는게 났다.\(`vertical-align: baseline`\)

#### 📝**텍스트 영역의 크기 조정 가능 여부 제어**

대부분 브라우저에서 `<textarea>`는 크기를 조정할 수 있다.

페이지에 요소의 크기를 변경하는 데 사용할 수 있는 오른쪽 모서리에 드래그 핸들이 있다.

이는 `resize` CSS 속성에 의해 제어된다. 기본적으로 활성화 되어 있지만, 명시적으로 비활성화 할 수 있다.\(`none`\)

```css
textarea {
  resize: none;
}
```

#### **유효하고 유효하지 않은 값 스타일 지정**

`<textarea>` 요소, 예를 들면 그와 설정 경계 여부 `minlength`, `maxlength` 또는 `required`를 사용하여 강조할 수 있다.

`:valid` 및 `:invalid` 가상 클래스, 예를 들면 텍스트 영역이 유효한지 또는 유효하지 않은 지 따라 테두리 값을 지정할 수 있다.

```css
textarea:invalid {
  border: 2px dashed red;
}

textarea:valid {
   border: 2px solid lime;
}
```

### 2. `<fieldset>` Element

`<fieldset>` 요소는 웹 양식의 컨트롤과 `<label>`을 묶을 때 사용한다.

#### 1\)  `<fieldset>` CSS Styling

`<fieldset>`는 기본적 으로 `display` 값은 block 이다.

`<fieldset>`은 기본 스타일로 콘텐츠를 감싸는 `2px` 너비의 groove 테두리, 작은 양의 내부 여백, 그리고 `min-inline-size: min-content`를 갖는다.

`<legend>` 요소는 `<fieldset>`의 블록 시작 방향\(대개 위쪽\) 테두리 위를 가로지르는 위치에 놓인다.

```markup
<form action="#">
  <fieldset>
    <legend>Simple fieldset</legend>
    <input type="radio" id="radio">
    <label for="radio">Spirit of radio</label>
  </fieldset>
</form>
```

### 3. `<legend>` Element

`<legend>` 요소는 부모 `<fieldset>` 콘텐츠의 설명을 나타낸다.

### 4. `<datalist>` Element

`<datalist>` 요소는 다른 컨트롤에서 고를 수 있는 가능한, 혹은 추천하는 선택지를 나타내는 `<option>` 요소 여럿을 담는다.

### 5. `<progress>` Element

`<progress>` 요소는 어느 작업의 완료 정도를 나타내며, 주로 진행 표시줄의 형태로 띈다.

### 6. `<output>` Element

`<output>` 요소는 웹 사이트나 앱에서 계산이나 사용자 행동의 결과를 삽입할 수 있는 컨트롤 데이터 요소 이다.

### 7. `<meter>` Element

`<meter>` 요소는 특정 범위 내에서 스칼라 값, 또는 백분율 값을 나타낸다.

### Reference 

textarea element [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/textarea)

fieldset element [→\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/fieldset)

legend element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/legend)

datalist element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/datalist)

progress element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/progress)

output element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/output)

meter element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/meter)

Forms[ →HTML5.2 표준 기술 사양](https://html.spec.whatwg.org/multipage/forms.html#sec-forms)

Formspress - 폼 전송 test[ →\(SITE\)﻿](https://formspree.io/)

