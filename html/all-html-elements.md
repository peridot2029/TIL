# 📄 All HTML Elements

### 개요

* HTML5 기준으로 작성한다.
* 더 이상 사용되지 않는\(deprecated\) 요소나 속성은 제외한다.
* 의미론적\(semantic\)인 내용 위주로 작성한다.
* 빈 태그\(empty tags\)는 `<TAG />`와 같이 `/`를 포함하여 표시한다.
* 해당 요소에 필수적으로 사용되어야 하는 속성\(required attributes\)은 설명에 `(필수)`를 표시한다. \(그 외는 모두 선택 속성\)

### 주요 범위

#### &lt;html&gt;

HTML 문서의 범위를 지정.

| attribute | description | value |
| :--- | :--- | :--- |
| lang | 문서의 언어\([ISO 639-1](https://ko.wikipedia.org/wiki/ISO_639-1_%EC%BD%94%EB%93%9C_%EB%AA%A9%EB%A1%9D)\) | `ko`, `en` |

#### &lt;head&gt;

HTML 문서의 정보를 설정.

#### &lt;body&gt;

HTML 문서의 구조를 설정.

### 메타데이

#### &lt;title&gt;

웹 브라우저의 표시줄 또는 페이지 탭에서 보여지는 문서의 제목을 설정.

#### &lt;base/&gt;

HTML 문서에 포함된 모든 상대 URL들의 기준 URL를 설정.

* 한 문서에 하나의 `<base/>` 요소만 포함 가능.

<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">href</td>
      <td style="text-align:left">&#xAE30;&#xC900; URL</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">target</td>
      <td style="text-align:left"><code>&lt;a&gt;</code> &#xC694;&#xC18C;&#xCC98;&#xB7FC; <code>target</code> &#xC18D;&#xC131;&#xC744;
        &#xC0AC;&#xC6A9;&#xD558;&#xB294; &#xC694;&#xC18C;&#xC758; &#xAC12;</td>
      <td
      style="text-align:left">
        <p><code>_self(default)</code>,</p>
        <p><em> </em><code>_blank</code>
        </p>
        </td>
    </tr>
  </tbody>
</table>

#### &lt;link/&gt;

외부 리소스의 연결 및 현재 문서와의 관계를 명시. \(HTML, CSS, ICON 등 가져오기\)

| attribute | description | value |
| :--- | :--- | :--- |
| rel | \(필수\)현재 문서와 리소스의 관 |  `stylesheet`, `icon` |
| href | 외부 리소스 URL | URL |
| type | 외부 리소스 MIME  타입 | `text/css`, `images/x-icon` |

#### &lt;meta/&gt;

기타 메타 데이터 요소\(`<link/>`, `<style>`\)로 나타낼 수 없는 메타데이터를 나타내기 위해 설정. \(검색 엔진 또는 웹 브라우저에서 정보를 제공\)

<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">charset</td>
      <td style="text-align:left">&#xBB38;&#xC790;&#xC778;&#xCF54;&#xB529; &#xBC29;&#xC2DD;</td>
      <td style="text-align:left"><code>UTF-8</code>, <code>EUC-KR</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">&#xBA54;&#xD0C0; &#xB370;&#xC774;&#xD130;&#xC758; &#xC774;&#xB984;, &#xC815;&#xBCF4;&#xC758;
        &#xC885;&#xB958;</td>
      <td style="text-align:left"><code>author</code>, <code>description</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">http-equiv</td>
      <td style="text-align:left">
        <p>&#xC11C;&#xBC84;/&#xC0AC;&#xC6A9;&#xC790; &#xC5D0;&#xC774;&#xC804;&#xD2B8;&#xC758;
          &#xC791;&#xB3D9;&#xBC29;&#xC2DD; &#xBCC0;&#xACBD;&#xC5D0; &#xB300;&#xD55C;
          &#xC9C0;&#xC2DC;</p>
        <p>(HTTP &#xC751;&#xB2F5; &#xD5E4;&#xB354; &#xC81C;&#xACF5;)</p>
      </td>
      <td style="text-align:left"><code>refresh</code>, <code>X-UA-Compatible</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">content</td>
      <td style="text-align:left"><code>name</code>, <code>http-equiv</code>&#xC758; &#xAC12;</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

#### &lt;style&gt;

스타일 정보\(CSS\)를 설정.

### 콘텐츠 구분

#### &lt;h1&gt;, &lt;h2&gt;, &lt;h3&gt;, &lt;h4&gt;, &lt;h5&gt;, &lt;h6&gt;

문서의 정보 계층을 구조화 하고 숫자가 낮을 수록 높은 단계의 중요한 제목.

#### &lt;header&gt;

문서의 헤더를 설정. \(로고, 제목, 검색 등을 포함\)

#### &lt;footer&gt;

문서의 푸터를 설정. \(작성자, 저작권, 관련 문서 등을 포함\)

#### &lt;main&gt;

문서의 주요 콘텐츠를 설정.

* IE 지원 불가
* 한 문서에 하나의 `<main>` 요소만 포함 가능.

#### &lt;article&gt;

독립적으로 구분되거나 재사용 가능한 영역을 설정. \(매거진/신문, 기사, 블로그 등\)

* 일반적으로 `<article>` 요소를 사용할때는 `<h1>`~`<h6>` 제목 요소를 포함하여 식별.

#### &lt;section&gt;

문서의 일반적인 영역을 설정.

* 일반적으로 `<section>` 요소를 사용할때는 `<h1>`~`<h6>` 제목 요소를 포함하여 식별.

#### &lt;aside&gt;

문서의 별도 콘텐츠를 설정. \(광고, 기타 링크, 사이드바\(side bar\)를 설정\)

#### &lt;nav&gt;

다른 페이지 링크를 제공하는 영역을 설정. \(보통 메뉴, 목차, 색인 등을 설정\)

#### &lt;address&gt;

`<body>`, `<article>`, `<footer>` 등에서 연락처 정보를 제공하기 위해 포함하여 사용.

#### &lt;div&gt;

본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정. \(꾸미는 목적으로 사용\)

### 문자 콘텐츠

#### &lt;ol&gt;, &lt;ul&gt;, &lt;li&gt;

각 항목 `<li>`의 정렬된 목록 `<ol>`이나, 정렬되지 않은 목록 `<ul>`을 설정.

* `<ol>`과`<ul>`은 자식으로 &lt;li&gt;만 포함 가능.
* `<li>`는 단독으로 사용할 수 없으며, `<ol>`이나`<ul>` 자식으로 포함되어야 한다.
* 정렬된 목록 `<ol>`의 항목 순서는 중요도를 의미할 수 있다.

#### &lt;ol&gt;

정렬된 목록을 설정.

| attribute | description | value |
| :--- | :--- | :--- |
| start | 항목에 매겨지는 번호의 시작 값 | number |
| type | 항목에 매겨지는 번호의 유형 | `a`, `A`, `i`, `I`, `1` |

#### &lt;li&gt;

항목을 설정.

| attribute | description | value |
| :--- | :--- | :--- |
| value | 항목의 순서를 설정 | number |

#### &lt;dl&gt;, &lt;dt&gt;, &lt;dd&gt;

용어 `<dt>`와 정의 `<dd>` 쌍들의 영역 `<dl>`을 설정.

* `<dl>`은 `<dd>`, `<dt>`만은 포함해야 한다.
* key/value 형태를 표시할 때 유용.

#### &lt;p&gt;

하나의 문단을 설정

* 일반적으로 정보통신보조기기 등 다음 문단 `<p>` 으로 넘어갈 수 있는 단축키를 제공한다.

#### &lt;hr/&gt;

문단의 분리\(주제에 의한\)를 위한 설정.

* 대부분의 경우 수평선\(border\)으로 표시\(표현적 관점\)되나 의미적 관점으로만 사용해야 한다.

#### &lt;pre&gt;

서식이 미리 지정된 텍스트를 설정.

* 텍스트의 공백과 줄바꿈을 유지하여 표시 할 수 있다.
* 기본적으로 Monospace 글꼴로 계열로 표시된다.

#### &lt;blockquote&gt;

일반적인 인용문을 설정.

| attribute | description | value |
| :--- | :--- | :--- |
| cite | 인용된 정보의 URL | URL |

### 인라인 텍스트

#### &lt;a&gt;

다른 페이지, 같은 페이지 위치\(\#\), 파일, 이메일 주소, 전화번호 등 다른 URL로 연결할 수 있는 하이퍼링크를 설정.

<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">download</td>
      <td style="text-align:left">&#xC774; &#xC694;&#xC18C;&#xAC00; &#xB9AC;&#xC18C;&#xC2A4;&#xB97C; &#xB2E4;&#xC6B4;&#xB85C;&#xB4DC;&#xD558;&#xB294;
        &#xC6A9;&#xB3C4;&#xB85C; &#xC0AC;&#xC6A9;&#xB428;&#xC744; &#xC758;&#xBBF8;</td>
      <td
      style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">href</td>
      <td style="text-align:left">&#xB9C1;&#xD06C; URL (&#xC0DD;&#xB7B5; &#xAC00;&#xB2A5;)</td>
      <td style="text-align:left">URL</td>
    </tr>
    <tr>
      <td style="text-align:left">rel</td>
      <td style="text-align:left">&#xD604;&#xC7AC; &#xBB38;&#xC11C;&#xC640; &#xB9C1;&#xD06C; URL&#xC758;
        &#xAD00;&#xACC4;</td>
      <td style="text-align:left"><code>license</code>, <code>prev</code>, <code>next</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">target</td>
      <td style="text-align:left">&#xB9C1;&#xD06C; URL&#xC758; &#xD45C;&#xC2DC;(&#xBE0C;&#xB77C;&#xC6B0;&#xC800;
        &#xD0ED;) &#xC704;&#xCE58;</td>
      <td style="text-align:left">
        <p><code>_self(default)</code>,</p>
        <p> <code>_blank</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">&#xB9C1;&#xD06C; URL&#xC758; MIME &#xD0C0;&#xC785;</td>
      <td style="text-align:left"><code>text/html</code>
      </td>
    </tr>
  </tbody>
</table>



#### &lt;abbr&gt;

약어를 지정. \(`title` 속성을 사용하여 전체 글자 또는 설명을 제공\)

#### &lt;b&gt;

문체가 다른 글자의 범위를 설정.

* 특별한 의미를 가지지 않는다.
* 읽기 흐름에 도움을 주는 용도로 사용.
* 다른 태그가 적합하지 않은 경우 마지막 수단으로 사용.
* 기본적으로 글자가 두껍게\(bold\)로 표시된다.

#### &lt;mark&gt;

사용자의 관심을 끌기 위해 하이라이팅 할 때 사용.

* 기본적으로 형광펜을 사용한 것 처럼 글자 배경이 노란색\(yellow\)으로 표신된다.

#### &lt;em&gt;

단순한 의미를 강조.

* 중첩이 가능.
* 중첩될 수록 강조 의미가 강해진다.
* 정보통신보조기기 등에서 구두 강조로 발음된다.
* 기본적으로 이텔릭체\(italic type\)로 표시된다.

#### &lt;strong&gt;

의미의 중요성을 나타내기 위해 사용한다.

* 기본적으로 글자가 두껍게\(bold\)로 표시된다.

#### &lt;i&gt;

&lt;em&gt;, &lt;strong&gt;, &lt;mark&gt;, &lt;cite&gt;, &lt;dfn&gt; 등에서 표현할 수 있는 적합한 의미가 아닌 경우에 사용.

* 기본적으로 이텔릭체\(italic type\)로 표시된다.

#### &lt;dfn&gt;

용어를 정의할 때 사용.

#### &lt;cite&gt;

창작물에 대한 참조를 설정. \(책, 논문, 영화, TV 프로그램, 노래, 게임 등의 제목\)

* 기본적으로 이텔릭체\(italic type\)로 표시된다.

#### &lt;q&gt;

짧은 인용문 설정.

| attribute | description | value |
| :--- | :--- | :--- |
| cite | 인용된 정보의 URL | URL |

#### &lt;u&gt;

밑줄이 있는 글자를 설정.

* 순수하게 꾸미는 용도의 요소로 사용.
* &lt;a&gt;와 헷갈릴 수 있는 위치에서 사용하지 않도록 주의.
* `<span style="text-decoration: underline;">`을 활용할 수 있을 경우에는 사용을 권장하지 않는다.

#### &lt;code&gt;

컴퓨터 코드 범위를 설정.

* 기본적으로 고정폭\(monospace\) 글꼴 계열로 표시된다.

#### &lt;kbd&gt;

텍스트 입력 장치\(키보드\)에서 사용자 입력을 나타내는 텍스트 범위를 설정.

#### &lt;sup&gt;, &lt;sub&gt;

위 첨자 `<sup>`와 아래 첨자`<sub>`를 설정.

#### &lt;time&gt;

날짜나 시간을 나타내기 위한 목적으로 사용.

* IE 지원불가

#### &lt;span&gt;

본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정.

| attribute | description | value |
| :--- | :--- | :--- |
| datetime | 유효한 날짜 문자 | date |

#### &lt;br/&gt;

줄바꿈을 설정.

### 수정

#### &lt;del&gt;

삭제된\(변경된\) 텍스트의 범위를 지정.

| attribute | description | value |
| :--- | :--- | :--- |
| cite | 변경을 설명하는 리소스의 URI | URI |
| datetime | 변경이 일어난 유요한 날짜 문자 | date |

#### &lt;ins&gt;

새로 추가된\(변경된\) 텍스트의 범위를 지정.

| attribute | description | value |
| :--- | :--- | :--- |
| cite | 변경을 설명하는 리소스의 URI | URI |
| datetime | 변경이 일어난 유요한 날짜 문자 | date |

### 멀티미디어

####  &lt;img&gt;

이미지를 삽입.

| attribute | description | value |
| :--- | :--- | :--- |
| src | \(필수\)이미지 URL | URL |
| alt | \(필수\)이미지의 대체텍스트 |  |
|  width | 이미지의 가로 너비 |  |
| height | 이미지의 세로 너비 |  |
| srcset | 브라우저에게 제시할 이미지 URL과 원본 크기의 목록을 정의 |  `w`, `x` |

#### &lt;audio&gt; 

소리 콘텐츠\(mp3\)를 삽입.

* `autoplay`가 지정된 경우, `preload`는 무시된다.

| attribute | description | value |
| :--- | :--- | :--- |
| autoplay | 준비되면 바로 재생 | boolean |
| controls | 제어 메뉴를 표시 | boolean |
| loop | 재생이 끝나면 다시 처음부터 재생 | boolean |
| preload | 페이지가 로드될 때 파일을 로드할지의 지정\(힌트 제공\) | `none` - 로드하지 않는, `metadata(default)`-  메타데이터만 로드,`auto -`전체 파일 로드 |
| src | 콘텐츠 URL | URL |
| muted | 음소거 여부 | boolean |

#### &lt;video&gt;

동영상 콘텐츠\(mp4\)를 삽입.

* `autoplay`가 지정된 경우, `preload`는 무시된다.

| attribute | description | value |
| :--- | :--- | :--- |
| autoplay | 준비되면 바로 재생 | boolean |
| controls | 제어 메뉴를 표시 | boolean |
| loop | 재생이 끝나면 다시 처음부터 재생 | boolean |
| muted | 음소거 여부 | boolean |
| poster | 동영상 썸네일 이미지 URL | URL |
| preload | 페이지가 로드될 때 파일을 로드할지의 지정\(힌트 제공\) | `none` - 로드하지 않는, `metadata(default)`- 메타데이터만 로드,`auto` - 전체 파일 로드 |
| src | 콘텐츠 URL | URL |
| width | 동영상 가로 너비 |  |
| height | 동영상 세로 너비 |  |

#### &lt;figure&gt;, &lt;figcaption&gt;

`<figure>`는 이미지, 삽화, 도표 등의 영역을 설정.

`<figcaption>`는 `<figure>`에 포함되어 이미지, 삽화 등의 설명을 표시.

### 내장 콘텐츠

#### &lt;iframe&gt;

다른 HTML 페이지를 현재 페이지에 삽입. \(중첩된 브라우저 컨텍스트\(프레임\)을 표시\)

<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">&#xD504;&#xB808;&#xC784;&#xC758; &#xC774;&#xB984;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">src</td>
      <td style="text-align:left">&#xD3EC;&#xD568;&#xD560; &#xBB38;&#xC11C;&#xC758; URL</td>
      <td style="text-align:left">URL</td>
    </tr>
    <tr>
      <td style="text-align:left">width</td>
      <td style="text-align:left">&#xD504;&#xB808;&#xC784;&#xC758; &#xAC00;&#xB85C; &#xB108;&#xBE44;</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">height</td>
      <td style="text-align:left">&#xD504;&#xB808;&#xC784;&#xC758; &#xC138;&#xB85C; &#xB108;&#xBE44;</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">allowfullscreen</td>
      <td style="text-align:left">&#xC804;&#xCCB4; &#xD654;&#xBA74; &#xBAA8;&#xB4DC; &#xC0AC;&#xC6A9; &#xC5EC;&#xBD80;</td>
      <td
      style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">frameborder</td>
      <td style="text-align:left">&#xD504;&#xB808;&#xC784; &#xD14C;&#xB450;&#xB9AC; &#xC0AC;&#xC6A9; &#xC5EC;&#xBD80;</td>
      <td
      style="text-align:left"><code>0</code>, <code>1(default)</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">sandbox</td>
      <td style="text-align:left">&#xBCF4;&#xC548;&#xC744; &#xC704;&#xD55C; &#xC77D;&#xAE30; &#xC804;&#xC6A9;&#xC73C;&#xB85C;
        &#xC0BD;&#xC785;</td>
      <td style="text-align:left">
        <p>boolean or
          <br /><code>allow-form</code>- &#xC591;&#xC2DD; &#xC81C;&#xCD9C; &#xAC00;&#xB2A5;,
          <br
          /><code>allow-scripts</code>- &#xC2A4;&#xD06C;&#xB9BD;&#xD2B8; &#xC2E4;&#xD589;
          &#xAC00;&#xB2A5; ,
          <br /><code>allow-same-origin</code>- &#xAC19;&#xC740; &#xCD9C;&#xCC98;(&#xB3C4;&#xBA54;&#xC778;)&#xC758;
          &#xB9AC;&#xC18C;&#xC2A4;</p>
        <p>&#xC0AC;&#xC6A9; &#xAC00;&#xB2A5;</p>
      </td>
    </tr>
  </tbody>
</table>

#### &lt;canvas&gt;

 [Canvas API](https://developer.mozilla.org/ko/docs/Web/HTML/Canvas)이나 [WebGL API](https://developer.mozilla.org/ko/docs/Web/API/WebGL_API)를 사용하여 그래픽이나 애니메이션을 랜더링.

| attribute | description |
| :--- | :--- |
| widhth | 캔버스의 가로 너비 |
| height | 캔버스의 세로 너비 |

### 스크립트

#### &lt;script&gt;

스크립트 코드를 문서에 포함하거나 참조.\(외부 스크립트\)  

<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">async</td>
      <td style="text-align:left">
        <p>&#xC2A4;&#xD06C;&#xB9BD;&#xD2B8;&#xC758; &#xBE44;&#xB3D9;&#xAE30;&#xC801;(Asynchronously)
          &#xC2E4;&#xD589; &#xC5EC;&#xBD80;,</p>
        <p><code>src</code> &#xC18D;&#xC131; &#xD544;&#xC218;</p>
      </td>
      <td style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">defer</td>
      <td style="text-align:left">
        <p>&#xBB38;&#xC11C; &#xD30C;&#xC2F1;(&#xAD6C;&#xBB38; &#xBD84;&#xC11D;)&#xD6C4;
          &#xC791;&#xB3D9; &#xC5EC;&#xBD80; ,</p>
        <p><code>src</code> &#xC18D;&#xC131; &#xD544;&#xC218;</p>
      </td>
      <td style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">src</td>
      <td style="text-align:left">
        <p>&#xCC38;&#xC870;&#xD560; &#xC678;&#xBD80; &#xC2A4;&#xD06C;&#xB9BD;&#xD2B8;
          URL ,</p>
        <p>&#xD3EC;&#xD568;&#xB41C; &#xC2A4;&#xD06C;&#xB9BD;&#xD2B8; &#xCF54;&#xB4DC;&#xB294;
          &#xBB34;&#xC2DC;&#xB41C;&#xB2E4;.</p>
      </td>
      <td style="text-align:left">URL</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">MIME &#xD0C0;&#xC785;</td>
      <td style="text-align:left"> <code>text/javascript(default)</code>
      </td>
    </tr>
  </tbody>
</table>

#### &lt;noscript&gt;

스크립트를 지원하지 않는 경우에 삽입할 HTML을 정의.

### 표 콘텐츠

#### &lt;table&gt;, &lt;tr&gt;, &lt;th&gt;, &lt;td&gt;

  데이터 표 `<table>`의 행 줄 / `<tr>`과 열 칸, 셀\(Cell\) / `<th>`, `<td>`을 생성.

#### &lt;th&gt;

'머리글 칸'을 지정.

| attribute | description | value |
| :--- | :--- | :--- |
| abbr | 열에 대한 간단한 설명 |  |
| headers | 관련된 하나 이상의 다른 머리글 칸 `id` 속성 값 |  |
| colspan | 확장하려는\(병합\) 열의 수 | `1(default)` |
| rowspan | 확장하려는\(병합\) 행의 수 | `1(default)` |
| scope | 자신이 누구의 ‘머리글 칸’인지 명시 | `col` - 자신의 열 `colgroup` - 모든 열 `row` - 자신의 행 `rowgroup`- 모든 행 `auto(default)` |

#### &lt;td&gt;

'일반 칸'을 지정.

| attribute | description | value |
| :--- | :--- | :--- |
| headers | 관련된 하나 이상의 다른 머리글 칸 `id` 속성 값 |  |
| colspan | 확장하려는\(병합\) 열의 수 | `1(default)` |
| rowspan | 확장하려는\(병합\) 행의 수 | `1(default)` |

#### &lt;caption&gt;

표의 제목을 설정.

* 열리는 &lt;table&gt; 요소 바로 다음에 작성해야 한다.
* &lt; table&gt; 요소 당 하나의 &lt;caption&gt;만 사용 가능.

#### &lt;colgroup&gt;, &lt;col/&gt;

표의 열들을 공통적으로 정의하는 컬럼 `<col>` 과 그의 집합 `<colgroup>`

| attribute | description | value |
| :--- | :--- | :--- |
| span | 연속되는 열 수 | `1(default)` |

#### &lt;thead&gt;, &lt;tbody&gt;, &lt;tfoot&gt;

 표의 머리글`<thead>`, 본문`<tbody>`, 바닥글`<tfoot>`을 지정.

* 기본적으로 테이블의 레이아웃에 영향을 주지 않는다.

### 양식

#### &lt;form&gt;

웹 서버에 정보를 제출하기 위한 양식 범위를 정의.

* `<form>`이 다른 `<form>`을 자식 요소로 포함할 수 없다.



| attribute | description | value |
| :--- | :--- | :--- |
| action | 전송한 정보를 처리할 웹페이지의 URL | URL |
| autocomplete | 사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부 | `on(default)`, `off` |
| method | 서버로 전송할 HTTP 방식 | `GET(default)`, `POST` |
| name | 고유한 양식의 이름 |  |
| novalidate | 서버로 전송시 양식 데이터의 유효성을 검사하지 않도록 지정 |  |
| target | 서버로 전송 후 응답받을 방식을 지정 | `_self(default)`,`_blank` |

#### &lt;input/&gt;

사용자에게 입력 받을 데이터 양식

#### &lt;input type="values"&gt;

`<input>` 요소의 `type`속성에 입력할 수 있는 값의 목록. 

#### &lt;label&gt;

 라벨 가능 요소\([labelable](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#Form_labelable)\)의 제목\(caption\).

* `for` 속성으로 라벨 가능 요소를 참조하거나 콘텐츠로 포함.
* 라벨 가능 요소
  *  `<button>`, `<input>`, `<progress>`, `<select>`, `<textarea>`

| attribute | description |
| :--- | :--- |
| for | 참조할 라벨 가능 요소의 `id` 속성 값 |

#### &lt;button&gt;

선택 가능한 버튼을 지정.

<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">autofocus</td>
      <td style="text-align:left">
        <p>&#xD398;&#xC774;&#xC9C0;&#xAC00; &#xB85C;&#xB4DC;&#xB420; &#xB54C; &#xC790;&#xB3D9;&#xC73C;&#xB85C;
          &#xD3EC;&#xCEE4;&#xC2A4;,</p>
        <p>&#xBB38;&#xC11C; &#xB0B4; &#xACE0;&#xC720;&#xD574;&#xC57C; &#xD55C;&#xB2E4;.</p>
      </td>
      <td style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">disabled</td>
      <td style="text-align:left">&#xBC84;&#xD2BC;&#xC744; &#xBE44;&#xD65C;&#xC131;&#xD654;</td>
      <td style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">form</td>
      <td style="text-align:left">
        <p><code>&lt;form&gt;</code>&#xC758; <code>id</code> &#xC18D;&#xC131; &#xAC12;,</p>
        <p>&#xD574;&#xB2F9; &lt;form&gt; &#xD6C4;&#xC190;&#xC774; &#xC544;&#xB2D0;
          &#xACBD;&#xC6B0;</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">&#xD3FC; &#xB370;&#xC774;&#xD130;&#xC640; &#xD568;&#xAED8; &#xC804;&#xC1A1;&#xB418;&#xB294;
        &#xBC84;&#xD2BC;&#xC758; &#xC774;&#xB984;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">&#xBC84;&#xD2BC;&#xC758; &#xD0C0;&#xC785;</td>
      <td style="text-align:left"><code>button</code>, <code>reset</code>, <code>submit</code>
      </td>
    </tr>
  </tbody>
</table>

#### &lt;textare&gt;

여러 줄의 일반 텍스트 양식.



<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">autocomplete</td>
      <td style="text-align:left">
        <p>&#xC0AC;&#xC6A9;&#xC790;&#xAC00; &#xC774;&#xC804;&#xC5D0; &#xC785;&#xB825;&#xD55C;
          &#xAC12;&#xC73C;&#xB85C; &#xC790;&#xB3D9; &#xC644;&#xC131; &#xAE30;&#xB2A5;&#xC744;
          &#xC0AC;&#xC6A9;&#xD560; &#xAC83;&#xC778;&#xC9C0; &#xC5EC;&#xBD80;,</p>
        <p>&#xBB38;&#xC11C; &#xB0B4; &#xACE0;&#xC720;&#xD574;&#xC57C; &#xD55C;&#xB2E4;.</p>
      </td>
      <td style="text-align:left"><code>on(default)</code>, <code>off</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">autofocus</td>
      <td style="text-align:left">&#xD398;&#xC774;&#xC9C0;&#xAC00; &#xB85C;&#xB4DC;&#xB420; &#xB54C; &#xC790;&#xB3D9;&#xC73C;&#xB85C;
        &#xD3EC;&#xCEE4;&#xC2A4;</td>
      <td style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">disabled</td>
      <td style="text-align:left">&#xC591;&#xC2DD;&#xC744; &#xBE44;&#xD65C;&#xC131;&#xD654;</td>
      <td style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">form</td>
      <td style="text-align:left">
        <p><code>&lt;form&gt;</code>&#xC758; <code>id</code> &#xC18D;&#xC131; &#xAC12;,</p>
        <p>&#xD574;&#xB2F9; &lt;form&gt; &#xD6C4;&#xC190;&#xC774; &#xC544;&#xB2D0;
          &#xACBD;&#xC6B0;</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">maxlength</td>
      <td style="text-align:left">&#xC785;&#xB825; &#xAC00;&#xB2A5;&#xD55C; &#xCD5C;&#xB300; &#xBB38;&#xC790;
        &#xC218;</td>
      <td style="text-align:left">number</td>
    </tr>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">&#xC591;&#xC2DD;&#xC758; &#xC774;&#xB984;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">placeholder</td>
      <td style="text-align:left">&#xC0AC;&#xC6A9;&#xC790;&#xAC00; &#xC785;&#xB825;&#xD560; &#xAC12;&#xC758;
        &#xD78C;&#xD2B8;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">readonly</td>
      <td style="text-align:left">&#xC218;&#xC815; &#xBD88;&#xAC00;&#xD55C; &#xC77D;&#xAE30; &#xC804;&#xC6A9;</td>
      <td
      style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">rows</td>
      <td style="text-align:left">&#xC591;&#xC2DD;&#xC758; &#xC904; &#xC218;</td>
      <td style="text-align:left"><code>2(default),</code>number</td>
    </tr>
  </tbody>
</table>

#### &lt;fieldset&gt;, &lt;legend&gt;

같은 목적의 양식을 그룹화 `<fieldset>` 하여 제목`<legend>`을 지정.

| attribute | description | value |
| :--- | :--- | :--- |
| disabled | 그룹 내 모든 양식 요소를 비활성화 | boolean |
| form | 그룹이 속할 하나 이상의 `<form>`의 `id` 속성 값 |  |
| name | 그룹의 이름 |  |

#### &lt;fieldset&gt;

같은 목적의 양식을 그룹화.

#### &lt;select&gt;, &lt;datalist&gt;, &lt;optgroup&gt;, &lt;option&gt;

 옵션`<option>`, `<optgroup>`의 선택 메뉴`<select>` 또는 자동완성`<datalist>`을 제공.

#### &lt;select&gt;

옵션을 선택하는 메뉴.

| attribute | description |  |
| :--- | :--- | :--- |
| autocomplete | 사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부 | `on(default)`, `off` |
| disabled | 선택 메뉴를 비활성화 | boolean |
| form | 선택 메뉴가 속할 하나 이상의 `<form>`의 `id` 속성 값 |  |
| multiple | 다중 선택 여부 | boolean |
| name | 선택 메뉴의 이름 |  |
| size | 한 번에 볼 수 있는 행의 개수 | 0\(1과 같다\), number |

#### &lt;datalist&gt;

`<input>`에 미리 정의된 옵션을 지정하여 자동완성\(autocomplete\) 기능을 제공하는 데 사용.

* `<input>`의 `list` 속성 바인딩.
* `<option>`을 포함하여 정의된 옵션을 지정.

#### &lt;optgroup&gt;

`<option>`을 그룹화.

| attribute | description | value |
| :--- | :--- | :--- |
| label | \(필수\)옵션 그룹의 이름 |  |
| disabled | 옵션 그룹을 비활성화 | boolean |

#### &lt;option&gt;

선택 메뉴`<select>` 또는 자동완성`<datalist>`에서 사용될 옵션.

* 선택적 빈\(empty\) 요로 사용 가능.

<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">disabled</td>
      <td style="text-align:left">&#xC635;&#xC158;&#xC744; &#xBE44;&#xD65C;&#xC131;&#xD654;</td>
      <td style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">label</td>
      <td style="text-align:left">
        <p>&#xD45C;&#xC2DC;&#xB420; &#xC635;&#xC158;&#xC758; &#xC81C;&#xBAA9;,</p>
        <p>&#xC0DD;&#xB7B5;&#xB418;&#xBA74; &#xD3EC;&#xD568;&#xB41C; &#xD14D;&#xC2A4;&#xD2B8;&#xB97C;
          &#xD45C;&#xC2DC;</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">selected</td>
      <td style="text-align:left">&#xC635;&#xC158;&#xC774; &#xC120;&#xD0DD;&#xB418;&#xC5C8;&#xC74C;&#xC744;
        &#xD45C;&#xC2DC;</td>
      <td style="text-align:left">boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">value</td>
      <td style="text-align:left">
        <p>&#xC591;&#xC2DD;&#xC73C;&#xB85C; &#xC81C;&#xCD9C;&#xB420; &#xAC12;,</p>
        <p>&#xC0DD;&#xB7B5;&#xB418;&#xBA74; &#xD3EC;&#xD568;&#xB41C; &#xD14D;&#xC2A4;&#xD2B8;&#xAC12;&#xC73C;&#xB85C;
          &#xC0AC;&#xC6A9;</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

#### &lt;progress&gt;

작업의 완료 진행률을 표시.

<table>
  <thead>
    <tr>
      <th style="text-align:left">attribute</th>
      <th style="text-align:left">description</th>
      <th style="text-align:left">value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">max</td>
      <td style="text-align:left">&#xC791;&#xC5C5;&#xC758; &#xCD1D;&#xB7C9;</td>
      <td style="text-align:left">number</td>
    </tr>
    <tr>
      <td style="text-align:left">value</td>
      <td style="text-align:left">
        <p>&#xC791;&#xC5C5;&#xC758; &#xC9C4;&#xD589;&#xB7C9;,</p>
        <p><code>max</code> &#xC18D;&#xC131;&#xC744; &#xC0DD;&#xB7B5;&#xD560; &#xACBD;&#xC6B0; <code>0</code>~<code>1</code> &#xC0AC;&#xC774;&#xC758;
          &#xC22B;&#xC790;&#xC5EC;&#xC57C; &#xD55C;&#xB2E4;.</p>
      </td>
      <td style="text-align:left">number</td>
    </tr>
  </tbody>
</table>

### 전역 속성 \(global attributes\)

모든 HTML 요소에서 공통적으로 사용 가능한 속성.

#### class

공백으로 구분된 요소의 별칭을 지정, CSS 또는 JavaScript의 요소 선택기를 통해서 요소를 선택하거나 접근.

#### ID

문서에서 고유한 식별자를 정의, CSS 또는 JavaScript의 요소 선택기를 통해서 요소를 선택하거나 접근.

#### style

요소에 적용할 CSS를 선언.

#### title

요소의 정보\(설명\)을 지정.

#### lang

 요소의 언어\([ISO 639-1](https://ko.wikipedia.org/wiki/ISO_639-1_%EC%BD%94%EB%93%9C_%EB%AA%A9%EB%A1%9D)\)를 지정.

#### data-\*

사용자 정의 데이터 속성을 지정. HTML에 JavaScript에서 이용할 수 있는 데이터\(정보\)를 저장하는 용도로 사용.

#### draggable

 요소가 [Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API)를 사용 가능한지 여부를 지정.

#### hidden

요소를 숨김.

#### tabindex

`tab`키를 이용해 요소를 순차적으로 포커스 탐색할 순서를 지정.

* [대화형 콘텐츠\(Interactive Content\)](https://developer.mozilla.org/ko/docs/Web/Guide/HTML/%EC%BB%A8%ED%85%90%ED%8A%B8_%EC%B9%B4%ED%85%8C%EA%B3%A0%EB%A6%AC#%EB%8C%80%ED%99%94%ED%98%95_%EC%BD%98%ED%85%90%EC%B8%A0)는 기본적으로 코드 순서대로 탭 순서가 지정된다.
* 비대화형 콘텐츠에 `tabindex="0"`을 지정하여 대화형 콘텐츠와 같이 탭 순서를 사용.
* `tabindex="-1"`을 통해 포커스는 가능하지만 탭 순서에서 제외 가능.
* `tabindex="1"` 이상의 양수 값은 논리적 흐름을 방해하기 때문에 사용을 추천하지 않는다.

### 생략한 요소

#### &lt;template&gt;

렌더링되지 않는 콘텐츠를 보유.

* JavaScript를 사용해 렌더링.
* 반복적으로 사용하는 콘텐츠에 활용.
* IE 지원 불가

#### &lt;map&gt;, &lt;area&gt;

 클라이언트 측 이미지 맵`<map>`과 클릭 가능한 영역`<area>`을 정의. \(`<img />`와 연결해 사용\)

### 생략한 속성

<table>
  <thead>
    <tr>
      <th style="text-align:center">element</th>
      <th style="text-align:center">attribute</th>
      <th style="text-align:center">description</th>
      <th style="text-align:center">value</th>
      <th style="text-align:center">point</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center"><code>&lt;link /&gt;</code>,
        <br /><code>&lt;a&gt;</code>
      </td>
      <td style="text-align:center">hreflang</td>
      <td style="text-align:center">
        <p>&#xD604;&#xC7AC; &#xD398;&#xC774;&#xC9C0;&#xC758; &#xB300;&#xCCB4; &#xC5B8;&#xC5B4;</p>
        <p>(<a href="https://ko.wikipedia.org/wiki/ISO_639-1_%EC%BD%94%EB%93%9C_%EB%AA%A9%EB%A1%9D">ISO 639-1</a>)</p>
      </td>
      <td style="text-align:center"><code>ko</code>, <code>en</code>
      </td>
      <td style="text-align:center"><a href="https://moz.com/learn/seo/hreflang-tag">&#xB2E4;&#xB978; &#xC5B8;&#xC5B4; &#xB610;&#xB294; &#xC9C0;&#xC5ED;&#xBCC4; &#xC5EC;&#xB7EC; &#xBC84;&#xC804;&#xC758; &#xD398;&#xC774;&#xC9C0;&#xAC00; &#xC788;&#xB294; &#xACBD;&#xC6B0;</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;ol&gt;</code>
      </td>
      <td style="text-align:center">reversed</td>
      <td style="text-align:center">&#xD56D;&#xBAA9;&#xC744; &#xC5ED;&#xC21C;&#xC73C;&#xB85C; &#xC124;&#xC815;</td>
      <td
      style="text-align:center"></td>
        <td style="text-align:center">IE &#xC9C0;&#xC6D0; &#xBD88;&#xAC00;</td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;link&gt;</code>,
        <br /><code>&lt;img /&gt;</code>,
        <br /><code>&lt;video&gt;</code>,
        <br /><code>&lt;script&gt;</code>
      </td>
      <td style="text-align:center">crossorigin</td>
      <td style="text-align:center">&#xAC00;&#xC838; &#xC624;&#xAE30;&#xAC00; <a href="https://developer.mozilla.org/ko/docs/Web/HTTP/Access_control_CORS">CORS</a>&#xB97C;
        &#xC0AC;&#xC6A9;&#xD558;&#xC5EC; &#xC218;&#xD589;&#xB418;&#xC5B4;&#xC57C;&#xD558;&#xB294;&#xC9C0;
        &#xC5EC;&#xBD80;</td>
      <td style="text-align:center"><code>anonymous</code>,
        <br /><code>use-credentials</code>
      </td>
      <td style="text-align:center"></td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;img /&gt;</code>
      </td>
      <td style="text-align:center">ismap</td>
      <td style="text-align:center">&#xC11C;&#xBC84; &#xCE21; &#xC774;&#xBBF8;&#xC9C0; &#xB9F5;&#xC73C;&#xB85C;
        &#xC9C0;&#xC815;&#xD574; &#xD074;&#xB9AD;&#xD558;&#xC5EC; &#xC88C;&#xD45C;&#xB97C;
        <a
        href="https://en.wikipedia.org/wiki/Query_string">&#xCFFC;&#xB9AC;&#xC2A4;&#xD2B8;&#xB9C1;</a>&#xC73C;&#xB85C; &#xC11C;&#xBC84;&#xC5D0;
          &#xC804;&#xC1A1;&#xD560;&#xC9C0; &#xC5EC;&#xBD80;</td>
      <td style="text-align:center">&#xBD88;&#xB9B0;(Boolean)</td>
      <td style="text-align:center"><code>&lt;img /&gt;</code>&#xAC00; &#xC720;&#xD6A8;&#xD55C; <code>href</code> &#xC18D;&#xC131;&#xC744;
        &#xAC00;&#xC9C4; <code>&lt;a&gt;</code>&#xC758; &#xD558;&#xC704; &#xC694;&#xC18C;&#xC778;
        &#xACBD;&#xC6B0;&#xC5D0;&#xB9CC; &#xD5C8;&#xC6A9;</td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;img /&gt;</code>
      </td>
      <td style="text-align:center">usemap</td>
      <td style="text-align:center">&#xD074;&#xB77C;&#xC774;&#xC5B8;&#xD2B8; &#xCE21; &#xC774;&#xBBF8;&#xC9C0;
        &#xB9F5;&#xC73C;&#xB85C; &#xC9C0;&#xC815;</td>
      <td style="text-align:center"><code>&lt;map&gt;</code>&#xC758; <code>#</code> + <code>name</code> &#xC18D;&#xC131;
        &#xAC12;</td>
      <td style="text-align:center">
        <p><code>&lt;a&gt;</code>, <code>&lt;button&gt;</code>&#xC758; &#xD558;&#xC704;
          &#xC694;&#xC18C;&#xC778; &#xACBD;&#xC6B0;</p>
        <p>&#xC0AC;&#xC6A9; &#xBD88;&#xAC00;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;form&gt;</code>
      </td>
      <td style="text-align:center">accept-charset</td>
      <td style="text-align:center">&#xC11C;&#xBC84;&#xAC00; &#xBC1B;&#xC744; <a href="https://www.iana.org/assignments/character-sets/character-sets.xhtml">&#xBB38;&#xC790;&#xC778;&#xCF54;&#xB529; &#xBC29;&#xC2DD;</a>
      </td>
      <td style="text-align:center"><code>UTF-8</code>, <code>EUC-KR</code>
      </td>
      <td style="text-align:center"><code>UNKNOWN</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;form&gt;</code>
      </td>
      <td style="text-align:center">enctype</td>
      <td style="text-align:center"><code>method</code>&#xC18D;&#xC131;&#xC774; <code>POST</code>&#xC77C; &#xACBD;&#xC6B0;,
        &#xC11C;&#xBC84;&#xB85C; &#xC804;&#xC1A1;&#xD558;&#xB294; &#xCF58;&#xD150;&#xCE20;&#xC758;
        <a
        href="https://developer.mozilla.org/ko/docs/Web/HTTP/Basics_of_HTTP/MIME_types">MIME &#xD0C0;&#xC785;</a>
      </td>
      <td style="text-align:center"></td>
      <td style="text-align:center"></td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>
      </td>
      <td style="text-align:center">accept</td>
      <td style="text-align:center">&#xC11C;&#xBC84;&#xAC00; &#xBC1B;&#xC744; &#xD30C;&#xC77C; &#xC885;&#xB958;</td>
      <td
      style="text-align:center">&#xD30C;&#xC77C; &#xD655;&#xC7A5;&#xC790;(<code>.jpg</code>, <code>.png</code>..),
        <br
        /><a href="https://developer.mozilla.org/ko/docs/Web/HTTP/Basics_of_HTTP/MIME_types">MIME &#xD0C0;&#xC785;</a>,
        <br
        /><code>audio/*</code>,
        <br /><code>video/*</code>,
        <br /><code>image/*</code>
        </td>
        <td style="text-align:center"><code>type=&quot;file&quot;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>
      </td>
      <td style="text-align:center">width</td>
      <td style="text-align:center">&#xC774;&#xBBF8;&#xC9C0;&#xC758; &#xAC00;&#xB85C; &#xB108;&#xBE44;</td>
      <td
      style="text-align:center">number</td>
        <td style="text-align:center"><code>type=&quot;image&quot;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>
      </td>
      <td style="text-align:center">height</td>
      <td style="text-align:center">&#xC774;&#xBBF8;&#xC9C0;&#xC758; &#xAC00;&#xB85C; &#xB108;&#xBE44;</td>
      <td
      style="text-align:center">number</td>
        <td style="text-align:center"><code>type=&quot;image&quot;</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>,
        <br /><code>&lt;button&gt;</code>
      </td>
      <td style="text-align:center">formaction</td>
      <td style="text-align:center">&#xC591;&#xC2DD;&#xC744; &#xC81C;&#xCD9C;&#xD560; &#xB54C; &#xC591;&#xC2DD;
        &#xB370;&#xC774;&#xB97C; &#xBCF4;&#xB0BC; &#xC704;&#xCE58;</td>
      <td style="text-align:center">URL</td>
      <td style="text-align:center">
        <p><code>type=&quot;submit&quot;</code>,
          <br /><code>type=&quot;image&quot;</code>,
          <br /><code>form</code>&#xC758; &#xC18D;&#xC131;&#xBCF4;&#xB2E4;</p>
        <p>&#xC6B0;&#xC120;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>,
        <br /><code>&lt;button&gt;</code>
      </td>
      <td style="text-align:center">formenctype</td>
      <td style="text-align:center">&#xC591;&#xC2DD; &#xB370;&#xC774;&#xD130;&#xB97C; &#xC11C;&#xBC84;&#xB85C;
        &#xBCF4;&#xB0B4;&#xAE30; &#xC804;&#xC5D0; &#xC778;&#xCF54;&#xB529; &#xD560;
        &#xBC29;&#xBC95;&#xC744; &#xC9C0;&#xC815;</td>
      <td style="text-align:center">-</td>
      <td style="text-align:center">
        <p><code>type=&quot;submit&quot;</code>,
          <br /><code>type=&quot;image&quot;</code>,
          <br /><code>form</code>&#xC758; &#xC18D;&#xC131;&#xBCF4;&#xB2E4;</p>
        <p>&#xC6B0;&#xC120;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>,
        <br /><code>&lt;button&gt;</code>
      </td>
      <td style="text-align:center">formmethod</td>
      <td style="text-align:center">&#xC591;&#xC2DD; &#xB370;&#xC774;&#xD130;&#xB97C; &#xBCF4;&#xB0B4;&#xB294;
        &#xBC29;&#xBC95;</td>
      <td style="text-align:center"><code>GET</code>, <code>POST</code>
      </td>
      <td style="text-align:center">
        <p><code>type=&quot;submit&quot;</code>,
          <br /><code>type=&quot;image&quot;</code>,
          <br /><code>form</code>&#xC758; &#xC18D;&#xC131;&#xBCF4;&#xB2E4;</p>
        <p>&#xC6B0;&#xC120;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>,
        <br /><code>&lt;button&gt;</code>
      </td>
      <td style="text-align:center">formnovalidate</td>
      <td style="text-align:center">&#xC591;&#xC2DD; &#xB370;&#xC774;&#xD130;&#xC758; &#xC720;&#xD6A8;&#xC131;&#xC744;
        &#xAC80;&#xC0AC;&#xD558;&#xC9C0; &#xC54A;&#xB3C4;&#xB85D; &#xC9C0;&#xC815;</td>
      <td
      style="text-align:center">boolean</td>
        <td style="text-align:center">
          <p><code>type=&quot;submit&quot;</code>,
            <br /><code>type=&quot;image&quot;</code>,
            <br /><code>form</code>&#xC758; &#xC18D;&#xC131;&#xBCF4;&#xB2E4;</p>
          <p>&#xC6B0;&#xC120;</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>,
        <br /><code>&lt;button&gt;</code>
      </td>
      <td style="text-align:center">formtarget</td>
      <td style="text-align:center"></td>
      <td style="text-align:center"><code>_self</code>, <code>_blank</code>
      </td>
      <td style="text-align:center">
        <p><code>type=&quot;submit&quot;</code>,
          <br /><code>type=&quot;image&quot;</code>,
          <br /><code>form</code>&#xC758; &#xC18D;&#xC131;&#xBCF4;&#xB2E4;</p>
        <p>&#xC6B0;&#xC120;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;,</code>
        <br /><code>&lt;textarea&gt;</code>
      </td>
      <td style="text-align:center">minlength</td>
      <td style="text-align:center">&#xC785;&#xB825; &#xAC00;&#xB2A5;&#xD55C; &#xCD5C;&#xC18C; &#xBB38;&#xC790;
        &#xC218;</td>
      <td style="text-align:center">number</td>
      <td style="text-align:center"><code>type=&quot;text&quot;</code>,
        <br /><code>type=&quot;email&quot;</code>,
        <br /><code>type=&quot;password&quot;</code>,
        <br /><code>type=&quot;tel&quot;</code>,
        <br /><code>type=&quot;url&quot;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>
      </td>
      <td style="text-align:center">pattern</td>
      <td style="text-align:center">
        <p>&#xC591;&#xC2DD;&#xC758; &#xAC12;&#xC744; &#xAC80;&#xC0AC;&#xD558;&#xB294;
          &#xC815;&#xADDC;</p>
        <p>&#xD45C;&#xD604;&#xC2DD;</p>
      </td>
      <td style="text-align:center">RegExp</td>
      <td style="text-align:center"><code>type=&quot;text&quot;</code>,
        <br /><code>type=&quot;search&quot;</code>,
        <br /><code>type=&quot;tel&quot;</code>,
        <br /><code>type=&quot;url&quot;</code>,
        <br /><code>type=&quot;email&quot;</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>,
        <br /><code>&lt;textarea&gt;</code>,
        <br /><code>&lt;select&gt;</code>
      </td>
      <td style="text-align:center">required</td>
      <td style="text-align:center">&#xD544;&#xC218; &#xC5EC;&#xBD80;</td>
      <td style="text-align:center">boolean</td>
      <td style="text-align:center"></td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>
      </td>
      <td style="text-align:center">size</td>
      <td style="text-align:center">&#xC591;&#xC2DD;&#xC758; &#xAC00;&#xB85C; &#xB108;&#xBE44;</td>
      <td style="text-align:center">number, <code>20</code>
      </td>
      <td style="text-align:center">
        <p>&#xD3C9;&#xADE0; &#xBB38;&#xC790; &#xB108;&#xBE44;&#xB97C;</p>
        <p>&#xAE30;&#xC900;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;input /&gt;</code>,
        <br /><code>&lt;textarea&gt;</code>
      </td>
      <td style="text-align:center">spellcheck</td>
      <td style="text-align:center">&#xB9DE;&#xCDA4;&#xBC95; &#xBC0F; &#xBB38;&#xBC95; &#xAC80;&#xC0AC;&#xC758;
        &#xD544;&#xC694; &#xC5EC;&#xBD80;</td>
      <td style="text-align:center">boolean</td>
      <td style="text-align:center"></td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;button&gt;</code>
      </td>
      <td style="text-align:center">value</td>
      <td style="text-align:center">
        <p>&#xD3FC; &#xB370;&#xC774;&#xD130;&#xC640; &#xD568;&#xAED8; &#xC804;&#xC1A1;&#xB418;&#xB294;</p>
        <p>&#xBC84;&#xD2BC;&#xC758; &#xCD08;&#xAE30;&#xAC12;</p>
      </td>
      <td style="text-align:center"></td>
      <td style="text-align:center">IE &#xC9C0;&#xC6D0; &#xBD88;&#xAC00;</td>
    </tr>
    <tr>
      <td style="text-align:center"><code>&lt;textarea&gt;</code>
      </td>
      <td style="text-align:center">cols</td>
      <td style="text-align:center">&#xC591;&#xC2DD;&#xC758; &#xAC00;&#xB85C; &#xB108;&#xBE44;</td>
      <td style="text-align:center">number, <code>20</code>
      </td>
      <td style="text-align:center">
        <p>&#xD3C9;&#xADE0; &#xBB38;&#xC790; &#xB108;&#xBE44;&#xB97C;</p>
        <p>&#xAE30;&#xC900;</p>
      </td>
    </tr>
  </tbody>
</table>

### 생략한 전역 속성

#### accesskey

요소의 키보드 단축키 힌트를 제공.

* 다음의 이유 등으로 일반 목적의 웹사이트에서는 사용을 권장하지 않는다.
  * 브라우저 키보드 단축키 혹은 보조기기의 기능과 충돌
  * 특정 키보드의 존재하지 않는 키 사용
  * 숫자 같은 논리적인 관계가 없는 키 지정
  * `accesskey`의 존재를 모르는 사용자의 실수

#### contenteditable

요소의 사용자 편집 여부를 지정.

### Reference <a id="reference"></a>

#### HTML elements reference  [→\(MDN\)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

