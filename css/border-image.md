# 📄 border-image

### 1. border-image 

border-image 속성은 요소를 둘러싸는 테두리\(border\)에 이미지를 사용할 수 있다.

* `border-image-outset`
* `border-image-repeat`
* `border-image-slice`
* `border-image-source`
* `border-image-width`

### 2. border-image Property

#### 1\) border-image-outset

`border-image-outset`속성은 요소의 테두리 상자와 테두리 이미지의 거리를 설정한다.

`border-image-outset` 으로 인해 요소 바깥에 그려지는 테두리로는 스크롤이 생기지 않으며, 마우스 이벤트가 발생하지 않는다.

```css
border-image-width: [<length> | <number>]{1,4}
```

| property value | description |
| :--- | :--- |
| `length` | 테두리 거리의 크기로 고정값 사용 |
| `number` | 테두리 거리의 크기로 `border-width`의 배수를 사용. |

#### 2\) border-image-repeat

border-image-repeat 속성은 이미지의 모서리 영역을 요소의 테두리 이미지 크기에 맞춰 조절할 때 사용할 방법이다.

```css
border-image-repeat: [ stretch | repeat | round | space ]{1,2}
```

| property value | description |
| :--- | :--- |
| `stretch(default)` | 이미지의 영역을 늘리거나, 줄여 간격을 채운다. |
| `repeat` | 이미지의 모서리 영역을 타일처럼 반복해 간격을 채운다. 크기가 맞지 않으 마지막 이미지는 짤린다. |
| `round` | 이미지의 모서리의 영역을 타처럼 반복해 간격을 채운다. 크기가 맞지 않으면 늘어나거나, 줄어든다. |
| `space` | 이미지의 모서리 영역을 타일처럼 반복해 간격을 채운다. 크기가 맞지 않으면 각 타일에 균등하게 공백을 배치한다. |

#### 3\) border-image-slice

`border-image-slice` 속성은 `border-image-source`로 설정한 이미지를 여러 개의 영역으로 나눈다. 이렇게 나눠진 영역이 요소의 테두리 이미지를 이룬다.

```css
border-image-slice: [<number> | <percentage>]{1,4} && fill?
```

| property value | description |
| :--- | :--- |
| `number` | 픽셀로 거리를 지정 |
| `%` | 이미지의 크기에 대한 상대적인 크기를 지정 |
| `fill` | 테두리 이미지의 가운데 영역을 배경 이미지 처럼 사용 |

#### 4\) border-image-source

`border-image-source`  속성은 요소의 테두리 이미지로 사용할 이미지를 지정한다.

```css
border-image-source: none | <image>
```

| property value | description |
| :--- | :--- |
| `none` | border-image를 사용하지 않고, border-style이 대신 표시 |
| `image` | 테두리에 사용할 이미지를 참조 |

#### 5\) border-image-width

border-image-width 속성은 테두리 이미지 너비\(width\)를 설정한다.

| property value | description |
| :--- | :--- |
| `length` |  |
| `number` |  |
| `%` |  |
| `auto` |  |



