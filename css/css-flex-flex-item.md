# 📄 CSS -Flex Item

## 1. Flexbox  정의

**flexbox**는 뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때에도 효율적으로 요소를 배치, 정렬, 분산할 수 있는 방법을 제공하는 CSS3의 **새로운 레이아웃 방식**이다.

## 2. Flexbox  → flex item

전체적인 정렬이나 흐름에 관련된 속성은 **flex container**에 정의하고, 자식 요소의 크기나 순서에 관련된 속성은 **flex item**에 정의한다.

![](../.gitbook/assets/flex-base.webp)

### \(1\). flex item → flex

`flex-grow`, `flex-shrink`, `flex-basis` 속성을 축약해서 `flex` 속성으로 표현한다. 

즉, 속성의 값으로 정수 하나만 선언하면, 선언한 값은 `flex-grow` 속성 값이 된다. 

나머지는 기본값인 `flex-shrink : 1` 속성과 `flex-basis : 0` 속성이 적용된다.

| value | description |
| :--- | :--- |
| `1` | `flex : 1` 속성은 `flex : 1 1 0` 속성을 의미한다. |
| `2, 3` | `flex : 2 1 0`, `flex : 3 1 0`을 나타낸다. |

 

### \(2\). flex item → flex-grow

`flex-grow` 속성은 **flex item의 확장에 관련된 속성**이다. 0과 양의 정수를 속성값에 사용한다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">value</th>
      <th style="text-align:left">description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"> <code>0</code> (defalut)</td>
      <td style="text-align:left">
        <p>&#xC18D;&#xC131; &#xAC12;&#xC774; 0 &#xC774;&#xBA74; flex container&#xC758;
          &#xD06C;&#xAE30;&#xAC00; &#xCEE4;&#xC838;&#xB3C4;,</p>
        <p>flex item&#xC758; &#xD06C;&#xAE30;&#xAC00; &#xCEE4;&#xC9C0;&#xC9C0; &#xC54A;&#xACE0;
          &#xC6D0;&#xB798; &#xD06C;&#xAE30;&#xB85C; &#xC720;&#xC9C0;&#xB41C;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>1</code>
      </td>
      <td style="text-align:left">
        <p>&#xC18D;&#xC131; &#xAC12;&#xC774; 1 &#xC774;&#xC0C1;&#xC774;&#xBA74; flex
          container&#xAC00; &#xCEE4;&#xC9C8; &#xB54C;,</p>
        <p>flex item&#xC758; &#xD06C;&#xAE30;&#xB3C4; &#xCEE4;&#xC9C0;&#xAC8C; &#xD558;&#xB824;&#xBA74;
          1 &#xC774;&#xC0C1;&#xC758; &#xAC12;&#xC744; &#xC18D;&#xC131; &#xAC12;&#xC73C;&#xB85C;
          &#xC124;&#xC815;&#xD55C;&#xB2E4;.</p>
        <p>flex item&#xC740; &#xC6D0;&#xB798; &#xD06C;&#xAE30;&#xC640; &#xC0C1;&#xAD00;
          &#xC5C6;&#xC774; flex container&#xB97C; &#xCC44;&#xC6B0;&#xB3C4;&#xB85D;
          flex item&#xC758; &#xD06C;&#xAE30;&#xAC00; &#xCEE4;&#xC9C4;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>

### \(3\). flex item → flex-shrink

`flex-shrink` 속성은 **flex item의 축소에 관련된 속성**이다. 0과 양의 정수를 속성값에 사용한다. 기본값은 1이다.

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left">description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>0</code>
      </td>
      <td style="text-align:left">
        <p>&#xC18D;&#xC131; &#xAC12;&#xC774; 0 &#xC774;&#xBA74; flex container&#xC758;
          &#xD06C;&#xAE30;&#xAC00; flex item&#xC758; &#xD06C;&#xAE30;&#xBCF4;&#xB2E4;
          &#xC791;&#xC544;&#xC838;&#xB3C4;</p>
        <p>&#xD06C;&#xAE30;&#xAC00; &#xC904;&#xC5B4;&#xB4E4;&#xC9C0; &#xC54A;&#xACE0;
          &#xC6D0;&#xB798; &#xD06C;&#xAE30;&#xB85C; &#xC720;&#xC9C0;&#xB41C;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>1</code>(defalut)</td>
      <td style="text-align:left">
        <p>&#xC18D;&#xC131; &#xAC12;&#xC774; 1 &#xC774;&#xC0C1; &#xC774;&#xBA74;,
          flex container&#xC758; &#xD06C;&#xAE30;&#xAC00; flex item&#xC758; &#xD06C;&#xAE30;&#xBCF4;&#xB2E4;
          &#xC791;&#xC544;&#xC9C8; &#xB54C;</p>
        <p>flex item&#xC758; &#xD06C;&#xAE30;&#xAC00; flex container&#xC5D0;&#xAC8C;
          &#xB9DE;&#xCD94;&#xC5B4; &#xC904;&#xC5B4;&#xB4E0;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>

### \(4\). flex item → flex-basis

{% hint style="warning" %}
속성 값을 0 으로 선언할 때에는 `flex-basis: 0px`, `flex-basis: 0%`와 같은 단위도 함께 

설정해야 된다.
{% endhint %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">value</th>
      <th style="text-align:left">description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>px</code>,<code> %</code>, <code>em</code>,<code> rem</code>
      </td>
      <td style="text-align:left">
        <p><code>width</code> &#xC18D;&#xC131;&#xC5D0;&#xC11C; &#xC0AC;&#xC6A9;&#xD558;&#xB294;
          &#xBAA8;&#xB4E0; &#xB2E8;&#xC704;(<code>px, %, em, rem</code>)&#xB97C;
          &#xC18D;&#xC131; &#xAC12;&#xC5D0; &#xC0AC;&#xC6A9;&#xD560; &#xC218; &#xC788;&#xB2E4;.</p>
        <p>&#xC18D;&#xC131; &#xAC12;&#xC744; px &#xB610;&#xB294; %&#xC640; &#xAC19;&#xC740;
          &#xB2E8;&#xC704;&#xB97C; &#xC0AC;&#xC6A9;&#xD574;&#xC11C; &#xC124;&#xC815;&#xD55C;&#xB2E4;&#xBA74;
          flex item&#xC758; &#xD06C;&#xAE30;&#xAC00; &#xACE0;&#xC815;&#xB41C;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>0</code>
      </td>
      <td style="text-align:left">
        <p>&#xC18D;&#xC131; &#xAC12;&#xC744; 0&#xC73C;&#xB85C; &#xC124;&#xC815;&#xD558;&#xBA74;,
          flex item&#xC740; &#xC808;&#xB300;&#xC801; flex item(absoulte flex item)&#xC774;
          &#xB418;&#xC5B4;</p>
        <p>flex container &#xAE30;&#xC900;&#xC73C;&#xB85C; &#xD06C;&#xAE30;&#xAC00;
          &#xACB0;&#xC815;&#xB41C;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>auto</code>(defalut)</td>
      <td style="text-align:left">&#xC18D;&#xC131; &#xAC12;&#xC744; auto&#xB85C; &#xC124;&#xC815;&#xD558;&#xBA74;
        flex item&#xC740; &#xC0C1;&#xB300;&#xC801; flex item(relative flex item)&#xC774;
        &#xB418;&#xC5B4; &#xCF58;&#xD150;&#xCE20;&#xC758; &#xD06C;&#xAE30;&#xB97C;
        &#xAE30;&#xC900;&#xC73C;&#xB85C; &#xD06C;&#xAE30;&#xAC00; &#xACB0;&#xC815;&#xB41C;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>

![](../.gitbook/assets/helloworld-201811-flex_10.png)

### \(5\). flex item → order

`order` 속성은 flex item의 순서와 관련된 속성이다. 0 부터 값이 클수록 밀리기 때문에 정수와 음수를 속성 값에 사용한다. 기본 값은 0 이다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">value</th>
      <th style="text-align:left">description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>0</code>(defalut)</td>
      <td style="text-align:left">&#xAE30;&#xBCF8; &#xAC12;&#xC740; 0 &#xC774;&#xACE0; &#xC18D;&#xC131;
        &#xAC12;&#xC5D0; &#xB530;&#xB77C;&#xC11C; &#xBC30;&#xCE58; &#xC21C;&#xC11C;&#xAC00;
        &#xACB0;&#xC815;&#xB41C;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>-1</code>
      </td>
      <td style="text-align:left">
        <p>&#xC18D;&#xC131; &#xAC12;&#xC744; -1&#xC73C;&#xB85C; &#xC124;&#xC815;&#xD558;&#xBA74;,
          order&#xC758; &#xAE30;&#xBCF8;&#xAC12; &#xBCF4;&#xB2E4; &#xC791;&#xC740;
          &#xC74C;&#xC218; &#xAC12; &#xC774;&#xAE30; &#xB54C;&#xBB38;&#xC5D0;</p>
        <p>&#xAC00;&#xC7A5; &#xBA3C;&#xC800; &#xD45C;&#xC2DC;&#xD560; &#xC218; &#xC788;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>1</code>
      </td>
      <td style="text-align:left">
        <p>&#xB2E4;&#xB978; flex item&#xB4E4;&#xC744; &#xC18D;&#xC131; &#xAC12;&#xC744;
          &#xAE30;&#xBCF8;&#xAC12;&#xC73C;&#xB85C; 0&#xC73C;&#xB85C; &#xC124;&#xC815;
          &#xD6C4;,</p>
        <p>&#xC5B4;&#xB5A4; flex item&#xC758; &#xC18D;&#xC131; &#xAC12;&#xC744; 1&#xB85C;
          &#xC124;&#xC815;&#xD55C;&#xB2E4;&#xBA74;, &#xAC00;&#xC7A5; &#xB9C8;&#xC9C0;&#xB9C9;&#xC5D0;
          &#xD45C;&#xC2DC; &#xB41C;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>

✍ **Exmple**

{% tabs %}
{% tab title="HTML" %}
```markup
<h2>flex item - order</h2>
<div class="flex-container">
  <!-- order : 5 -->
  <div class="item">1</div>
  <!-- order: 4 -->
  <div class="item">2</div>
  <!-- order : 2 -->
  <div class="item">3</div>
  <!-- order : 1 -->
  <div class="item">4</div>
  <!-- order : 3 -->
  <div class="item">5</div>
  <!-- order : 7 -->
  <div class="item">6</div>
 <!-- order : 6 -->
  <div class="item">7</div>
</div>
```
{% endtab %}

{% tab title="CSS" %}
```css
body {
	margin: 0 350px;
}

/* flex container */
.flex-container {
	display: flex;
	flex-flow: row wrap;
	height: 130px;
	border: 1px solid transparent;
	box-shadow: 0 0 0 1px #d9d9d9;
}

/* flex item */
.item {
	flex: 1 0 50px;
	display: flex;
	justify-content: center;
	align-items: center;
	margin-bottom: 1px;
	line-height: 1;
	font-size: 2rem;
	text-align: center;
	color: #fff;
}

/* order */
.item:nth-child(1) {
	order: 5;
	background: #d9727b;
}

.item:nth-child(2) {
	order: 4;
	background: #735454;
}

.item:nth-child(3) {
	order: 2;
	background: #342c40;
}

.item:nth-child(4) {
	order: 1;
	background: #f2ad94;
}

.item:nth-child(5) {
	order: 3;
	background: #f2d0c4;
}

.item:nth-child(6) {
	order: 7;
	background: #469aee;
}

.item:nth-child(7) {
	order: 6;
	background: #141cab;
}

```
{% endtab %}

{% tab title="RESULT" %}
![](../.gitbook/assets/.png%20%282%29.png)
{% endtab %}
{% endtabs %}

### \(6\). flex item → align-self

`align-self` 속성은 flex item 교차 축\(cross axis\)에 정렬 관련된 속성이다.

flex container 내에 있는 모든 flex item의 정렬하는 방법은 `align-items` 속성을 사용해서 정렬한다. 

필요에 의해서 일부 flex item만 정렬 방법을 변경할 경우에 `align-self` 를 사용한다.

| value | description |
| :--- | :--- |
| `auto`\(defalut\) | 기본 값은 `auto`로 flex container의 `align-items` 속성을 상속 받는다. |
| `stretch` | flex container의 교차축을 채우기 위해 flex item을 늘린다. |
| `flex-start` | flex item 각 줄의 시작점 \(flex-start\)으로 정렬한다. |
| `flex-end` | flex item 각 줄의 끝점 \(flex-end\)으로 정렬한다. |
| `center` | flex item 가운데\(center\)로 정렬한다. |
| `baseline` | flex item을 문자 기준선에 정렬한다. |

![](../.gitbook/assets/flex-align-self.webp)

###  Reference <a id="reference"></a>

A Complete Guide to Flexbox [→\(CSS-TRICKS\)](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)​‌

CSS flexible 레이아웃: flex item의 팽창과 수축. [→\(SITE\)](https://naradesign.github.io/article/)​‌

Typical use cases of Flexbox [→\(MDN\)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Typical_Use_Cases_of_Flexbox)​‌

Flexbox 이해: 당신이 알아야 할 모든 것 \(Understanding Flexbox: Everything you need to know\) [→\(SITE\)](https://www.vobour.com/4-flexbox-%EC%9D%B4%ED%95%B4-%EB%8B%B9%EC%8B%A0%EC%9D%B4-%EC%95%8C%EC%95%84%EC%95%BC-%ED%95%A0-%EB%AA%A8%EB%93%A0-%EA%B2%83-understa)​‌

Flex 완벽 가이드 → [\(SITE\)](https://heropy.blog/2018/11/24/css-flexible-box/)​‌

flexbox로 만들 수 있는 10가지 레이아웃 [→ \(NAVER\)](https://d2.naver.com/helloworld/8540176)​‌

플렉스 박스 레이아웃 [→\(SITE\)](https://poiemaweb.com/css3-flexbox)​‌

Flex 지원 범위 [→\(Can I Use\)](https://caniuse.com/#search=flexbox)



