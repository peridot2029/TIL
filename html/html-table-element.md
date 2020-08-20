# 📄 HTML Table Element

## 1. `<table>` Element

테이블 몸체에 해당되며, 행 \(row\)/열 \(column\) 및 셀 \(cell\)을 포함한다. 복잡한 내용은 x, y 축에 따라서 이해하기 쉽게 데이터를 구조화 하는데 테이블을 사용한다. **가장 좋은 테이블은 최대한 단순하게 표를 구성하는 것이다.**

### **\(1\).** `<table>` 사용 시 주의점

테이블 내에 테이블을 중첩해서는 안된다.

테이블 레이아웃\(배치\) 목적으로 사용해서 안된다. 

`border` 속성을 사용해서 테두리를 그릴 수 있다.

## 2. `<caption>` Element

테이블의 제목을 명시적으로 제공하며, 제작자는 표의 내용을 이해할 수 있도록 정보를 제공해야 한다. 테이블의 내용이 복잡해 설명이 필요하다면 아래의 방법 중 하나를 선택해서 기술한다.

### \(1\). 설명 \(summary\)을 추가하는 방법

`aria-describedby`속성을 사용해 설명 단락\(paragraph\)을 연결한다.

`<figure>` 요소에 `aria-labelledby`속성을 사용해 제목\(caption\)을 연결한다.

✍ **Example**

```markup
<p id="compare-shoes-table">성인 남성 운동화 사이즈 비교 표로 4행 12열로 구성되.</p>
<!-- table에 대한 자세한 내용을 기술할 때 aria-describedby 사용해서 단락의 ID 값을 연결한다. -->
    <table border="1" aria-describedby="compare-shoes-table">
        <caption>성인 남성 운동화 사이즈표</caption>
    </table>
```

## **3. `<tr>`Element**

테이블의 행\(row\)를 말하며, 내부에 셀 제목\(header\),셀 내용\(data\)을 포함한다.

## 4. `<th>` Element

테이블 셀 제목\(header cell in a table\)으로 행\(tr\) 내부에 포함되어야 한다.

| attribute | description |
| :--- | :--- |
| `scope` | 행\(row\) 또는 열\(col\), 행 그룹\(rowgroup\), 열 그룹\(colgroup\)의 제목임을 명시한다. |
| `abbr` | 제목 길이 축약\(abbreviation\)이 필요할때 사용한다. |
| `colspan` | 열\(column\)을 그룹 지울때 사용한다. |
| `rowspan` | 행\(row\)을 그룹 지울 떄 사용한다. |

## 5. `<td>` Element

테이블 셀 내용\(data cell in a table\)으로 행\(tr\) 내부에 포함되어야 한다.

| attribute | description |
| :--- | :--- |
| `headers` | 셀 지목을 하나 이상 연결하여 읽기 용이하도록 구성할 때 사용한다. |
| `colspan` | 열\(column\)을 그룹 지울때 사용한다. |
| `rowspan` | 행\(row\)을 그룹 지울  사용한다. |

## 6.`<thead>` Element

테이블 행 블록\(row block\) 내에 제목 열 그룹\(column headers\)으로 구성할 경우 사용한다. 선택적\(option\) 으로 사용한다. \(필수 아니다\)

## 7. `<tbody>` Element

행 블록 내에 테이블 데이터로 구성할 때 사용한다. 선택적\(option\)으로 사용한다.\(필수 아니다\)

## 8. `<tfoot>`Element

행 블록 내에 열 요약\(column summaries\)로 구성할 때 사용한다. 선택적\(option\)으로 사용한다. \(필수 아니다\)

## 9. `<col>`Element

테이블 열\(column\)을 하나 이상 묶고자 할 때 사용한다.일반적으로 colgroup 요소 내부에 포함시킨다. 선택적\(option\)으로 사용한다. \(필수 아니다\)

## 10. `<colgroup>`Element

테이블 열\(column\) 그룹을 만들고자 할 때 사용한다.내부에 col 요소를 포함하거나, 포함하지 않을 수 있다. 선택적\(option\)으로 사용한다. \(필수 아니다\)

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









