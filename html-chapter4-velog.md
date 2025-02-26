# HTML Chapter 4 - CSS 기초 총정리

이번에는 HTML Chapter 4에서 배운 CSS(Cascading Style Sheets)의 기본 개념과 활용법에 대해 정리해보려고 한다. HTML이 웹 페이지의 구조와 내용을 담당한다면, CSS는 웹 페이지의 시각적 표현과 레이아웃을 담당한다.

## 1. CSS의 개념

### CSS의 필요성

CSS가 없다면 웹 페이지는 단순한 텍스트와 기본 구조만 가지게 된다. CSS를 사용하면 다음과 같은 이점이 있다:

- 디자인과 내용의 분리 (관심사 분리)
- 일관된 스타일 적용으로 유지보수 용이
- 다양한 기기와 화면 크기에 대응 가능
- 로딩 속도 향상 (HTML 코드의 간소화)
- 다양한 시각적 효과 구현 가능

### CSS 문법

CSS는 선택자(selector)와 선언부(declaration block)로 구성된다:

```css
선택자 {
  속성: 값;
  속성: 값;
}
```

예시:
```css
h1 {
  color: blue;
  font-size: 20px;
}
```

여기서:
- `h1`은 선택자로, 스타일을 적용할 HTML 요소를 지정한다.
- `color`와 `font-size`는 속성(property)이다.
- `blue`와 `20px`은 해당 속성의 값(value)이다.
- 각 속성과 값은 콜론(`:`)으로 구분하고, 선언의 끝에는 세미콜론(`;`)을 사용한다.

### CSS의 위치

CSS 코드는 다음 세 가지 방법으로 HTML 문서에 적용할 수 있다:

1. **인라인 스타일**: HTML 요소의 `style` 속성에 직접 작성
2. **내부 스타일 시트**: HTML 문서 내의 `<head>` 섹션에 `<style>` 태그를 사용하여 작성
3. **외부 스타일 시트**: 별도의 CSS 파일을 생성하여 HTML 문서에 연결

## 2. 선택자(selector)

선택자는 스타일을 적용할 HTML 요소를 선택하는 패턴이다.

### jQuery 라이브러리와의 관계

CSS 선택자는 jQuery와 같은 JavaScript 라이브러리에서도 사용된다. jQuery는 CSS 선택자 문법을 활용하여 DOM 요소를 선택하고 조작한다:

```javascript
// CSS 선택자 ".myClass"를 사용하여 요소 선택
$(".myClass").css("color", "red");
```

### 타입 선택자

HTML 태그 이름을 직접 사용하는 가장 기본적인 선택자이다:

```css
h1 {
  color: blue;
}

p {
  font-size: 16px;
}
```

### 전체 선택자

애스터리스크(`*`) 기호를 사용하여 모든 요소를 선택한다:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

### 아이디 선택자

HTML 요소의 `id` 속성을 사용하여 선택한다. 해시(`#`) 기호를 사용하여 표시한다:

```css
#header {
  background-color: black;
  color: white;
}
```

HTML에서는 다음과 같이 사용한다:
```html
<div id="header">헤더 영역</div>
```

주의: 한 HTML 문서 내에서 같은 id는 한 번만 사용해야 한다.

### 클래스 선택자

HTML 요소의 `class` 속성을 사용하여 선택한다. 마침표(`.`) 기호를 사용하여 표시한다:

```css
.highlight {
  background-color: yellow;
}

.error {
  color: red;
}
```

HTML에서는 다음과 같이 사용한다:
```html
<p class="highlight">강조된 텍스트</p>
<p class="error">오류 메시지</p>
<p class="highlight error">강조된 오류 메시지</p>
```

한 요소에 여러 클래스를 공백으로 구분하여 적용할 수 있다.

### 선택자 그룹

쉼표를 사용하여 여러 선택자에 동일한 스타일을 적용할 수 있다:

```css
h1, h2, h3 {
  font-family: Arial, sans-serif;
}

.warning, .error, .alert {
  font-weight: bold;
}
```

### 자손과 자식 선택자

**자손 선택자(공백)**: 특정 요소의 모든 하위 요소(자식, 손자 등)를 선택한다.
```css
div p {
  color: blue;
}
```
위 코드는 `div` 안에 있는 모든 `p` 요소를 선택한다(깊이에 상관없이).

**자식 선택자(>)**: 특정 요소의 직접적인 자식 요소만 선택한다.
```css
div > p {
  color: red;
}
```
위 코드는 `div`의 직접적인 자식인 `p` 요소만 선택한다.

### 의사 클래스(Pseudo-class)

의사 클래스는 요소의 특별한 상태를 선택하기 위해 사용된다. 콜론(`:`)으로 표기한다:

```css
/* 방문하지 않은 링크 */
a:link {
  color: blue;
}

/* 방문한 링크 */
a:visited {
  color: purple;
}

/* 마우스를 올렸을 때 */
a:hover {
  color: red;
}

/* 클릭했을 때 */
a:active {
  color: green;
}

/* 첫 번째 자식 요소 */
li:first-child {
  font-weight: bold;
}

/* 마지막 자식 요소 */
li:last-child {
  border-bottom: none;
}

/* 홀수 번째 요소 */
tr:nth-child(odd) {
  background-color: #f2f2f2;
}
```

## 3. CSS를 추가하는 방법

### 내부 스타일 시트

HTML 문서의 `<head>` 섹션 내에 `<style>` 태그를 사용하여 CSS를 정의한다:

```html
<!DOCTYPE html>
<html>
<head>
  <title>내부 스타일 시트 예제</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }
    h1 {
      color: navy;
    }
    p {
      line-height: 1.5;
    }
  </style>
</head>
<body>
  <h1>제목</h1>
  <p>본문 내용...</p>
</body>
</html>
```

장점: 추가 파일 없이 HTML 문서에 스타일을 적용할 수 있다.
단점: 여러 페이지에서 동일한 스타일을 사용할 경우 중복이 발생한다.

### 외부 스타일 시트

별도의 CSS 파일(`.css` 확장자)을 만들고, HTML 문서의 `<head>` 섹션에서 `<link>` 태그를 사용하여 연결한다:

```css
/* styles.css 파일 */
body {
  font-family: Arial, sans-serif;
  margin: 20px;
}
h1 {
  color: navy;
}
p {
  line-height: 1.5;
}
```

```html
<!DOCTYPE html>
<html>
<head>
  <title>외부 스타일 시트 예제</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <h1>제목</h1>
  <p>본문 내용...</p>
</body>
</html>
```

장점: 
- 여러 HTML 페이지에서 동일한 스타일을 재사용할 수 있다.
- HTML과 CSS를 분리하여 유지보수가 쉽다.
- 브라우저가 CSS 파일을 캐싱하여 로딩 속도가 향상될 수 있다.

### 인라인 스타일

HTML 요소의 `style` 속성을 사용하여 직접 스타일을 적용한다:

```html
<h1 style="color: blue; font-size: 24px;">인라인 스타일 제목</h1>
<p style="color: gray; margin-left: 20px;">인라인 스타일 문단</p>
```

장점: 특정 요소에 빠르게 스타일을 적용할 수 있다.
단점: 
- HTML과 CSS가 혼합되어 유지보수가 어렵다.
- 재사용이 불가능하다.
- 스타일의 우선순위가 높아 덮어쓰기가 어렵다.

### 다중 스타일 시트

여러 스타일 시트를 결합하여 사용할 수 있다:

```html
<head>
  <link rel="stylesheet" href="base.css">
  <link rel="stylesheet" href="layout.css">
  <style>
    /* 추가 스타일 */
    .custom {
      border: 1px solid black;
    }
  </style>
</head>
```

스타일 충돌 시 나중에 선언된 스타일이 적용된다(캐스케이딩 원칙).

### 많이 사용되는 속성들

```css
/* 텍스트 관련 */
p {
  font-size: 16px;          /* 글자 크기 */
  color: #333;              /* 글자 색상 */
  font-family: Arial, sans-serif; /* 글꼴 */
  text-align: center;       /* 텍스트 정렬 */
  line-height: 1.5;         /* 줄 간격 */
}

/* 여백 관련 */
div {
  margin: 10px;             /* 바깥 여백 */
  padding: 15px;            /* 안쪽 여백 */
}

/* 테두리 관련 */
.box {
  border: 1px solid black;  /* 테두리 */
  border-radius: 5px;       /* 모서리 둥글게 */
}

/* 배경 관련 */
body {
  background-color: #f0f0f0; /* 배경색 */
  background-image: url('bg.jpg'); /* 배경 이미지 */
}

/* 레이아웃 관련 */
.container {
  width: 80%;              /* 너비 */
  max-width: 1200px;       /* 최대 너비 */
  height: 400px;           /* 높이 */
  display: flex;           /* 플렉스 박스 레이아웃 */
  position: relative;      /* 위치 지정 방법 */
}
```

## 4. 색상

CSS에서는 여러 방법으로 색상을 지정할 수 있다.

### 16진수로 색상 표현하기

16진수(HEX) 색상 코드는 파운드 기호(`#`)로 시작하고, 빨강(R), 초록(G), 파랑(B) 값을 16진수로 표현한다:

```css
p {
  color: #FF0000;       /* 빨강 */
  background-color: #00FF00;  /* 초록 */
}

h1 {
  color: #0000FF;       /* 파랑 */
  border-color: #FF00FF;    /* 자홍색 */
}
```

축약형으로도 사용할 수 있다(각 색상 쌍이 동일한 경우):
```css
.red {
  color: #F00;  /* #FF0000과 동일 */
}
```

### 이름으로 색상 표현하기

CSS에는 약 140개의 이름이 지정된 색상이 있다:

```css
h1 {
  color: red;
}

p {
  color: navy;
}

.warning {
  background-color: yellow;
}

.info {
  background-color: skyblue;
}
```

주요 기본 색상: 
- `black`, `white`, `red`, `green`, `blue`
- `yellow`, `cyan`, `magenta`
- `gray`, `lightgray`, `darkgray`

### RGB값으로 색상 표현하기

RGB 함수를 사용하여 색상을 표현할 수 있다:

```css
p {
  color: rgb(255, 0, 0);  /* 빨강 */
}

h2 {
  color: rgb(0, 128, 0);  /* 초록 */
}

.transparent {
  background-color: rgba(0, 0, 255, 0.5);  /* 반투명 파랑 */
}
```

`rgba()`는 알파(투명도) 값을 추가로 지정할 수 있다. 알파 값은 0(완전 투명)부터 1(완전 불투명) 사이의 값을 가진다.

### 원하는 색상을 찾는 방법

색상을 선택하는 몇 가지 도구:

1. **색상 피커 도구**: 대부분의 코드 에디터와 그래픽 도구에 내장되어 있다.
2. **웹 기반 색상 도구**:
   - Adobe Color (https://color.adobe.com)
   - Coolors (https://coolors.co)
   - Paletton (https://paletton.com)
3. **색상 팔레트 생성기**:
   - Material Design Color Tool
   - Flat UI Colors

색상 조합 팁:
- 브랜드 색상을 주요 색상으로 사용한다.
- 색상 대비를 고려하여 가독성을 확보한다.
- 너무 많은 색상을 사용하지 않는다 (3-5개 정도가 적당).
- 의미를 가진 색상을 일관되게 사용한다 (예: 빨강=오류, 초록=성공).

## 5. 폰트

### 폰트의 종류

CSS에서는 다양한 폰트 유형을 사용할 수 있다:

1. **세리프(Serif)**: 글자 끝에 작은 장식이 있는 폰트
   - 예: Times New Roman, Georgia, Garamond

2. **산세리프(Sans-serif)**: 장식이 없는 깔끔한 폰트
   - 예: Arial, Helvetica, Verdana, Roboto

3. **모노스페이스(Monospace)**: 모든 글자의 너비가 동일한 폰트
   - 예: Courier New, Consolas, Monaco

4. **필기체(Cursive)**: 손글씨 스타일의 폰트
   - 예: Comic Sans MS, Brush Script

5. **장식체(Fantasy)**: 장식적이고 독특한 폰트
   - 예: Impact, Papyrus

### Serif와 Sans-serif의 차이

**세리프(Serif)**: 
- 글자 끝에 작은 장식(세리프)이 있다.
- 전통적이고 격식 있는 느낌을 준다.
- 인쇄물에서 가독성이 좋다.
- 주로 본문보다는 제목에 사용된다.

**산세리프(Sans-serif)**:
- 'Sans'는 프랑스어로 '없다'는 의미로, 세리프(장식)가 없는 폰트를 의미한다.
- 현대적이고 깔끔한 느낌을 준다.
- 화면에서 가독성이 좋다.
- 웹 디자인에서 많이 사용된다.

### 폰트 패밀리

`font-family` 속성을 사용하여 폰트를 지정한다:

```css
body {
  font-family: 'Helvetica Neue', Arial, sans-serif;
}

h1 {
  font-family: Georgia, Times, 'Times New Roman', serif;
}

code {
  font-family: 'Courier New', monospace;
}
```

여러 폰트를 쉼표로 구분하여 나열하면, 브라우저는 첫 번째 폰트부터 사용 가능한 폰트를 적용한다. 마지막에 일반적인 폰트 계열(serif, sans-serif 등)을 지정하는 것이 좋다.

**웹 폰트 사용하기**:

Google Fonts와 같은 서비스를 통해 웹 폰트를 사용할 수 있다:

```html
<head>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Roboto', sans-serif;
    }
  </style>
</head>
```

또는 `@font-face` 규칙을 사용하여 직접 폰트 파일을 호스팅할 수 있다:

```css
@font-face {
  font-family: 'MyCustomFont';
  src: url('fonts/mycustomfont.woff2') format('woff2'),
       url('fonts/mycustomfont.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}

body {
  font-family: 'MyCustomFont', sans-serif;
}
```

### 폰트 크기 설정

`font-size` 속성을 사용하여 폰트 크기를 지정한다:

```css
body {
  font-size: 16px;  /* 픽셀 단위 */
}

h1 {
  font-size: 2em;   /* 부모 요소의 2배 크기 */
}

h2 {
  font-size: 1.5rem;  /* 루트 요소(html)의 1.5배 크기 */
}

small {
  font-size: 80%;   /* 부모 요소의 80% 크기 */
}
```

**폰트 크기 단위**:
- `px`: 픽셀, 고정된 크기
- `em`: 부모 요소의 폰트 크기에 대한 배수
- `rem`: 루트 요소(html)의 폰트 크기에 대한 배수
- `%`: 부모 요소의 폰트 크기에 대한 비율
- `vw`: 뷰포트 너비의 1/100
- `vh`: 뷰포트 높이의 1/100

## 6. 텍스트 스타일 설정

### 텍스트 색상과 텍스트 정렬

```css
p {
  color: #333;             /* 텍스트 색상 */
  text-align: center;      /* 가운데 정렬 */
}

.right-aligned {
  text-align: right;       /* 오른쪽 정렬 */
}

.justified {
  text-align: justify;     /* 양쪽 정렬 */
}
```

`text-align` 속성 값:
- `left`: 왼쪽 정렬 (기본값)
- `right`: 오른쪽 정렬
- `center`: 가운데 정렬
- `justify`: 양쪽 정렬 (마지막 줄 제외)

### 텍스트 장식

`text-decoration` 속성을 사용하여 텍스트에 선을 추가하거나 제거할 수 있다:

```css
a {
  text-decoration: none;   /* 밑줄 제거 */
}

h2 {
  text-decoration: underline;  /* 밑줄 */
}

.important {
  text-decoration: underline red wavy;  /* 빨간색 물결 밑줄 */
}

.strike {
  text-decoration: line-through;  /* 취소선 */
}
```

`text-decoration` 속성 값:
- `none`: 장식 없음
- `underline`: 밑줄
- `overline`: 윗줄
- `line-through`: 취소선

### 텍스트 변환

`text-transform` 속성을 사용하여 텍스트의 대소문자를 변환할 수 있다:

```css
.uppercase {
  text-transform: uppercase;  /* 모두 대문자 */
}

.lowercase {
  text-transform: lowercase;  /* 모두 소문자 */
}

.capitalize {
  text-transform: capitalize;  /* 각 단어의 첫 글자만 대문자 */
}
```

### 텍스트 그림자

`text-shadow` 속성을 사용하여 텍스트에 그림자 효과를 추가할 수 있다:

```css
h1 {
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.glow {
  text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #e60073;
}

.multi-shadow {
  text-shadow: 1px 1px 2px black, 0 0 1em blue, 0 0 0.2em blue;
}
```

`text-shadow` 속성의 값:
- 첫 번째 값: 수평 오프셋 (양수는 오른쪽, 음수는 왼쪽)
- 두 번째 값: 수직 오프셋 (양수는 아래쪽, 음수는 위쪽)
- 세 번째 값: 흐림 반경 (blur radius)
- 네 번째 값: 그림자 색상

### Word Wrapping

`word-wrap` 속성(새 이름: `overflow-wrap`)을 사용하여 긴 단어가 컨테이너를 벗어나지 않도록 할 수 있다:

```css
p {
  word-wrap: break-word;
}
```

관련 속성들:
- `white-space`: 공백과 줄바꿈 처리 방법 지정
  ```css
  pre {
    white-space: pre-wrap;  /* 줄바꿈 유지하고 자동 줄바꿈 */
  }
  ```

- `word-break`: 단어 내에서 줄바꿈 허용 여부 지정
  ```css
  .break-all {
    word-break: break-all;  /* 모든 문자에서 줄바꿈 가능 */
  }
  ```

### 다중 컬럼

CSS3의 다중 컬럼 레이아웃을 사용하여 신문 형식의 다단 레이아웃을 만들 수 있다:

```css
.multi-column {
  column-count: 3;         /* 컬럼 개수 */
  column-gap: 40px;        /* 컬럼 간격 */
  column-rule: 1px solid #ddd;  /* 컬럼 사이의 선 */
}

h2 {
  column-span: all;        /* 제목이 모든 컬럼에 걸쳐 표시 */
}
```

주요 속성:
- `column-count`: 컬럼 개수
- `column-width`: 최소 컬럼 너비 (브라우저가 컬럼 개수 자동 조정)
- `columns`: 컬럼 개수와 너비를 한 번에 지정 (`columns: 3 200px;`)
- `column-gap`: 컬럼 사이의 간격
- `column-rule`: 컬럼 사이의 선 (border와 유사한 문법)
- `column-span`: 요소가 모든 컬럼에 걸쳐 표시될지 여부

## 마무리

이번 Chapter 4에서는 CSS의 기본 개념부터 실제 적용 방법, 그리고 텍스트와 폰트 스타일링에 대해 알아보았다. CSS는 웹 디자인의 핵심 요소로, 이러한 기초 지식을 바탕으로 더 복잡한 레이아웃과 애니메이션 등을 구현할 수 있다.

특히 선택자의 활용과 다양한 속성들을 잘 이해하고 활용하면, HTML 문서의 구조는 그대로 유지하면서도 다양한 디자인을 적용할 수 있다. 실제 프로젝트에서는 외부 스타일 시트를 주로 사용하며, 필요에 따라 내부 스타일이나 인라인 스타일을 보조적으로 활용하는 방식을 권장한다.

다음 장에서는 CSS를 활용한 레이아웃 구성과 반응형 디자인에 대해 더 자세히 알아볼 예정이다.
