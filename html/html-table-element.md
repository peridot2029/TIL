# 📄 HTML - Table Element

## 1. `<table>` Element

`<table>` 요소는 데이터를 포함하는 셀\(cell\)들의 **행\(row\)**과 **열\(colum\)**로 구성된 **2차원 테이블**을 정의할때 사용한다. 

`<table>`  요소는 자식 요소인 하나 이상의 `<tr>`, `<th>`, `<td>` 요소들로 구성한다.

`<table>` 요소는 **레이아웃 목적이 아닌 도표의 의미가 필요할 때 사용한다.**

## **2. `<tr>`Element**

테이블에서 셀들로 이루어진 하나의 **행\(row\)**을 정의할 때 사용한다.

`<tr>`요소는 하나 이상의`<td>`, `<th>` 요소를 포함할 수 있다.

## 3. `<th>` Element

`<th>`요소는 제목의 정보를 저장하는 **헤더 셀\(header cell\)**을 정의할 때 사용한다.

### \(1\). `<th>` Element Attribute

| attribute | description |
| :--- | :--- |
| `scope` | 행\(row\) 또는 열\(col\), 행 그룹\(rowgroup\), 열 그룹\(colgroup\)의 제목임을 명시한다. |
| `abbr` | 제목 길이 축약\(abbreviation\)이 필요할때 사용한다. |
| `colspan` | 세로로 열들을 병합 할 때 사용한다. |
| `rowspan` | 가로로 행들을 병합 할 때 사용한다. |

## 4. `<td>` Element

테이블을 구성하는 셀\(cell\)은 `<th>`,`<td>` 요소로 두 가지로 구분된다.

`<td>` 요소는 테이블에서 **하나의 데이터 셀\(data cell\)**을 정의할 때 사용한다.

### \(1\). **`<td>`** Element Attribute

| attribute | description |
| :--- | :--- |
| `headers` | 셀 지목을 하나 이상 연결하여 읽기 용이하도록 구성할 때 사용한다. |
| `colspan` | 세로로 열들을 병합 할 때 사용한다. |
| `rowspan` | 가로로 행들을 병합 할 때 사용한다. |

## 5. `<caption>` Element

`<caption>` 요소는 표의 제목을 나타날 때 사용한다.

이 요소는 ****`<table>`요소의 가장 첫 번째 자식으로 와야 하며, `<table>`요소에서 단 한 번만 사용할 수 있다.

테이블이 레이아웃 용도가 아니라면 `<caption>`요소는 필수로 사용 되어야 한다.

## 6. `<colgroup>`Element

테이블에서 열\(colum\)을 그룹을 만들고자 할 때 사용한다.

`<colgroup>` 요소 내부에는 `<col>` 요소를 포함 하거나, 포함하지 않을 수 있다.

`<colgroup>` 요소는 `<caption>` 요소 다음에 위치해야 되며 선택적으 사용한다.

## 7. `<col>`Element

`<col>` 요소는 `<colgroup>` 요소에 속하는 열을 하나 이상 묶고자 할 때 사용한다.

### \(1\).  `<col>`, `<colgroup>` Element Attribute

`<col>`, `<colgroup>` 요소에서 합쳐질 열\(column\)의 개수를 `span` 속성으로 명시한다.

`<colgroup>` 요소가 `<col>` 요소를 포함하지 않을 경우 `span` 속성으로 열 묶음 개수를 명시한다.

## 6.`<thead>` Element

`<thead>` 요소는 테이블에서 제목 콘텐츠를 그룹화 하는데 사용되며, 테이블 내에서 한 번만 쓸 수 있다.

`<thead>` 요소는 테이블 각 영역을 명시하기 위해서 `<tbody>`, `<tfoot>` 요소와 함께 사용된다.

## 7. `<tbody>` Element

이 요소는 테이블에서 내용 콘텐츠들을 하나의 그룹으로 묶을 때 사용한다.

`<tbody>` 요소는 `<thead>`, `<tfoot>` 요소와 달리 여러번 선언되어 사용할 수 있다.

## 8. `<tfoot>`Element

이 요소는 테이블에서 하단에 위치하며 푸터 콘텐츠들을 하나의 그룹으로 묶을 때 사용한다.

`<tfoot>` 요소는 `<thead>` 요소와 같이 테이블 내에서 한 번만 쓸 수 있다.



### Reference <a id="reference"></a>

table  element [ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/table)

caption element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/caption)

col element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/col)

colgroup element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/colgroup)

tr element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/tr)

thead element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/thead)

tbody element[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/tbody)

tfoot elememt[ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/tfoot)

th element →[\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/th)

td elelement [ →\(MDN\)](https://developer.mozilla.org/ko/docs/Web/HTML/Element/td)

tabular Data[ →HTML5.2 표준 기술 사양﻿](https://html.spec.whatwg.org/multipage/tables.html#tabular-data)









