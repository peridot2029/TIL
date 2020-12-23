# 📄 Introduction

### 1. CSS 란?

CSS는 **Cascading Style Sheet**의 약자로 HTML 요소들이 각 종 미디어에서 어떻게 보이는가를 정의하는데 사용되는 스타일 시트 언어이다.

#### 1\) CSS 사용하는 목적

> HTML만으로 웹 페이지를 제작할 경우 매우 많은 작업이 소요 되며, 작업을 완성한 후에도 스타일의 변경 및 유지 보수가 힘들다. 그래서 W3C에서는 이러한 문제점을 해결하기 위해서 만든 스타일 시트 언어가 바로 CSS 이다.

CSS는 웹 페이지의  스타일을 별도 파일을 저장할 수 있게 해주므로 사이트의 전체 스타일을 손쉽게 제어할 수 있다.

또한 웹 사이트의 스타일을 일관성 있게 유지할 수 있게 해주며, 그에 따른 유지 보수 또한 쉬워진다.

외부 스타일 시트는 보통의 확장자 .css 파일로 저장한다.

### 2. CSS  **Syntax**

![](../.gitbook/assets/css-declaration-small.png)

#### 1\) Selector

**선택자\(selector\)**는 CSS를 적용하고자 하는 HTML 요소를 가리킨다.

#### 2\) Declaration

**선언부\(declaratives\)**에는 하나 이상의 선언들을 **세미콜론\(;\)**으로 구분하여 포함할 수 있으며, **중괄호\({}\)**를 사용하여 전체를 둘러싼다.

각 **선언\(declaration\)**은 CSS **속성명\(property\)**과 **속성값\(value\)**을 가지며,그 둘은 **콜론\(:\)**으로 연결된다. 이러한 CSS 선언은 언제나 마지막에 **세미콜론\(;\)**으로 끝마친다.

#### 3\) Property name

선택한 HTML 요소를 꾸밀 수 있는 방법이다

#### 4\) Property Value

**속성\(property\)**의 오른쪽 **콜론\(:\)** 뒤에 사용할 수 있는 값을 **크기 단위** 또는 **색상 표현 단위** 등의 **특정 단위**로 지정한다.

### 3. CSS Styling

HTML 문서에 CSS 스타일을 적용할 때에는 아래와 같은 세 가지 방법을 사용할 수 있다.

#### 1\) Inline Style

인라인 스타일\(Inline style\)은 HTML 요소 내부에 style 속성을 사용하여 CSS 스타일을 적용하는 방법이다.

인라인 스타일은 해당 요소에만 스타일을 적용할 수 있다.

```markup
<body>
    <h1 style="corlo:red;">css Inline style</h1>
</body>
```

#### 2\) Internal Style Sheet

내부 스타일 시트\(Internal style sheet\)는 HTML 문서 내의 &lt;head&gt; 요소 내에 &lt;style&gt; 요소를 사용하여 CSS 스타일을 적용하는 방법이다.

내부 스타일 시트는 해당 HTML 문서에만 스타일을 적용할 수 있다.

```markup
<head>
    <style>
        h1 { color: red; }
    </style>
</head>
```

#### 3\) External Style Sheet

외부 스타일 시트\(External style sheet\)는 스타일을 적용할 웹 페이지의 &lt;head&gt; 요소에 &lt;link&gt; 요소를 사용하여 외부 스타일 시트를 포함해야만 스타일이 적용된다. 

외부에 작성된 스타일 시트 파일은 .css 파일 확장자를 사용하여 저장한다.

```markup
<head>
    <link rel="stylesheet" type="text/css" href="../css/style.css">
</head>
```

#### 4\) 스타일 적용의 우선 순위

위에서 설명한 스타일 적용 방법들이 혼합되어 사용될 경우 최종적으로는 스타일은 아래와 같은 순서에 따라 결정된다.

1. 인라인 스타일 
2. 내부 또는 외부 스타일 시트
3. 웹 브라우저의 기본 스타일

🔎 인라인 스타일이 적용된 요소에는 외부 스타일 시트와 상관없이 무조건 인라인 스타일이 적용된다.

```markup
<link rel="stylesheet" type="text/css" href="../css/style.css">
...
<h1>External Style Sheet</h2>
<h1 style="color:red;">Inline style</h2>
```















