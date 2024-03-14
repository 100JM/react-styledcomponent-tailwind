React - vanilla CSS & styled-components & tailwind CSS
============

   
Vanilla CSS
----------
### 장단점
- 장점   
1. 말 그대로 바닐라 CSS이기 때문에 특별한 관례를 따르지 않아도 된다.
2. 컴포넌트 파일에서 import해서 사용하니 스타일링을 추가하려는 사람으로 인해 방해를 받거나 간섭을 받지 않고 컴포넌트 작업을 할 수 있다.

- 단점
1. CSS를 알아야 한다.
2. CSS 코드와 규칙은 여러개의 파일로 나누어 특정 컴포넌트 파일로 import하더라도 해당 컴포넌트로 스코핑되지 않는다.   
   즉, 다른 컴포넌트 간에 스타일 충돌이 발생할 수 있다.

### Inline 스타일
style 속성에 중괄호가 필요하고 카멜 표기법 or 작은 따옴표로 key를 지정한다.
> 설정한 jsx 요소에만 영향을 미친다는 장점이 있지만 모든 요소를 개별적으로 스타일하므로 추가와 수정에 효율적이지 않다.
```jsx
<p style={{textAlign: 'center'}}>Inline styling</p>

// 조건부 스타일링
<input style={{backgroundColor: 1 === 1 ? 'red' : 'black'}} />
```

### CSS module
CSS 모듈을 사용하여 스타일 코드와 규칙을 컴포넌트에 스코핑되도록 할 수 있다.   
> 많은 컴포넌트를 사용하는 큰 프로젝트라면 각각 자체의 CSS 파일을 갖게되는 단점도 있다.

CSS 파일명에 .module 패턴을 추가한다.   
이는 기본 빌드 프로세스에 대한 신호로 볼 수 있다.   
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/d50ae598-3482-4e81-a815-72cbb1dd8b4f)   

CSS 모듈을 사용한 컴포넌트에서 아래와 같이 import 한다음 사용하면된다.   
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/24ddab73-7d0f-47ab-8525-9a6b37fcd571)   
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/0a098b07-8c8d-4aec-82e1-315e01e42b22)

랜더링된 DOM에 적용된 클래스와 헤더 섹션에 주입된 스타일 살펴보면 이상한 이름이 있는 것을 볼 수 있는데 이는 빌드 툴에 의해 자동으로 생성된 것이다.   
이것이 CSS 모듈의 개념이며 이 클래스 이름은 이제 해당 컴포넌트에 대해 고유하게된다.   
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/069f7531-c116-43f6-828c-4f558b12a67d)   
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/48d6988c-6aa6-4ad6-82d8-8764e7f969d2)

styled-components
--------
### 개념
styeld-components 패키지는 바닐라 CSS를 기반으로하는 솔루션 중 하나로 CSS 규칙이나 스타일을 별도의 파일이나 인라인 스타일로 지정하지 않고 해당 패키지의 도움을 받아 생성된 특별한 컴포넌트내에서 정의하는 것이다.   
터미널에서 npm install styled-components를 실행하여 설치 할 수있다.

### 적용하기
styled-components로부터 styled를 import하고 자바스크립트 객체인 styled를 사용하여 다른 속성에 접근한다.   
매핑되는 속성들은 해당 html 요소를 개발자가 설정한 스타일을 가지는 개별 컴포넌트로 만들어준다.   
작성한 요소 속성 다음 백틱 안에 원하는 스타일을 설정하면 된다.   
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/6e0a6106-cda5-462c-85fc-683a219b866b)
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/eda3666a-4ea1-4ec9-abdb-e56974b740e5)   

적용된 스타일을 살펴보면 styled-components는 고유한 CSS 클래스 이름은 생성하고 헤더 섹션에서 해당 클래스에대해 개발자가 작성한 CSS 규칙을 정의한다.   
그런 다음 생성된 클래스를 요소에 추가한다.   
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/5f136550-fab0-40b3-812e-617d7308f01d)
![image](https://github.com/100JM/react-styledcomponent-tailwind/assets/85985604/3150c2da-d5ce-4281-8b0e-b9bf97d6cf91)


