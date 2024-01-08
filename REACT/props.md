## props

- properties 의 줄임말
- 어떠한 값을 컴포넌트에게 전달해줘야 할 때 사용 (하위 컴포넌트에 전송)
- 객체형태로 전달
- 데이터에 있는 아이디값을 많이 사용한다. (인덱스는 잘 사용하지 않음, 키값은 전송되지 않음)

```javascript
import { useState } from 'react';
export default function Mainpage() {
  let [list, setList] = useState([
    '인천 을왕리 해수욕장',
    '송도 센트럴파크',
    '파주 프로방스/헤이리마을',
  ]);

  // list: 전달하는 이름, {list}: 전달하는 값
  // ({}) : 디스트럭쳐링 문법
  function List({ list, i }) {
    return (
      <li className='list'>
        <p>
          <span>{i + 1}</span> {list}
          <span>{props.i + 1}</span> {props.list}
          <span>{props.i + 1}</span> {props[list]}
        </p>
      </li>
    );
  }
}
```
