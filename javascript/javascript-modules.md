# 📄 JavaScript Modules

### 1. Modules 

모듈은 구현해야 할 기능을 캡슐화 하고, 공개 API 제공하여 다른 코드에서 재사용 가능한 코드 블록이다.

### 2. Modules 조건

📝 **추상화 \(abstraction\)**

외부 라이브러리 기능을 위임하여 사용할 때, 복잡한 이해 없이도 사용 가능해야 한다.

📝 **캡슐화 \(encapsulation\)**

코드 내부를 외부로부터 접근할 수 없도록 감출 수 있어야 한다.

📝 **재사용 \(resuse\)**

동일한 코드를 반복하여 작성하지 않도록 재사용 가능해야 한다.

📝 **의존성 관리 \(dependency management\)**

코드를 작성하지 않고도 쉽게 의존성을 변경할 수 있어야 한다.

### 3. 클라이언트 환경에서의 Modules

웹의 탄생 시대부터 모듈이란 개념은 존재하지 않았다.

모듈 비슷한 방법은 각각 나눠진 파일을 HTML 문서에서 순차적으로 로드해야된다.

주의할 점은 의존 모듈 파일이 먼저 불러와야 올바르게 작동한다.

