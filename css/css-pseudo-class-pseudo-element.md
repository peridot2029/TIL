# 📄 CSS - Pseudo Class, Pseudo Element

## 1. Peseudo Class 

**가상 클래스 선택자\(pesudo class\)**는 웹 문서에 소스에 존재하지 않지만 필요에 의해 임의로 가상 선택자를 지정하여 사용하는 선택자 이다.

### \(1\). X:link

문서 안의 하이퍼링크 중 아직 방문하지 않은 링크에 적용한다.

### \(2\). X:**visited** 

한 번 이상 방문한 사이트에 적용되며, 기본 색상은 자주\(puple\)색 이다.

### \(3\). X:hover

해당 요소 위에 마우스 포인터를 올려놓앗을 때 적용\(롤오버\)한다.

### \(4\). X:**focus**

해당 요소 초점이 맞춰졌을 때 적용된다. 즉, 텍스트 필드 안에 초점이 맞춰질 때를 의미한다.

### \(5\). X:**first-child**

첫 번째 자식 요소 선택한다.

### \(6\). X:**last-child** 

마지막 자식 요소 선택한다.

### \(7\). X :nth-child\(n\)

n번째 자식 요소를 선택한다. n 에는 숫자를 넣어도 된다.

odd, even, 2n+1, 2n 등의 수식을 사용할 수 있다.

```css
link-list li:nth-child(1) {
 outline : 3px solid #ff0;
}

.link-list li:nth-child(2n) {
 outline : 3px solid #ff0;
}

.link-list li:nth-child(odd) {
  outline : 3px solid #ff0;
 }

.link-list li:nth-child(2n-1) {
 outline: 3px solid #ff0;
}

.link-list li:nth-child(even){
 outline: 3px solid #ff0;
}
```

### \(8\). X:lang

 lang 속성을 가진 요소를 선택하여 사용한다.

## 2. Peseudo Element 

가상 요소 선택자 \(pesudo element\)는 가상 클래스 선택자와 엄연히 다르다.

가상 요소 선택자 \(pesudo element\)는 세미콜론\(::\) 를 두 번 사용한다. 이 문법은 CSS3 부터 적용 되었지만, 브라우저 하위 호한 목표로 인해 세미콜론\(:\) 한 번만 사용해도 된다.

### \(1\). Y:**:first-letter** 

Y의 첫 번째 줄의 첫 글자에 스타일 적용, 블록 레벨 요소만\(이미지 또는 인라인 테이블과 같은\)다른 콘텐츠로 시작하지 않을 때를 말한다.

### **\(2\)**. Y:**:first-line**

Y의 첫 번째 행에 스타일 적용하는 블록 레벨 요소를 말한다.

### \(3\). Y::before

요소의 콘텐츠 시작 부분에 생성된 콘텐츠를 추가하며, '전'을 의미한다.

### \(4\). Y::after

요소의 콘텐츠 끝부분에 생성된 콘텐츠를 추가하며, '후'를 의미한다.



### Reference <a id="reference"></a>

css 가상 요소  [→\(MDN\)](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

