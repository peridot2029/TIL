# Gradient

### 1. Gradient ?

* 그래디언트\(gradient\)란 둘 이상의 색상 사이의 표현을 부드럽게 전환해주는 효과를 의미한다.
* CSS3는 선형 그래디언트\(liner gradinets\), 원형 그래디언트\(radial gradients\) 두 가지 형태가 있다.

### 2. liner gradinets

* 선형 그래디언트\(liner gradinets\)는 적용된 HTML 요소에 선형으로 그래디언트 효과를 적용시켜 준다.
* 선형 그래디언트를 만들기 위해서는 최소한 두 개 이상의 색상 지정점이 필요하다.

```css
background: liner-gradinet(진행방향, 색상지정점1, 색상지정점2, ...);
```

* 색상 지정점은 그래디언트 효과로 그 사이의 색상 표현을 부드럽게 전환해주고 싶은 색상을 명시한다.
* 가장 먼저 정의된 색상 지정점이 시작되며, 그 후로는 마지막 지정점까지 차례대로 그래디언트 효과가 적용된다.

#### 1\).  진행 방향 설정

* 선형 그래디언트는 효과의 기본 진행 방향은 위쪽에서 아래로 진행된다.
* 그래디언트의 진행방향은 top, right, bottom, left 뿐만 아니라 대각선으로 설정할 수 있다.

#### 2\). 투명도 설정

* 그래디언트에 투명도를 추가하고 싶을 때는 rgba 색상값을 사용한다.
* rgba 색상값의 알파 채널 값은 완전한 투명 상태인 0.0부터 투명도가 전혀 없는 1.0 사이의  값을 가진다.

#### 3\). repeating-liner-gradinet\(\) method

* repating-liner-gradinet\(\) 메서드는 선형 그래디언트 효과가 계속 반복되도록 설정한다.

### 3. radial-gradinet



```css
radial-gradient(shape size at position, color1, color2, ..., color3);
```



#### 1\).  색상 지정점 사이의 간격 조절

#### 2\). 모양 설정



#### 3\). 크기 설정





