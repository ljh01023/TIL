# 리액트(REACT)

- 리액트는 사용자 인터페이스를 구축하기 위한 JavaScript 라이브러리입니다.
- 리액트로 개발하는 가장 큰 이유
  - SPA(Single Page Appication)가 가능하여 유지보수가 용이함. (header, main, footer 등 변경되는 부분만 수정가능)
  - 네이티브앱 가능 (웹,앱 모두 개발 가능)
  - 어떤 환경에서도 개발 가능 (mac, android 등)
- 프로젝트마다 새로 리액트 라이브러리 설치
  > npx crate-react-app 폴더명 (. : 이 폴더에 npm을 만들겠다)
  > host3000번으로 열림.

---

## 단축키 사용 (Snippets)

- 설정 > Configure User Snippets > javascriptreact.json 검색 > 아래 내용 입력후 저장
  > rfc 입력하면 improt부분 내용 자동 입력됨

```javascript
// snippets 저장 내용 (rfc 단축키)
{
  "reactFunction": {
    "prefix": "rfc",
    "body": [
      "import React from 'react';",
      "export default function ${1:${TM_FILENAME_BASE}}() {",
      " return (",
      "   <>",
      "   </>",
      " );",
      "}"
    ],
    "description": "Creates a React Function component"
  }
}
```

---

## 리액트 폴더

### <strong> public:

- 실제 서버에 배포되는 폴더 (빌드된 내용만 올라감)
- favicon, logo등 바뀌지 않는 내용들
- index.html (하나만 존재함)
- 정적인파일 (변경되지 않을 이미지)

  > 경로는 절대경로 사용 (/는 절대경로를 뜻하며, 보통 public을 뜻함)

  > index.html : index.html이 랜더링 되어 DOM에 출력됨. <br/>
  > index.js 실행 -> app.js실행 -> 랜더링
  >
  > > index 코드 수정외에는 거의 사용할일 없음.

<br>

### <strong> src:

- 컴파일 될때 사용되는 부분들

  > 주로 수정될 부분, 사용될 폴더를 미리 만들어 경로 수정 후 작성을 추천!

- 경로를 사용할때는 상대경로로 사용
  > 랜더링 될때 주소와 이름 바뀌어 랜더링됨.

#### components:

- 공통으로 사용되는 내용
- 기능이 일어나는, 세부적으로 사용되는 최소 단위로 구분 (Header, Footer, button 등)

- 컴포넌트의 파일명 첫 글자는 대문자(영문)
- 사용법: 함수명은 대문자로 시작

### pages:

- 섹션이나 큰 컴포넌트
- 페이지: 새로 화면이 바뀌는 경우 사용 (페이지내 세부 컴포넌트 나뉠 수 있음)

```javascript
export default function 함수명(컴포넌트 함수의 이름) (){
 return()
 }
```

```javascript
function 함수명(){
    return()
}

export default 함수명;
```

```javascript
// 여러개의 컴포넌트를 한번에 export할때는 {} 사용한다.
exprot{컴포넌트명, 컴포넌트명}

  > export {MainPage, a} 내보내기
  > 똑같이 받아오기 import {MainPage, a} form ''./pages/
```

#### css :

- css : 페이지별로 나누는게 좋음. (나중에 찾아보기 쉽도록)

#### index.js:

- 보통 리액트 셋팅용으로 대표파일 하나만 부름 (App.js)
- 컴파일되는 파일들을 import 해야함

  > 공용으로 사용하는 css (reset.css, common.css), App.js등 <br>

  ```javascript
  import '상대경로' ;

  const root = ReactDOM.createRoot(document.getElementById('root'));
  root.render(
  <React.StrictMode>
   <파일명/> or <파일명><파일명/>
  </React.StrictMode>
  );
  reportWebVitals();
  ```

#### App.js

#### gitignore: 업데이트 하지않을 내용들.

#### packge.json

- 라이브러리 히스토리 (포크로 찍어가거나, 클로닝할때 버전에 맞게 설치해줌)
- dependencies : 라이브러리 설치되어 있는 리스트
- 버전 관리 가능
- 디버그(Debug) :

  > npm install 명령어로 모듈 설치 가능

noscript: 스크립트가 실행되지 않았을대 보이는 메세지
