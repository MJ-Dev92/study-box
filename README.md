# 특수 문자 용어

기호 | 이름
--|--
` | Backtick, Grave
~ | Tilde
! | 느낌표
@ | At sign
\# | Sharp, Number sign
$ | Dollar sign
% | Percent sign
^ | Caret
& | Ampersand
\* | Asterisk
\- | Hyhen, Dash
_ | Underscore, Low dash
= | Equals sign
" | Quotation mark
' | Apostrophe
; | Semicolon
: | Colon
, | Comma
. | Dot
/ | Slash
\| | Vertical bar
\ | Backslash
() | 소괄호 
{} |  Brace
[] | Bracket
<> | 꺽쇠괄호 Angle Bracket

# Reset.css
- searching reset.css to Google  
- [reset](https://www.jsdelivr.com/package/npm/reset-css)  
- [reset](https://cdnjs.com/libraries/meyer-reset)  
- 사용 방법
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Document</title>
  <!-- 홈페이지에서 링크복사후 붙여넣어 사용 -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css" />
  <link rel="stylesheet" href="../CSS/main.css" />
</head>
<body>
  
</body>
</html>
```

# emmet 문법
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Document</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css" />
  <link rel="stylesheet" href="../CSS/main.css" />
</head>
<body>
  <!-- Emmet은 CSS 선택자를 활용해 사용하는 기능 -->
  <!-- * 기호는 곱하기, {}는 내용을 삽입, $는 순서대로 숫자 입력을 의미 -->
  <!-- CSS선택자 외 나머지 내용은 모두 Emmet에서만 지원 가능 -->
  <!-- div>ul>li*4{$} -->
    <div>
    <ul>
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
    </ul>
  </div>
</body>
</html>
```
