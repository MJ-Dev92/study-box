# HTML

## 요소(Element)
<태그>내용(contents)</태그>

## 상위요소 부모요소 자식요소 

```html
  <div> <!-- 상위요소 (자식 기준 부모이상의 것들은 상위요소라고 부른다.) -->
    <div> <!-- 부모요소 -->
      <div>sss</div> <!-- 자식요소 (상위요소 기준으로 하위요소라고 불린다.) -->
    </div>
  </div>
```

## 속성, 값

```html
  <태그>속성(Attribte)="값(Value)">내용</태그>
  <img src="" alt="">
  <input type="text">
  <br>
```

## 글자와 상자
- 요소가 화면에 출력되는 특성, 크게 2가지로 구분
    - 인라인(Inline)요소 : 글자를 만들기 위한 요소들
    - 블록(Block)요소 : 상자(레이아웃)를 만들기 위한 요소들

## 인라인(Inline)
- span : 대표적인 인라인 요소! 본질적으로 아무것도 나타내지 않는, 콘텐츠 영역을 설정하는  
용도
```html
  <span>Hello</span> 
  <span>World</span>
  <span><div></div></span> <!-- block요소 자식으로 사용 불가 -->
  <span><span></span></span>  <!-- 가능 -->
```
- 인라인은 포함한 콘텐츠 크기만큼 자동으로 줄어듬
- css속성으로 요소의 width,height,padding,margin 지정해도 반응이 없다


## 블록(Block)
- div : 대표적인 블록요소! 본질적으로 아무것도 나타내지 않는,  
콘텐츠 영역을 설정하는 용도
```html
  <div>Hello</div>
  <div>World</div>
  <div><div></div></div>  <!-- 가능 -->
  <div><span></span></div>  <!-- 가능 -->
```
- 요소가 수직으로 쌓임
- 부모 요소의 크기만큼 width가 자동으로 늘어남
- 포함한 콘텐츠 크기만큼 height 자동으로 줄어듬!
- css속성 width,height,padding,margin 반응함  


# 핵심 요소 정리
## Block요소
요소 | 용도 | 속성
--|--|--
div | 특별한 의마가 없는 구분을 위한 요소. (Division) | tapindex = '-1' (탭 할수있는 속성)
Heading1 | 제목을 의미하는 요소(Heading)
p | 문장을 의미하는 요소(Paragraph)
ul | 순서가 필요없는 목록의 집합을 의미(Unordered List)
li | 목록 내 각 항목(List Item)


## Inline요소
요소 | 용도 | 속성
--|--|--
img | 이미지를 삽입하는 요소.(image)
a | 다른/같은 페이지로 이동하는 하이퍼링크를 지정하는 요소 | target="_blank"(새탭)
span |  특별한 의미가 없는 구분을 위한 요소
br/ | 줄바꿈 요소(Break)

## Inline-Block요소
- 수평으로 쌓이지만 가로 세로값이 적용된다
- 인라인베이스지만 블록도 가지고 있다  

요소 | 용도 | 속성 | 타입
--|--|--|--
input | 사용자가 데이터를 입력하는 요소 | value:미리 입력된 값(데이터),  placeholder:사용자가 입력할 값(데이터)의 힌트, disabled: 입력 요소 비활성화 | checkbox, radio(1개만 선택 가능)


## 테이블 요소
요소 | 용도
--|--
table | 표 요소, 행(Row)과 열(Column)의 집합.
tr | 행(Row)을 지정하는 요소(Table Row)
td | 열(Column)을 지정하는 요소(Table Data)
label | input요소와 text를 세트로 합쳐준다
```html
  <table>
    <tr>
      <td>A</td><td>B</td>
    </tr>
    <tr>
      <td>C</td><td>D</td>
    </tr>
  </table>

  <label>
    <input type="checkbox" />
    Apple
  </label>
```

## 전역 속성
속성 | 용도
--|--
title | 요소의 정보나 설명을 지정
style | 요소에 적용할 스타일(CSS)을 지정
class | 요소를 지칭하는 중복 가능한 이름
id | 요소를 지칭하는 고유한 이름
data-이름 | 요소에 데이터를 지정
```html
    <div data-fruit-name="apple">사과</div>
  <div data-fruit-name="banana">바나나</div>
```
```javascript
const els = document.querySelectorAll('div')
els.forEach(el => {                  // Javascript에서는 -이 안됨 대문자로 대처
  console.log(el.dataset.fruitName)  // apple, banana 출력
})
```
