# 📄CSS Type Selector, Class Selector

### 1. X

요소\(타입, 태그\) 선택자 \(Element Type Selector\), 문서 내에 있는 특정 요소를 대상으로 삼는다.

### 2. X\[ \]

속성 선택자 \(Attribute Selector\), 괄호를 사용해서 ~ 라면 뜻으로 속성이 있는 태그만 대상으로 삼는다.

속성 뒤에 눈웃음\(^\) 기호를 사용한다면 속성값이 모두 일치하는 것을 대상으로 삼는다.

속성 뒤에 캐럿\($\) 기호를 사용한다면 끝에 확장자가 끝나는 일치 하는 단어를 모두 대상으로 삼는다.

속성 뒤에 별표\(\*\) 기호를 사용한다면 포함된 단어를 모두 대상으로 삼는다.

### 3. X, Y

그룹 선택자 \(Grouping Selector\), 동일한 코드를 나눠서 쓰는 것은 비효율적 이기 때문에 콤마\(,\)로 묶어서 대상으로 삼는다.

### 4. \*

전체 선택자 \(Universal Selector\), 모든 요소를 선택하여 대상으로 삼는다.

### 5. X Y

자손 선택자 \(Descendent Selector\), 문서 구조에서 특정 요소의 자손을 대상으로 삼는다. 



### 6. X + Y

인접 선택자, 특정 요소의 바로 뒤에 있는 요소만 선택 대상으로 삼는다.

### 7. X &gt; Y

자식 선택자 \(Child Selector\),  특정 요소의 **직계 자식만**을 대상으로 삼는다.

예를 들면, `class`가 `container`인 `div`의 직계 자손 `ul`만을 대상으로 삼는다.

✍ **Exmple**

```markup
<div class="container">
    <ul>
        <li>list one</li>
        <li>list two</li>
    </ul>
</div>
```

### 8. X ~ Y

일반 형제 선택자\(General Sibling Selector\) ****, **인접 선택자**와 유사 하지만 인접 선택자 보다 덜 엄격하다. 

`ul`안에 모든 `p`요소를 대상으로 삼는다.

✍ **Exmple**

```css
ul ~ p {
   color: red;
}
```

### 9. .X .Y

멀티 클래스 선택자 \(Mutil Class Selector\), 점\(.\)을 사용해서 두 개 요소를 연결하여 대상으로 삼는다.

✍ **Exmple**

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

