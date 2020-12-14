# 📄CSS - Type Selector, Class Selector

### 1. X

요소\(타입, 태그\) 선택자 \(element type selector\), 문서 내에 있는 특정 요소를 대상으로 삼는다.

### 2. X\[ \]

속성 선택자 \(attribute selector\), 괄호\(\[ \]\)를 사용해서 ~ 라면 뜻으로 속성이 있는 요만 대상으로 삼는다.

{% tabs %}
{% tab title="HTML" %}
```markup
<ul>
		<li><a href="#internal">Internal link</a></li>
		<li><a href="http://example.com">Example link</a></li>
		<li><a href="#InSensitive">InSensitive internal link</a></li>
		<li><a href="http://example.org">Example org link</a></li>
		<li><a href="https://example.org">Example https org link</a></li>
</ul>

```
{% endtab %}

{% tab title="CSS" %}
```css
a {
	color: black;
	text-decoration: none;
}

/* 속성의 값이 value로 시작하는 요소를 선택 */
a[href^="#"]{
	color: orange;
}

/* 속성의 값이 value를 포함한 요소를 선택 */
a[href*="example"]{
	color: pink;
}

/*  속성의 값이 value로 끝나는 요소를 선택 */
a[href$=".org"]{
	color: red;
}

/*  속성의 값이 value로 시작하면서 value로 끝나는 요소 선택 */
a[href^="https"][href$=".org"]{
	color: green;
}
```
{% endtab %}
{% endtabs %}

### 3. X, Y

그룹 선택자 \(grouping selector\), 동일한 코드를 나눠서 쓰는 것은 비효율적 이기 때문에 콤마\(,\)로 묶어서 대상으로 삼는다.

### 4. \*

전체 선택자 \(universal selector\), 모든 요소를 선택하여 대상으로 삼는다.

### 5. X Y

자손 선택자 \(descendent selector\), 문서 구조에서 특정 요소의 자손을 대상으로 삼는다. 

### 6. X + Y

인접 형제 선택자 \(adjacent sibling selector\), 특정 요소의 바로 뒤에 있는 요소만 선택 대상으로 삼는다.

### 7. X &gt; Y

자식 선택자 \(child selector\),  특정 요소의 **직계 자식만**을 대상으로 삼는다.

예를 들면, `class`가 `container`인 `div`의 직계 자손 `ul`만을 대상으로 삼는다.

```markup
<div class="container">
    <ul>
        <li>list one</li>
        <li>list two</li>
    </ul>
</div>
```

### 8. X ~ Y

일반 형제 선택자\(general sibling selector\) ****, **인접 형 선택자**와 유사 하지만 인접 선택자 보다 덜 엄격하다. 

`ul`안에 모든 `p`요소를 대상으로 삼는다.

```css
ul ~ p {
   color: red;
}
```

### 9. .X .Y

멀티 클래스 선택자 \(mutil class selector\), 점\(.\)을 사용해서 두 개 요소를 연결하여 대상으로 삼는다.

```css
// When one element has two elements
.class1.class2{...}

// When element with class1 finds class2 inside
.class1 .class2{...}
```

###  <a id="reference"></a>

### Reference <a id="reference"></a>

css 선택자 [→\(MDN\)](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

반드시 기억해야 하는 CSS 선택자 30개 [→\(SITE\)﻿](https://code.tutsplus.com/ko/tutorials/the-30-css-selectors-you-must-memorize--net-16048)

