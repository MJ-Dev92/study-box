# CSS

## 기본 문법
- 선택자(스타일(CSS)을 적용할 **<u>대상</u>**(Selector)){속성:(은)값;(이다)}

## CSS 선언 방식
- 내장방식, 링크방식, 인라인 방식, @import방식

## 내장 방식
- styple의 내용(Contents)으로 스타일을 작성하는 방식

```html
<style>
  div {
    color : red;
    margin : 20px;
  }
</style>
```

## 인라인 방식
- 요소의 style 속성에 직접 스타일을 작성하는 방식(선택자 없음)

```html
<div style="color : red; margin: 20px;"></div>
```

## 링크 방식
- 병력방식
- \<link />로 외부 CSS문서를 가져와서 연결하는 방식

```html
<link rel="stylesheet" href="../CSS/main.css" />
```
```css
div {
  color: red;
  margin: 20px;
}
```

## Import 방식
- CSS의 @import규틱으로 CSS 문서 안에서 또 다른 CSS문서를 가져와 연결하는 방식
- 직렬방식 연결이 지연되는 점이 장점이자 단점이다
```html
<link rel="stylesheet" href="../CSS/main.css" />
```
```css
/* main.css */
@import url("./box.css");

div {
  color: red;
  margin: 20px;
}
```
```css
/* box.css */
.box {
  background-color: red;
  padding: 20px;
}
```
---
## CSS 선택자
- 기본, 복합, 가상클래스, 가상요소, 속성

## 기본
기호 | 용도
--|--
*(전체 선택자) | 모든 요소를 선택
ABC(태그 선택자) | 태그 이름이 ABC인 요소 선택
.ABC(클래스 선택자) | HTML **<u>class 속성의 값</u>**이 ABC인 요소 선택
#ABC(아이디 선택자) | HTML **<u>id 속성의 값</u>**이 ABC인 요소 선택

## 복합 선택자
기호 | 용도
--|--
ABC.XYZ(일치 선택자) | 선택자 ABC와 XYZ를 **<u>동시에 만족</u>**하는 요소선택
ABC > XYZ(자식 선택자) | 선택자 ABC와 **<u>자식 요소</u>** XYZ 선택
ABC XYZ(후손선택자) | 선택자 ABC의 **<u>하위 요소</u>** XYZ 선택 '띄어쓰기'가 선택자의 기호
ABC + XYZ(인접 형제 선택자) | 선택자 ABC의 다음 형제 요소 XYZ **<u>하나를 선택</u>**
ABC ~ XYZ(일반 형제 선택자) | 선택자 ABC의 다음 형제 요소 XYZ **<u>모두를 선택</u>** 

## 가상 클래스 선택자
기호 | 용도
--|--
ABC:hover | 선택자 ABC요소에 **<u>마우스 커서가 올라가 있는 동안</u>** 선택 
ABC:active | 선택자 ABC요소에 **<u>마우스를 클릭하고 있는 동안</u>** 선택
ABC:focus | 선택자 ABC요소가 **<u>포커스되면</u>** 선택
ABC:first-child | 선택자 ABC가 형제 요소 중 첫째라면 선택
ABC:last-child | 선택자 ABC가 형제 요소 중 막내라면 선택
ABC:nth-child(n) | 선택자가 ABC가 형제 요소 중 (n)째라면 선택
ABC:not(XYZ)(부정선택자) | 선택자가 XYZ가 아닌 ABC 요소 선택

**<u></u>**
## 가상 요소 선택자
기호 | 용도
--|--
ABC::before | 선택자 ABC 요소의 **<u>내부 앞</u>**에 내용(Content)을 삽입
ABC::after | 선택자 ABC 요소의 **<u>내부 뒤</u>**에 내용을 삽입


## 속성 선택자
기호 | 용도
--|--
[ABC] | 속성 ABC를 포함한 요소 선택
[ABC="XYZ"] | 속성 ABC를 포함하고 값이 XYZ인 요소 선택


```css
[type] {
  color: red;
}

[type="password"] {
  color: red;
}
```


## 스타일 상속
- 상속되는 CSS 속성들..
    - 모두 글자/문자 관련 속성들(모든 글자/ 문자속성은 아님 주의!)
    - font-style : 글자 기울기
    - font-weight : 글자 두꼐
    - font-size : 글자 크기
    - line-height : 줄 높이
    - font-family : 폰트(서체)
    - color : 글자 색상
    - text-align : 정렬
    - ....

## 강제 상속

```css
.parent {
  width: 300px;
  height: 200px;
  background-color: red;
}

.child {
  width: 100px;
  height: inherit;  /* inherit 상속이라는 뜻 */
  background-color: inherit;
  position: fixed;
  top: 100px;
  right
}
```

## 선택자 우선순위
- 우선순위란, 같은 요소가 여러 선언의 대상이 된 경우, 어떤 선언의 CSS속성을 우선 적용할지 결정하는 방법

1. 점수가 높은 선언이 우선함!
1. 점수가 같으면, 가장 마지막에 해석된 선언이 우선함
1. 점수를 계산하는것을 명시도라고 한다

선택자 | 점수
--|--
!important | 999999점
인라인 선언방식 | 1000점
ID | 100점
Class | 10점
tag | 1점
all | 0점
not | 0점
::befor(요소) | 1점

----
# CSS속성
- 속성 종류
- 박스 모델, 글꼴,문자, 배경, 배치, 플렉스(정렬), 전환, 변환, 띄움, 애니매이션,  
그리드, 다단, 필터

## 박스모델
속성 | 기본값 | 단위 | 용도
--|--|--|--
width | auto | px, em, vw등 | 가로 너비
height | auto | px, em, vw등 | 세로 너비
max-widh | none | px, em, vw | 최대 가로
max-height | none | px, em, vw | 최대 세로
min-widh | 0 | px, em, vw | 최소 가로
min-height | 0 | px, em, vw | 최소 세로

```css
.parent {
  /* width: 300px; */
  height: 200px;
  background-color: red;
}

.child {
  width: auto;
  max-width: 300px; /* 300보다 커질수 없다 부모요소만 최대너비 */
  height: 100px;
  background-color: khaki;
}

.parent {
  width: 300px;
  height: 200px;
  background-color: red;
}

.child {
  width: auto;
  min-width: 400px; /* 400보다 작아질 수 없다 부모요소만 최소너비 */
  height: 100px;
  background-color: khaki;
}
```

## 단위
단위 | 크기
--|--
px | 픽셀
% | 상대적 백분율
em | 요소의 글꼴 크기 (1em === 기본 폰트사이즈(16px))
rem | 루트 요소(html)의 글꼴 크기 (최상위 요소 = html)
vw | 뷰포트 가로 너비의 백분율 (1vw === 1/100)
vh | 뷰포트 세로 너비의 백분율 (1vh === 1/100)

```css
html {
  font-size: 16px;
}

.parent {
  width: 300px;
  height: 200px;
  background-color: red;
  font-size: 10px;
}

.child {
  width: 20em;  /* 조상 상속 받으면 320px, 부모 상속받아서 20em = 200px  */
  height: 50%;
  background-color: khaki;
}
```
```css
html {
  font-size: 16px;
}

.parent {
  width: 300px;
  height: 200px;
  background-color: red;
  font-size: 10px;
}

.child {
  width: 20rem;  /* 조상요소에만 상속받는다  */
  height: 50%;
  background-color: khaki;
}
```
```css
html {
  font-size: 16px;
}

.parent {
  width: 300px;
  height: 200px;
  background-color: red;
  font-size: 10px;
}

.child {
  width: 100vw;  /* view포트 100% 가로너비  */
  height: 50vh; /* view포트 50% 세로너비 */
  background-color: khaki;
}
```

## margin 외부여백
- 요소의 외부 여박(공간)을 지정하는 단축속성
- 음수 사용가능
- auto는 가로(세로)너비 요소의 가운데 정렬에 활용

이름 | 기본값 | 단위 | 속성
--|--|--|--
margin | auto | px, em, vw | auto

```css
/* 단축 속성 */
margin : 10px 20px; /* 위아래, 좌우 */
margin : 10px 20px 30px;  /* 위, 좌우, 아래 */
margin : 10xp 20px 30px 40px; /* 위, 오른쪽, 아래, 왼쪽 */
```

## padding 내부여백
- 요소의 내부 여백(공간)을 지정하는 단축 속성

이름 | 기본값 | 단위 | %
--|--|--|--
padding | auto | px, em, vw | 부모 요소의 가로 너비에 대한 비율로 지정


## border 테두리
- 요소의 테두리 선을 지정하는 단축속성

이름 | 속성 | 속성 | 속성
--|--|--|--
boder | border-width | border-style border-color
boder-width | 
border-style | none, solid, dotted, dashed, double | groove(홈이 파여있는 모양), ridge(솟은 모양(groove의반대)) | inset(요소 전체가 들어간 모양),outset(요소 전체가 나온모양)
border-color | black(기본값) | transparent(투명)

```css
border : medium none black; /* 기본값 */
```
- 색상 표현  
    -색을 사용하는 모든 속성에 적용 가능한 색상표현  

색상 이름 | Hex 생상코드 | RGB | RGBA | HSL | HSLA
--|--|--|--|--|--
브라우저에서 제공하는 색상이름 | 16진수 색상 | 빛의 삼원색 | 빛의 삼원색 + 투명도 | 색상,채도, 명도 | 색상, 채도, 명도, + 투명도
red, tomato | #000, #FFFFFF | rgb(255,255,255) | rgba(0,0,0,0.5) | hsl(120,100%,50%) | hsla(120,100%,50%,0.3)

## 요소의 테두리 선을 지정하는 기타 속성들
- border-방향 , border-방향-속성

```css
border-top: 두꼐 종류 색상;
border-top-width: 두께;
border-top-style: 종류:
border-top-color: 색상;
```

## border-radius
- 기본값 : 0 (둥글게 ㅇ벗음)
- 단위 : px, em, vw
- border-radius: 0 10px 0 0; 왼위 오른위 오른아래 왼아래

## box-sizing
- 요소의 크기 계산 기준을 지정

- 기본값 : content-box(요소의 내용으로 크기 계산, 요소 크기(가로세로)로 기준한다)
- border-box : 요소의 내용 + padding + border로 크기 계산(요소내용 + padding+ border크기를 포함 한채로 요소 크기(가로세로)로 기준한다)


## overflow
- 요소의 크기 이상으로 내용이 넘쳤을 때, 보여짐을 제어하는 단축 속성

- 기본값(visible) : 넘친 내용을 그대로 보여줌
- hidden : 넘친 내용을 잘라냄
- scroll : 넘친 내용을 잘라냄, 스클로바 생성
- auto : 넘친 내용이 있는 경우에만 잘라내고 스크롤바 생성

- 요소의 크기 이상으로 내용이 넘쳤을 때 , 보여짐을 제어하는 개별 속성들
    - overflow-x
    - overflow-y

## display
- 요소의 화면 출력(보여짐) 특성

- block(기본값) : 상자(레이아웃) 요소
- inline(기본값) : 글자 요소
- inline-block : 글자 + 상자요소
- flex : 플렉스 박스(1차원 레이아웃)
- grid : 그리드(2차원 레이아웃)
- none : 보여짐 특성 없음, 화면에서 사라짐
- 기타 : table, table-row, table-cell등


## opacity
-요소 투명도
1(기본값) : 불투명
0~1 : 0부터 1사이의 소수점 숫자


## 글꼴
- font-style
    - 글자의 기울기
    - normal(기본값) : 기울기 없음
    - italic : 이텔릭체
    - oblique : 기울어진 글자
- font-weight
    - 글자의 두께(가중치)
    - normal,400(기본값): 기본 두께
    - bold,700 : 두껍게
    - bolder : 상위(부모) 요소보다 더 두껍게
    - lighter : 상위(부모) 요소보다 더 얇기
    - 100~900 : 100단위의 숫자 9개, normal과 bold 이외 두께

- font-size
    - 글자의 크기
    - 16px(기본값) : 기본 크기
    - 단위 : px, em, rem
    - % : 부모요소의 폰트 크기에 대한 비율
    - smaller : 상위(부모) 요소보다 작은 크기
    - larger : 상위(부모) 요소보다 큰 크기
    - xx-small~xx-karge : 가장 작은 크기~ 가장 큰크기까지 7단계 크기 지ㅓㅇ


## line-hight
- 한 줄의 높이, 행간과 유사
- normal(기본값) : 브라우저의 기본 정의를 사용
- 숫자 : 요소의 글꼴 크기의 배수로 지정 (폰트 기본 크기 16px * 1.4) **<u>추천!!</u>**
- 단위 : px,em,rem등의 단위로 지정
- % : 요소의 글꼴 크기의 비율로 지정

```css
/* 4개 모두 같다 */
font-size: 16px;
line-height: 32px
line-height: 2
line-height: 200%
```

## 문자
- color : 글자의 색상
- text-align : 문자의 정렬 방식

    - left, right, center, justify(양쪽정열)
- text-decoration : 문장의 장식(선)

    - none(기본값)
    - underline
    - overline
    - line-through : 중앙 선

- text-indent : 문자 첫 줄의 들여쓰기(반대는 내어쓰기(outdent))
  - 음수가능
  - 들여쓰기 없음
  - 단위 px, em, rem


## 배경

- background-color
    - trnasparent : 투명함
    - 색상
    
- background-image

- background-repeat
    - repeat : 이미지를 수직, 수평 반복
    - repeat-x : 이미지를 수평 반복
    - repeat-y : 이미지를 수직 반복
    - no-repeat : 반복 없음
- background-position

   - 방향 : top,bottom
   - 단위 : px, em, rem

- background-size
    - auto : 이미지의 실제 크기
    - 단위
    - cover : 비율을 유지, 요소의 더넓은 너비에 맞춤
    - contain: 비율을 유지, 요소의 더 짧은 너비에 맞춤

- background-attachment
    - scroll(기본값) : 이미지가 요소를 따라서 같이 스크롤
    - fixed : 이미지가 뷰포트에 고정 스크롤x
    - local : 요소 내 스크롤 시 이미지가 같이 스크롤

## 배치

- position : 요소의 위치 지정 기준
    - sraic : 기준없음
    - relative : 요소 자신을 기준
    - absolute : 위치 상 부모 요소를 기준, 위치상 부모 요소를 꼭 확인!
    - fixed : 뷰포트(브라우저)를 기준
    - sticky : 스크롤 영역 기준 

## 요소 쌓임 순서(stack order)
- 어떤 요소가 사용자와 더 가깝게 있는지(위에 쌓이는지) 결정

    1. 요소에 position속성의 값이 있는 경우 위에 쌓임(기본값 static 제외)
    1. 1번 조건이 같은 경우, z-index 속성의 숫자 값이 높을 수록 위에쌓임
    1. 1번과 2번 조건까지 같은 경우, HTML의 다움 구조일 수록 위에 쌓임

- z-index : 요소의 쌓임 정도를 지정
    - auto : 부모 요소와 동일한 쌓임 정도
    - 숫자 : 숫자가 높을 수록 위에 쌓임

- 요소의 display가 변경됨
    - position속성의 깂으로 absolute, fixed가 지정된 요소는, display 속성이 block으로 변경됨


----

## flex(정렬)

- flex container와 flex item이 나누어져 있는 이유는 넣을 수 있는 속성값이 다르기 때문
    - flex container 속성값 : display, flex-flow, flex-direction, felx-wrap, justify-content, align-content, align-content, align-items

    - flex item : order, flex, flex-grow, flex-shring, flex-basis, align-self

- display : flex container의 화면 출력(보여짐)특성
    - flex: 블록 요소와 같이 flex container 정의
    - inline-flex: 인라인 요소와 같이 flex container 정의

- flex-direction : 주 축을 설정
    - row : 행 축(좌 => 우)
    - row-reverse : 행 축(우 => 좌)
    - column : 열 축(위 => 아래)
    - column-reverse : 열 축(아래 => 위)

- flex-wrap : flex items 묶음(줄 바꿈) 여부
    - nowrap : 묶음(줄 바꿈) 없음
    - wrap : 여러 줄로 묶음
    - wrap-reverse : wrap의 반대 방향으로 묶음

- justify-content : 주 축의 정렬 방법
    - flex-start : flex items를 시작점으로 정렬
    - flex-end : flex items를 끝점으로 정렬
    - center : flex items를 가운데 정렬
    - space-between : 각 flex item 사이를 균등하게 정렬
    - space-around : 각 flex item의 외부 여백을 균등하게 정렬

- align-content : 교차 축으 여러 줄 정렬 방법
    - stretch : flex items를 기작점으로 정렬
    - flex-start : flex items를 시작점으로 정렬
    - flex-end : flex items를 끝점으로 정렬
    - center : flex items를 가운데 정렬
    - space-between : 각 flex item 사이를 균등하게 정렬
    - space-around : 각 flex item의 외부 여백을  균등하게 정렬

- align-items : 교차 축의 한 줄 정렬 방법
    - stretch : flex items를 교차 축으로 늘림
    - flex-start : flex items를 각 줄의 기작점으로 정렬
    - flex-end : flex items를 각줄의 끝점으로 정렬
    - center : flex items를 각줄의 가운데 정렬
    - baseline : flex items를 각 줄의 문자 기전선에 정렬


## flex items

- order : flex item의 순서
    - 0 : 순서가 없음
    - 숫자 : 숫자가 작을 수록 먼저

- flex-grow : flex item의 증가 너비 비율
    - 0 : 증가 비율 없음
    - 숫자 : 증가 비율

- flex-shrink : flex item의 감소 너비 비율
    - 1 : flex container 너비에 따라 감소 비율적용
    - 숫자 : 감소 비율

- flex-basis : flex item의 공간 배분 전 기본 너비
    - auto : 요소의 content 너비
    - 단위 : px, em, rem


## 전환

- transition : 요소의 전환(시작과 끝) 효과를 지정하는 단축 속성
    - transition-property : 속성명
    - transition-duration : 지속시간
    - transition-timing-function : 타이밍함수
    - transition-delay : 대기시간

- transition-property : 전환 효과를 사용할 속성 이름을 지정
    - all : 모든 속성에 적용
    - 속성이름 : 전환 효과를 사용할 송성 이름 명시

```css
div {
  width: 100px;
  height: 100px;
  background-color: orange;
  transition: width 1s; /* 가로만 스무사하게 바뀌고 색상은 확 바뀐다. */
}
div:active {
  width: 300px;
  background-color: royalblue;
}
```

- transition-duration : 전환 효과의 지속시간을 지정
```css
div {
  width: 100px;
  height: 100px;
  background-color: orange;
  transition: 
  width .5s,    /* 가로는 빨리 변하고 컬러는 천천히 변한다 */
  background-color 2s;
}
div:active {
  width: 300px;
  background-color: royalblue;
}
```

- transition-timing-function : 전환 효과의 타이밍(Easing) 함수르 지정
    - ease : 느리게 - 빠르게 - 느리게
    - linear : 일정하게
    - ease-in : 느리게 - 빠르게
    - ease-out : 빠르게 - 느리게
    - ease-in-out : 느리게 - 빠르게 - 느리게
    - 구글 검색창에 [easing functions](https://easings.net/ko) 검색
    [easing functions mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function)
    - [tweenmax easing](https://greensock.com/docs/Easing) : 시각적으로 확인하고 가져와 쓸수도 있다

- transition-delay : 전환 효과가 몇 초 뒤에 시작할지 대기시간을 지정
```css
  div {
  width: 100px;
  height: 100px;
  background-color: orange;
  transition: 1s .5s;
}

div:active {
  width: 300px;
  background-color: royalblue;
}
```

## 변환

- transform: 변환함수1 변환함수2 변환함수3 ...;
- trnasform: 원근법 이동 크기 회전 기울임;
```css
.container {
  width: 100px;
  height: 100px;
  background-color: orange;
}

.container .item {
  width: 100px;
  height: 100px;
  background-color: royalblue;
  transform: rotate(45deg) scale(1.3);  /* 45도 회전, 1.3배 커진다. */
}
```

## 2D 변환 함수
- px
    - translate(x, y) : 이동(x축, y축)
    - translate(x) : 이동(x축)
    - translate(y) : 이동(y축)
    - scale(x,t) : 크기(x축, y축)

- deg
    - rotate(degree) : 회전(각도)
    - skewX(x) : 기울임(x축)
    - skewY(y) : 기울임(y축)

## 3D 변환 함수(잘 안쓰임)
- px
    - perspective(n) : 원근법(거리) :transform 사용할때 제일 앞에 작성해야한다.
- deg
    - rotateX(x) : 회전(x축)
    - rotateY(y) : 회전(y축)

## perspective : 속성과 함수 차이점

속성/함수 | 적용 대상 | 기준점 설정
--|--|--
perspectiv : 600px; | 관찰 대상의 부모 | perspctive-origin
transform : perspctive(600px) | 관찰 대상 | transform-origin

## backface-visibilty
- 3D 변환으로 회전된 요소의 뒷면 숨김 여부
- visible : 뒷면 보임
- hiddn : 뒷면 숨김
