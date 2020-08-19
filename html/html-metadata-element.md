# 📄 HTML Metadata Element

## 1. `<head>` Element

 문서의 제목과 스타일시트, 스크립트 링크 또는 선언은 포함하는 문서의 일반적인 정보\(메타데이터\)를 제공한다. 대부분 브라우저는 마크업에서 `<head>` 요소가 생략될 경우, 자동으로 `<head>` 요소를 생성하지만 일부는 그렇지 않다.

{% tabs %}
{% tab title="자동으로 <head> 요소를 생성하지 않는 브라우저 환경" %}
Android\(1.6\), iPhone \(3.1.3\), iOpera\(9.27\), Safari\(3.2.1\), Nokia\(90\)
{% endtab %}
{% endtabs %}

## 2. `<title>` Element

브라우저의 타이틀 바\(Title Bar\)나 페이지 탭에 보여지는 문서의 제목을 정의한다.텍스트만 포함할 수 있으며 포함된 태그들은 해석되지 않는다.

## 3. `<meta>` Element

 다른 메타 요소들 `<title>, <base>, <link>, <style>`로 나타낼 수 없는 메타데이터를 정의할 때 사용한다.

### \(1\)  메타데이터의 종류

{% tabs %}
{% tab title="charset이 설정된 경우" %}
 charset 선언 즉,  웹페이지를 작성하는 일련 형식에 사용되는 문자 인코딩 \(charset\)에 대한 설정, 이 속성보다 요소의 lang 속성이 우선하여 적용된다.`ex) <div lang="fr">`
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="http-equiv 속성이 설정된 경우" %}
pragma 지시어\(directive\)로 일반적으로 웹서버가 제공하는 웹페이지가 어떻게 제공되어야 하는지에 대한 정보를 제공한다.
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="name 속성이 설정된 경우" %}
문서 수준 메타 데이터의 이름을 정의하며, content 속성 값을 통해 설정한다.
{% endtab %}
{% endtabs %}

✍ **Exmple**

```markup
<!-- HTML 5 is no longer recommended for use as follows. -->
<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">

<!-- Move to url page value after 3 seconds. -->
<meta http-equiv="refresh" content="3;url=https://google.com">
```

## 4. `<link>` Element

현재 문서와 외부 리소스와의 관계\(relation\)를 명시한다.이 요소는 스타일시트를 링크 하는데 가장 많이 사용된다.

✍ **Exmple**

{% tabs %}
{% tab title="Dafalut" %}
```markup
<!-- Set Default Style -->
<link href="style.css" rel="stylesheet">
```
{% endtab %}

{% tab title="Alternate " %}
```markup
<!-- Alternate Style Sheet Settings -->
<link href="default.css" rel="stylesheet" title="DefaultStyle">
<link href="fancy.css" rel="alternate stylesheet" title="Fancy">
<link href="basic.css" rel="alternate stylesheet" title="Basic">
```
{% endtab %}
{% endtabs %}

## 5. `<style>` Element

문서 또는 문서 일부에 대한 정보를 포함한다. 기본적으로 CSS 언어가 사용된다.

✍ **Exmple**

{% tabs %}
{% tab title="Basic " %}
```markup
<!-- basic Style -->
<style type="text/css">
    body {color: #323232;}
</style>
```
{% endtab %}

{% tab title="Scoped " %}
```markup
<!-- scoped elements is no browser that supports it properly. -->
<section>
    <style scoped>
        p { color: #902c1f; }
    </style>
    <p> ... </p>
</section>
```
{% endtab %}
{% endtabs %}

## 6. `<Base>` Element

 문서에 포함된 모든 상대 URL들의 기준 URL을 나타낸다. 한 문서에 하나의 `<base>` 요소만 존재해야 한다.

✍ **Exmple**

```markup
<base target="_blank" href="http://www.example.com/">
```

### Reference <a id="reference"></a>

head - 헤드 요소[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/head)

title - 문서 타이틀 요소[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/title)

meta-링크 요소[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/meta)

link - 스타일 요소[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/link)

style - 스타일 요소[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/style)

base - 베이스 요소[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/base)

Document Metadata[ →HTML 5.2 표준 기술 사양﻿](https://html.spec.whatwg.org/multipage/semantics.html)

