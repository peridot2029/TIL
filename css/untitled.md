# 📄 Flex

### 1. container 정렬

* `display, flex-direction, justify-content`

#### 1-1. flex-direction \(default : row\)

* item 주축 설정

#### 1-2. flex-wrap \(default : nowrap\)

* item 여러 줄, 줄 바꿈 설정

#### 1-3. justify-content \(defalut : flex-start\)

* 주축 정렬 방법
* space-between - item 시작과 끝점에 고르게 정렬
* space-around - item의 균등한 여백을 포함하여 정렬

#### 1-4. align-content \(defalut : flex-start\)

* align-content를 사용하기 위해서 `flex-wrap : wrap;` 이어야 한다.
* 교차죽\(cross-axis\)의 정렬 방법, item 여러 줄 \(두 줄\) 이상 이고 여백이 있을 경우 사용 가능

### 2. item 정렬

* `order, flex, align-self` 등의 속성이 있다.

#### 2-1. flex-grow

* item의 증가 너비 비율 설정

#### 2-2. flex-basis \(defalut : auto\)

* item의 \(공간 배분 전\) 기본 너비 설정

#### 2-3. flex-shrink

* item 감소하는 너비 비율 설정

#### 2-4. flex

* item의 너비\(증가, 감소, 기본\)을 설정하는 단축 속성
* flex 단축 속성을 사용하게 되면 flex-basis는 자동으로 0 설정

