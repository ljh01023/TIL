# jQuery는 dom의 style 속성으로 코드를 삽입하므로 javascript 코드를 태그안에 인라인타입으로 삽입하지 않는것을 권장.

# javascript

## jQuery ( 선택자, for , each , this, arrow )

프론트(브라우저단)에서 최고의 호황을 누리던 라이브러리

## end : javascript 프레임워크 nodejs

- 프론트와 실행방법이 다름
- npmjs.com : npm 패키지 매니저 도구
- 서버만들기(버거로움) => express (간단히 처리됨)

# jQuery 선택자

1.  css 선택자
    js document.querySelector()
    js document.querySelectorAll()

        $('button')
        $('.show')
        $('#show')
        $('#show ~ .box')
        $('.showHide-container #show')

2.  순회 메소드
    .show+.hide next()/prev()/parent()
    자손 선택자 find()
    형제 eq(번호)/index()

# jQuery effect method

## 보임/숨김 : 애니메이션이 포함되어 있어서 제어가능

1.  show()/hide() : display:block/none ,
    기본 speed로 처리하지 않을 경우 왼쪽, 위 중심점 기준으로 움직임
2.  fadeIn()/fadeOut()/fadeToggle() : opacity
3.  slideDown()/slideUp()/slideToggle() : height
4.  animate()

### show/hide/fadeIn/fadeOut/slideUp/slideDown/animate()

effect method는 애니메이션을 포함하므로
css : animate, transition 등과 충돌 됨 >> stop()사용

## jQuery effect method의 파라미터()

- 첫번째 파라미터: speed (js에서는 delay지만, jQery에서는 speed로 사용)

  > 1s : 1000
  > speed : 기본속도는 400
  > 'fast' : 200
  > 'slow' : 600
  > 5s : 5000

- 두번째 파라미터: opacity

- 세번째 파라미터: call back

# height()/width()

1. 전달되는 파라미터가 없으면 getter
2. 전달되는 파리미터가 있으면 setter
   > speed 포함하고 있지 않음, css transition 추가가능
   > js : getWidth()/setWidth(값)
