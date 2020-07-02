# 📄 Flex

### 1. Flex 정의

Flex는 요소의 크기가 불분명 하거나 동적인 경우에, 각 요소를 정렬할 수 효율적인 방법을 제공한다.

Flex는 `container, item` 두 가지 개념으로 나뉜다. 

### 2. container 정렬

container는 item를 감싸는 부모 역할

`display, flex-direction, justify-content`등의 속성을 사용할 수 있다.

#### 2-1. display

block 또는 lnline이 아닌  `display: flex`, `display: inline-flex`설정한다.

| Title | Content |
| :--- | :--- |
| flex | Block 요소 처럼 수직 정렬 |
| inline-flex | lnline\(Inline block\) 요소 처럼 수평 정렬 |

#### 2-2. flex-flow

Item의 주 축\(main-axis\)을 설정, item의 여러 줄 묶음\(줄 바꿈\)도 설정한다.

#### 2-3. flex-direction 

item의 주 축\(main-axis\)을 설정한다.

| Title | Content |
| :--- | :--- |
| row ****\(**defalut**\) | item를 수평축, 왼쪽에서 오른쪽으로 정렬 |
| row-reverse | item `row`의 반대축으로 정렬 |
|  column | item 수직축, 위에서 아래로 정렬 |
| column-reverse | item `column`의 반대축으로 정렬 |

#### 2-4. flex-wrap

item 여러 줄 묶음, 줄 바꿈 설정한다.

| Title | Content |
| :--- | :--- |
| nowrap \(**defalut**\) | 모든 item 여러 줄 묶지 않고, 한 줄에 표시 |
| wrap | item 여러 줄 묶음 |
| wrap-reverse | item를 `wrap`의 역 방향으로 여러 줄 묶음  |

#### 2-5. justify-content

주 축\(main-axis\) 정렬 방법 설정한다.

| Title | Content |
| :--- | :--- |
| flex-start \(**defalut**\) | item를 시작점으로 정렬 |
| flex-end | item를 끝점으로 정렬 |
| center | item를 가운데 정렬 |
| space-between | item를 시작점 끝점에 정렬하고, 나머지 item은 사이에 고르게 정렬 |
| space-around | item를 균등한 여백을 포함하여 정렬 |

#### 2-6. align-content 

align-content를 사용하기 위해서 `flex-wrap : wrap;` 이어야 한다.

교차죽\(cross-axis\)의 정렬 방법, item 여러 줄 \(두 줄\) 이상 이고 여백이 있을 경우 사용 가능하다.

| Title | Content |
| :--- | :--- |
| stretch \(**defalut**\) | container의 교차축을 채우기 위해 item 를 늘림 |
| flex-start | item를 시작점으로 정렬 |
| flex-end | item를 끝점으로 정렬 |
| center | item를 가운데 정렬 |
| space-between | item를 시작점 끝점에 정렬하고, 나머지 item은 사이에 고르게 정렬 |
| space-around | item를 군등한 여백을 포함하여 정렬 |

####  2-7. alin-item

교차축\(cross-axis\)에서 item를 정렬 방법 설정한다.

item이 한 줄이 경우 많이 사용한다.

| Title | Content |
| :--- | :--- |
| stretch \(**defalut**\) | container의 교차축을 채우기 위해 item 를 늘림 |
| flex-start | item를 시작점으로 정렬 |
| flex-end | item를 끝점으로 정렬 |
| center | item를 가운데 정렬 |
| baseline | item를 문자 기준선에 정렬 |

### 3. item 정렬

`order, flex, align-self` 등의 속성이 있다.

#### 3-1. order

item 순서를 설정, 숫자를 지정하고 숫자가 클수록 순서가 밀린다.

| Title | Content |
| :--- | :--- |
| Number | item의 순서 정렬 |

#### 3-2. flex

item의 너비\(증가, 감소, 기본\)를 설정하는 단축 속성이다.

| Title | Content |
| :--- | :--- |
| flex-grow \(**defalut : 0**\) | item의 증가 너비 비율 설정 |
| flex-shrink \(**defalut : 1**\) | item의 감소 너비 비율 설정 |
| flex-basis \(**defalut : auto**\)  | item의 공간 배분 전, 기본 너비 설정 |

#### 3-2. align-self

교차축\(cross-axis\)에서 개별 item의 정렬 방법 설정한다.

| Title | Content |
| :--- | :--- |
| auto \(**defalut : auto**\) |  container의 `align-item` 속성을 상속 받음 |
| stretch | container의 교차 축을 채우기 위해 Item을 늘림 |
| flex-start | item를 각 줄의 시작점으로 정렬 |
| flex-end | item를 각 줄의 끝점으로 정렬 |
| center | item를 가운데 정렬 |
| baseline | item를 문자 기준선에 정렬 |

