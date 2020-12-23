# 📄 Selectors

### 1. Basic Selector

#### 1\) Universal selector

전체 선택자\(Universal selector\)는 `*`기호를 사용해서 모든 HTML 요소를 선택한다.

```css
* {
 margin: 0;
 padding: 0;
}
```

#### 2\) Type selector

타입 선택자\(Type selector\)는 `<h1>, <p>,` `<span>`, `<div>` 등 HTML 요소를 직접 선택한다.

#### 3\) Class selector

특정 집단\(class\)을 클래스 라고 하며, 같은 클래스 이름을 가지는 요소들을 모두 선택한다.

#### 4\) ID selector

웹 페이지에 포함된 여러 요소 중 **특정 ID**를 가지는 요소만 선택한다.

#### 5\) Attribute selector

속성 선택자\(Attribute selector\)는 특정 속성\(attribute\)를 갖고 있거나, 특정 속성이 특정 값 등을 갖고 있는 요소를 선택한다.

* `[attributename]`
  * attribute name 속성을 가진 요소를 선택한다.
* `[attributename="value"]`
  * arribute name 속성의 값이 value인 요소를 선택한다.
* `[attributename~="value"]`
  * attribute name 속성의 값이 value를 포함한 요소를 선택한다.
* `[attributename|="value"]`
  * attribute name 속성의 값이 value이거나 value~로 시작하는 요소를 선택한다.
* `[attributename^="value"]`
  * attribute name 속성의 값이 value로 시작하는 요소를 선택한다.
* `[attributename$="value"]`
  * attribute name 속성의 값이 value로 끝나는 요소를 선택한다.
* `[attributename*="value"]`
  * attribute name 속성의 값이 value를 포함한 요소를 선택한다

### 2. Grouping Selector

#### 1\) Selector list

그룹 선택자\(Selector list\)는 여러 선택자를 같이 사용하고자 할 때 쉼표\(,\)로 구분하여 연결한다.

```css
div,
span {
	border: 1px solid orange;
}
```

### 3. Combinator

연결자\(Combinator\)는 연관된 선택자들의 관계를 설정한다.  CSS는 하나 이상의 선택자를 포함할 수 있다.

#### 1\) Adjacent sibling selector, \(A + B\)

인접 형제 선택자\(Adjacent sibling selector\)는 `+`기호를 사용하며, A 요소 바로 뒤에 존재하는 첫 번째 B 요소만 선택한다.

```css
ul+p {
  color: red;
}
```

#### 2\) General sibling selector, \(A ~ B\)

일반 형제 선택자\(General sibling selector\)는 `~`기호를 사용하며, A 요소 뒤에 있는 모든 B 요소를 선택한다.

```css
ul~p {
  color: red;
}
```

#### 3\) Child selector, \(A &gt; B\)

자식 선택자\(Child selector\)는  `>`  기호를 사용하며, A 요소의 직계 자손인 B만 선택한다.

{% tabs %}
{% tab title="HTML" %}
```markup
<div class="container">
   <ul>
      <li> List Item
        <ul>
           <li> Child </li>
        </ul>
      </li>
      <li> List Item </li>
      <li> List Item </li>
      <li> List Item </li>
   </ul>
</div>
```
{% endtab %}

{% tab title="CSS" %}
```css
.container > ul {
  border: 1px solid black;
}
```
{% endtab %}
{% endtabs %}

#### 4\) Descendant selector, \(A B\)

자손 선택자\(Descendant selector\)는 `공백(space)`를 사용하여 구분하며, A 요소의 자손인 모든 B 요소를 선택한다.

```css
li a {
  text-decoration: none;
}
```

### 4. Pseudo <a id="reference"></a>

#### 1\) Pseudo classes

가상 클래스\(Pseudo class\)는 웹 문서에는 실제로 존재하지 않지만 필요에 의해 임의로 가상의 선택자를 지정한다.

* `:active`
  * 해당 요소가 활성되었을 때, 클릭한 상태
* `:checked`
  * radio, checkbox가 체크된 상
* `:first-child`
  * 부모 안에 있는 모든 요소 중 첫 번째 요소
* `A:first-of-type`
  * 부모 안에 A 라는 요소 중 첫 번째 요소
* `:focus`
  * 해당 요소에 초점이 맞춰졌을 때 적용, 텍스트 필드 안에 초점이 맞춰진 상태
* `:hover`
  * 마우스 포인터로 해당 요소에 초점이 맞춰진 상태
* `:lang`
  *  ****`lang`속성을 가진 요소를 선택
* `:last-child`
  * 부모 안에 모든 요소 모든 요소 중 마지막 요소
* `A:last-of-type`
  * 부모 안에 A 라는 요소 중 마지막 요
* `:link`
  * 웹 문서안의 하이퍼 링크 중 아직 방문하지 않은 링크에 적용
* `:nth-child(n)`
  * 부모 요소 안에 모든 요소 중 n번째 요소, 괄호 안에는 홀수\(odd\), 짝수\(even\), 수식\(2n+1\)등을 사
* `A:nth-of-type(n)`
  * 부모 요소 안에 A 라는 요소 중 n 번째 요
* `:visited`
  * 한 번 이상 방문한 사이트에 적용, 기본 색상이 자주색

#### 2\) Pseudo elements

가상 요소\(Pseudo element\)는선택한 요소의 일부분에만 스타일을 적용한다.

* `::first-letter`
  * 첫 번째 줄의 첫 글자를 선택
* `::first-line`
  * 첫 번째 줄을 선택
* `::before`
  * 요소의 앞을 선택
* `::after`
  * 요소의 뒤를 선택

### Reference <a id="reference"></a>

css selector [→\(MDN\)](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

반드시 기억해야 하는 CSS 선택자 30개 [→\(SITE\)﻿](https://code.tutsplus.com/ko/tutorials/the-30-css-selectors-you-must-memorize--net-16048)

가상 선택자 정리 및 비교 [→\(SITE\)﻿](https://lalacode.tistory.com/6)

