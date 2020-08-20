# 📄 CSS Flex - flex item

## 1. flex

**flexbox**는 뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때에도 효율적으로 요소를 배치, 정렬, 분산할 수 있는 방법을 제공하는 CSS3의 **새로운 레이아웃 방식**이다.

## 2. flex item

전체적인 정렬이나 흐름에 관련된 속성은 **flex container**에 정의하고, 자식 요소의 크기나 순서에 관련된 속성은 **flex item**에 정의한다.

![](../.gitbook/assets/flex-base.webp)

### \(1\). flex

`flex-grow`, `flex-shrink`, `flex-basis` 속성을 축약해서 `flex` 속성으로 표현한다. 

즉, 속성의 값으로 정수 하나만 선언하면, 선언한 값은 `flex-grow` 속성 값이 된다. 

나머지는 기본값인 `flex-shrink : 1` 속성과 `flex-basis : 0` 속성이 적용된다.

 📝**flex  :  1**

`flex : 1` 속성은 `flex : 1 1 0` 속성을 의미한다.

📝 **flex : 2  flex : 3** 

`flex : 2 1 0`, `flex : 3 1 0`을 나타낸다.

### \(2\). flex-grow

`flex-grow` 속성은 **flex item의 확장에 관련된 속성**이다. 0과 양의 정수를 속성값에 사용한다.

📝 **flex-grow : 0 \(defalut\)**

속성 값이 0 이면 flex container의 크기가 커져도, flex item의 크기가 커지지 않고 원래 크기로 유지된다.

📝 **flex-grow : 1**

속성 값이 1 이상이면 flex container가 커질 때 flex item의 크기도 커지게 하려면 1 이상의 값을 속성 값으로 설정한다.

flex item은 원래 크기와 상관 없이 flex container를 채우도록 flex item의 크기가 커진다.

### \(3\). flex-shrink

`flex-shrink` 속성은 **flex item의 축소에 관련된 속성**이다. 0과 양의 정수를 속성값에 사용한다. 기본값은 1이다.

📝 **flex-shrink : 0**

속성 값이 0 이면 flex container의 크기가 flex item의 크기보다 작아져도 크기가 줄어들지 않고 원래 크기로 유지된다.

📝 **flex-shrink : 1 \(defalut\)**

속성 값이 1 이상 이면 flex container의 크기가 flex item의 크기보다 작아질 때 flex item의 크기가 flex container에게 맞추어 줄어든다.

### \(4\). flex-basis

📝 **flex-basis : px, %, em, rem**

`width` 속성에서 사용하는 모든 단위\(`px, %, em, rem`\)를 속성 값에 사용할 수 있다.

속성 값을 px 또는 %와 같은 단위를 사용해서 설정한다면 flex item의 크기가 고정된다.

📝 **flex-basis : 0**

속성 값을 0으로 설정하면, flex item은 절대적 flex item\(absoulte flex item\)이 되어 flex container 기준으로 크기가 결정된다.

{% hint style="warning" %}
속성 값을 0 으로 선언할 때에는 `flex-basis: 0px`, `flex-basis: 0%`와 같은 단위도 함께 설정해야 된다.
{% endhint %}

📝 **flex-basis : auto \(defalut\)**

속성 값을 auto로 설정하면 flex item은 상대적 flex item\(relative flex item\)이 되어 콘텐츠의 크기를 기준으로 크기가 결정된다.

![](../.gitbook/assets/helloworld-201811-flex_10.png)

### \(5\). order

`order` 속성은 flex item의 순서와 관련된 속성이다. 0 부터 값이 클수록 밀리기 때문에 정수와 음수를 속성 값에 사용한다. 기본 값은 0 이다.

📝 **order : -1**

속성 값을 -1으로 설정하면, order의 기본값 보다 작은 음수 값 이기 떄문에 가장 먼저 표시할 수 있다.

📝 **order : 1**

다른 flex item들을 속성 값을 기본값으로 0으로 설정 후, 어떤 flex item의 속성 값을 1로 설정한다면, 가장 마지막에 표시 된다.



