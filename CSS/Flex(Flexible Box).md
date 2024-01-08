# Flex: 레이아웃 구성할때 사용하는 요소.
1. flex: Block 특성의 Flex Container 정렬	
2. inline-flex: Inline 특성의 Flex Container를 정렬

## Flex Container 속성
1. flex-flow : flex-direction와 flex-wrap의 단축 속성

2. flex-direction: 컨테이너가 flex 항목을 쌓을 방향을 정의
    - row(기본값): Itmes를 메인축(수평)으로 정렬 (왼쪽 > 오른쪽)
    - row-reverse : row 반대 축으로 정렬 (오른쪽 > 왼쪽, Items의 순서도 반대 정렬)
    - column : Items를 크로스축(수직)으로 정렬 (위 > 아래)
    - column-reverse : column의 반대 축으로 정렬 (아래>위, Items의 순서도 반대 정렬)

3. flex-wrap: flex items의 줄 바꿈 설정
    - nowrap(기본값) : Itmes를 한줄로 정렬 (배열 공간이 부족한 경우 Item의 너비를 줄여 한줄로 정렬)
    - wrap : Items를 여러 줄로 정렬 (Items의 배열 공간이 부족한 경우 다음 줄로 정렬)
    - wrap-reverse : wrap의 역 방향으로 정렬 (Items의 순서는 동일)

4. justify-content: flex 항목 정렬 (주축_main axis)
    - flex-start(기본값) : Items를 시작점(flex-start)에서 정렬 (왼쪽 > 오른쪽)
    - flex-end : Items를 끝점(flex-end)에서 정렬 (오른쪽 > 왼쪽)
    - center : Items를 가운데 정렬	
    - space-between : 첫번째 Item은 시작점에, 마지막 Item은 끝점에 정렬, 나머지 Items는 가운데 정렬 (좌우 여백 없음.)
    - space-around : Itmes를 일정한 간격으로 정렬 (좌우 여백있음(0.5비율), Items 간격(1비율) > 0.5 1 1 1 0.5)
    - space-evenly : Itmes를 양쪽 여백 포함 일정한 간격으로 정렬 (좌우 여백 있음, 여백 and Items 간격 비율 같음 > 1 1 1 1 1)

5. align-content: flex 항목 정렬 (크로스축(수직)_cross-axis)
    <strong>flex-wrap 속성을 통해 Items가 여러줄 이상이고 여백이 있을 경우에만 사용 가능</strong>
    - stretch(기본값) : Container의 크로스축(수직)을 채우기 위해 Items의 height값을 늘림 (Items의 heigh값이 지정 안된 경우)
    - flex-start : Items를 시작점(flex-start)으로 정렬 (상단)
    - flex-end : Items를 끝점(flex-end)으로 정렬 (하단)
    - center : Items를 가운데 정렬	
    - space-between : 첫번째 Item은 시작점에(상단), 마지막 Item은 끝점에(하단) 정렬, 나머지 Items는 가운데 정렬 (상하 여백 없음) 
    - space-around : Items를 일정한 간격으로 정렬 (상하 여백 있음)	

6. align-items: 크로스축(cross-axis)에서 Items의 정렬
    <strong> Items가 여러줄 이상일 경우, align-content 속성이 우선시 됨</strong>
    - stretch(기본값) : Container의 크로스축을(수직) 채우기 위해 Items의 height값 늘림 (Items의 heigh값이 지정 안된 경우)
    - flex-start : Items를 <strong>각 줄의</strong> 시작점(flex-start)으로 정렬 (각 줄 상단)	
    - flex-end : Items를 <storng>각 줄의</storng> 끝점(flex-end)으로 정렬 (각 줄 하단)
    - center : Items를 <strong>각 줄의</strong> 가운데 정렬	
    - baseline : Items를 text 기준선(하단)에 정렬

## Flex Items 속성
<!-- flex-grow많이 사용/grow사용하면 basis는 같이 사용하게 됨.
flex-colum: 1 / 1:1:1 비율로 사용하겠다. 많이 사용
shrink 계산법 어려워 많이 사용하지 않음. -->

1. flex : flex-grow, flex-shrink, flex-basis의 단축 속성
    - flex-shrink, flex-basis는 생략 가능
    - flex-basis는 생략할 경우 값이 0이 됨 (기본값 auto)

2. order : Item의 순서 설정
    - 기본값 : 0
    - 숫자가 클수록 Item 순서 뒤로 밀림.
    - 음수 사용 가능

3. flex-grow : Item의 증가 비율을 설정 
    - 기본값 : 0
    - 숫자가 클수록 너비값이 커짐
    - (ex)flex-grow : 1, 2, 1 > 25% , 50% , 25%

4. flex-shrink : Item의 감소 비율을 설정
    - 기본값 : 1


5. flex-basis :Item의 기본 너비 설정
    - 기본값: auto
    - auto값 사용하는 경우, <strong>flex : auto 꼭 같이 사용 할것</strong>
    - width, heigth등의 속성으로 Item의 너비 설정 가능 (auto인 경우)
    - flex-basis 생략하는 경우 값이 0이 됨.
    - flex-basis : 0 초기값으로 많이 사용함.

6. align-self : 크로스축(cross-axis) 기준으로 각 Item 정렬, Item요소에만 사용 가능 (각 Item을 크로스축(수직)기준으로 정렬)
    <strong>align-items의 속성보다 우선시 함.</strong>
    - auto(기본값) : Container의 align-items 속성 상속받음
    - stretch : Container의 크로스축을 채우기 위해 Item height값을 늘림	
    - flex-start : Item을 각 줄의 시작점(flex-start)으로 정렬 (각 줄 상단)
    - flex-end : Item을 각 줄의 끝점(flex-end)으로 정렬	(각 줄 하단)
    - center : Item을 가운데 정렬	
    - baseline : Item을 text 기준선(하단)에 정렬

### 중앙 정렬
    display: flex;
    justify-content: center;
    align-items: center;





