## useState : 상태변경 훅(Hook)

- useState 값: 숫자, 문자, 체, 데이터, 배열 모두 가능

```javascript
import { useState } from 'react';

export default function Mainpage() {
  let [list, setList] = useState([
    // list는 배열로 heap에 저장
    '인천 을왕리 해수욕장',
    '송도 센트럴파크',
    '파주 프로방스/헤이리마을',
  ]);

  // setList = ()=>{} //변경함수
  let edit = () => {
    let copy = [...list]; //spread operator문법 (deep copy)
    copy[0] = '부산 앞바다';
    setList(copy);
  };

  // 정렬도 가능
  let dataSort = () => {
    let copy = [...list];
    copy.sort(); //오름차순 정렬
    setList(copy);
  };

  // 리액트내에서는 if문 사용이 불가능하여 삼항연산자 사용
  // 리액트내의 이벤트 핸들러사용 : on이벤트이름={실행함수} 형태로 설정

  // map(메소드, 인덱스)
  // key값은 고유한 이름이어야하며, 중복되면 안됨. (key값은 필수)
  return (
    <main>
      <div className='inputCon'>
        <input placeholder='가고싶은 여행지를 등록하세요'></input>
        <button>add</button>
      </div>

      <button onClick={edit}>데이터 수정</button>
      <button onClick={dataSort}>데이터 정렬</button>
      <div className='listArea'>
        <p>
          <strong>totoal</strong>
          <span>{list.length}</span>
        </p>
        {list.length === 0 ? (
          <NoList />
        ) : (
          <ul className='listCon'>
            {list.map((a, i) => {
              return <List list={a} i={i} key={i} />;
            })}
          </ul>
        )}
      </div>
    </main>
  );
}

// 리스트 함수(반복되는 부분)
function List({ list, i }) {
  return (
    <li className='list'>
      <p>
        <span>{i + 1}</span> {list}
      </p>
      <i className='fa-solid fa-trash-can'></i>
    </li>
  );
}

// 리스트의 개수가 0 일때 보여지는 component
function NoList() {
  return (
    <div className='noList'>
      <i className='fa-regular fa-rectangle-list'></i>
      <p>등록된 여행지가 없습니다.</p>
    </div>
  );
}
```
