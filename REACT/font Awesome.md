## Font Awesome 사용법

> public폴더 내의 index.html 파일에 링크(font awesome css) 추가 후 필요한 부분에 내용 추가.

```javascript
// index.js
// reset.css, (공용)common.css, App등 연결
import React from 'react';
import ReactDOM from 'react-dom/client';
import './css/myreset.css';
import './css/common.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />; // App.js
  </React.StrictMode>
);
reportWebVitals();
```

```javascript
// App.js
// component에서 사용하는 header, main, footer등 연결
import Header from './components/Header';
import MainPage from './components/MainPage';

export default function Main() {
  return (
    <>
      <Header />
      <MainPage />
    </>
  );
}
```
