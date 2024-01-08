## JSX (JavaScript XML)

- JavaScript를 확장한 문법 (Javascript + XML)
- JavaScript의 공식적인 문서는 아니다.
- 브라우저에서 실행하기 전 바벨을 사용하여 일반 자바스크립트 형태의 코드로 변환

> return문 안쪽: jsx문법 적용구간

## jsx 문법의 특징

1. 부모는 하나만 존재 (부모 단일구조)
   > <></> 사용 가능 : div와 같이 별다른 뜻 없음. (fragment 문법)
1. class > className으로 사용 (js에서 class는 예약어라서 className으로 작성)
   > html: class
   > jsx: className
1. 변수 적용 가능 : {변수명}

   > 변수는 jsx 내부 모든곳에서 사용 가능
   > javascript는 {} 사용

1. 데이터 바인딩 가능
1. jsx 영역안에서 style을 전역으로 사용 가능
   > 카멜표기법으로 작성 해야함. (하이픈은 사용 불가)
   > vlue값은 ""로 감싸야함
   > 여러개 작성시 콤마 사용
