# 📄 CSS Cascade and Inheritance

## 1.Inheritance 

상속\(Inheritance\)은 상위\(부모, 조상\) 요소에 적용된 프로퍼티를  하위\(자식, 자손\) 요소가 물려 받는 것을 의미한다.

프로퍼티\(property\) 중에는 상속되는 것과 상속되지 않는 것이 있다.

| property | Inherit |
| :--- | :--- |
| width/height | no |
| margin | no |
| padding | no |
| border | no |
| box-sizing | no |
| display | no |
| visibility | yes |
| opacity | yes |
| background | no |
| font | yes |
| color | yes |
| line-height | yes |
| text-align | yes |
| vertical-align | no |
| text-decoration | no |
| white-space | yes |
| position | no |
| top/right/bottom/left | no |
| z-index | no |
| overflow | no |
| float | no |

### \(1\). Inheritance 제어

CSS는 상속을 제어하기 위한 4가지 특수 범용 속성 값을 제공한다. 모든 CSS 속성은 이러한 값을 허용한다.

#### **\`\`**[**`inherit`**](https://developer.mozilla.org/ko/docs/Web/CSS/inherit)**\`\`**

선택한 요소에 적용된 속성 값을 부모 요소의 속성 값과 동일하게 설정한다. 이것은 **사실상 상속에 영향을 미친다.**

#### **\`\`**[**`intial`**](https://developer.mozilla.org/ko/docs/Web/CSS/initial)**\`\`**

선택한 요소에 적용된 속성 값을 브라우저의 기본 스타일 시트에서 해당 요소의 해당 속성에 설정된 값과 동일하게 설정한다.  브라우저의 기본 스타일에서 값을 설정하지 않고 속성이 자연스럽게 상속되면 속성 값 대신`inherit`되도록 설정한다. 

#### **\`\`**[**`unset`**](https://developer.mozilla.org/ko/docs/Web/CSS/unset)**\`\`**

속성 값을 natural 값으로 재설정 한다. 즉, 속성이 자연적으로 상속되면 `inherit` 된 것 처럼 작동하고 그렇지 않으면 `initial` 처럼 작동한다.

#### **\`\`**[**`revert`**](https://developer.mozilla.org/ko/docs/Web/CSS/revert)**\`\`**

 `revert` 는 현재 엘리먼트에 선언 된 캐스캐이딩된 속성으로부터  [**style origin**](https://developer.mozilla.org/en-US/docs/Glossary/style_origin) 으로 되돌린다. 부모 속성 또는 user agent에 따라 default로 선언 된 속성으로 되돌리는 것이다.

✍ **Exmple**

{% tabs %}
{% tab title="HTML" %}
```markup
<ul>
    <li>Default <a href="#">link</a> color</li>
    <li class="my-class-1">Inherit the <a href="#">link</a> color</li>
    <li class="my-class-2">Reset the <a href="#">link</a> color</li>
    <li class="my-class-3">Unset the <a href="#">link</a> color</li>
</ul>    
```
{% endtab %}

{% tab title="CSS" %}
```css
body {
  color: green;
}

li:first-child a {
  color: blue
}

.my-class-1 a {
  color: inherit;
}

.my-class-2 a {
  color: initial;
}

.my-class-3 a {
  color: unset;
}

```
{% endtab %}

{% tab title="RESULT" %}
![](../.gitbook/assets/.png%20%281%29.png)
{% endtab %}
{% endtabs %}



## 2. Cascading

요소 하나 이상의 CSS 선언에 영향을 받을 수 있다. 이때 충돌을 피하기 위해  CSS 적용 우선 순위 필요하다. 이를 **캐스케이딩 \(cascading\)** 이라고 한다.

### \(1\). Cascading 3가지 규칙

**중요성 \(Importance\)**

**!important** 선언은 다른 선언 보다 우선권을 가진다. ****

✋이때 important가 적용된 속성을 덮어 쓰려면 다시 important를 사용해야 하기에 최대한 절대 사용하지 않도록 노력해야 한다.

**우선 순위 \(Specificity\)**

선택자의 우선권에 대한 척도, 각 척도를 1, 10, 100, 1000 단위로 생각하면 이해하기 쉽다.

✋ 전체 선택자\(\*\), 결합자\(+, &gt;, ~\) 및 부정  pseudo-class \(`:not`\) 는  우선 순위에 영향을 미치치 않는다.

{% tabs %}
{% tab title="CSS 각 척도에 대한 단위" %}
```text
요소 선택자  < 클래스 선택자  < ID 선택자  < 인라인 스타일
(0,0,0,1)     (0,0,1,0)     (0,1,0,0)     (1,0,0,0) 
```
{% endtab %}

{% tab title="CSS 각 척도에 대한 단위 계산" %}
```text
*                         -- 0000
a                         -- 0001
.link                     -- 0010
a[href]                   -- 0011
li:nth-child(2)a:hover    -- 0022
.nav:nth-child(2)a:hover  -- 0031
#outer a                  -- 0101
#outer #inner a           -- 0201
style="color:tan"         -- 1000
                          -- !important   
```
{% endtab %}
{% endtabs %}

#### 소스 순서

**중요성, 우선 순위**가 설정되지 않았거나, 동일한 경우 나중에 나온 소스의 스타일이 우선권을 가진다.



### Reference <a id="reference"></a>

cascade-캐스케이드 [→\(MDN\)﻿](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)



