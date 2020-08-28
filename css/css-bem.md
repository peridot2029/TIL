# 📄 CSS - BEM

## 1. BEM 기본 구조

BEM은 **block, element, modifer** 세 가지를 뜻한다. 그리고 각각 `--` 와 `__`로 구분한다.

BEM은 기본적으로 id를 사용하지 않으면, class 만을 사용한다.

또한 "어떻게 보이는가" 아니라 "어떠한 목적"인가에 따라서 이름을 짓는다.

이름을 연결할 때에는 `block-name` 과 같이 하이픈 하나만 써서 연결한다.

✍ **Exmple**

```css
// block - header, element - navigation, Modifier - navi-text 
.header__navigation--navi-text {
  color: red;
}
```

## 2. Block / Element / Modifier

### \(1\) Block

재사용 가능한 기능적인 독립적인 페이지 컴포넌트를 **block** 이라고 부른다.

### \(2\) Element

**element**는 **block**를 구성하는 단위이다. **element**는 자신 속한 블럭 내에서만 의미를 가진다. 그러므로 블럭 안에서 떼어다가 다른 데서 사용할 수 없다.

**block**은 독립적인 형태, **element**는 의존적인 형태 이다.

✍ **Exmple**

{% tabs %}
{% tab title=" BEM Incorrect Usage" %}
```markup
<form class="search-form">
  <div class="search-form__content">
      <input class="search-form__content__input"/>
      <button class="search-form__content__button">Search</button>
  </div>
</form>
```
{% endtab %}

{% tab title="BEM Correct Usage" %}
```markup
<form class="search-form">
  <div class="search-form__content">
      <input class="search-form__input"/>
      <button class="search-form__button">Search</button>
  </div>
</form>
```
{% endtab %}
{% endtabs %}

### \(3\) Modifier

block 또는 element의 **모양\(color, size\), 상태\(disabled, checked\)**를 정의한다.

**modifier**를 사용하기 위해서는 **block** 다음에 `--`를 추가하여 작성한다.



✍ **Exmple - BEM Correct Usage**

```css
.block‐‐modifier {
  
} 
 
.block__element‐‐modifier {
  
}

```

### Reference <a id="reference"></a>

 BEM File Structure [→\(SITE\)](https://en.bem.info/methodology/filestructure/)

[﻿](https://redux.js.org/recipes/reducing-boilerplate#actions)



