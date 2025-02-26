# HTML Chapter 2 학습 정리

안녕하세요! 이번에는 HTML 두 번째 수업에서 배운 내용을 정리해보겠다. HTML 문서의 기본 구조부터 다양한 요소들의 활용까지 살펴보자.

## 1. HTML 문서의 구조

### <!DOCTYPE> 선언
HTML 문서는 항상 문서 유형 선언(DOCTYPE)으로 시작한다. 이는 브라우저에게 어떤 버전의 HTML로 작성되었는지 알려준다.

```html
<!DOCTYPE html>
```

위 선언은 HTML5를 의미한다. HTML5 이전 버전들은 더 복잡한 DOCTYPE 선언을 사용했다.

### `<head>` 태그와 `<body>` 태그

HTML 문서는 크게 `<head>`와 `<body>` 두 부분으로 나뉜다:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>페이지 제목</title>
    <!-- 여기에 메타데이터, 스타일시트, 스크립트 등이 들어간다 -->
</head>
<body>
    <!-- 여기에 실제 화면에 표시될 내용이 들어간다 -->
</body>
</html>
```

- **`<head>`**: 문서의 메타데이터를 포함한다. 직접적으로 화면에 표시되지 않는 정보들이 여기에 포함된다.
  - `<title>`: 브라우저 탭에 표시되는 제목
  - `<meta>`: 문자 인코딩, 뷰포트 설정 등의 메타데이터
  - `<link>`: CSS 파일 연결
  - `<script>`: JavaScript 코드 또는 파일 연결
  - `<style>`: 인라인 CSS 스타일

- **`<body>`**: 실제로 웹 페이지에 표시될 모든 내용이 포함된다.

### 요소와 속성

HTML 요소는 시작 태그, 내용, 종료 태그로 구성된다:

```html
<태그명 속성="값">내용</태그명>
```

- **요소(Element)**: 시작 태그부터 종료 태그까지의 전체를 의미한다.
- **속성(Attribute)**: 요소에 대한 추가 정보를 제공한다.
  - 항상 시작 태그 내에 위치한다.
  - 이름과 값이 쌍으로 존재한다. (예: `name="value"`)
  - 값은 항상 따옴표로 묶는다.

예시:
```html
<a href="https://www.example.com" target="_blank">링크 텍스트</a>
```
여기서 `<a>`는 태그, `href`와 `target`은 속성, `"https://www.example.com"`과 `"_blank"`는 속성값, `링크 텍스트`는 내용이다.

## 2. 문서에 텍스트 표시

### `<p>` 태그 (문단 태그)
문단을 정의하는 데 사용된다. 자동으로 위아래에 여백이 생긴다.

```html
<p>이것은 하나의 문단이다. HTML에서 텍스트 내용을 구조화하는 가장 기본적인 방법이다.</p>
<p>이것은 다른 문단이다. 자동으로 위 문단과 간격이 생긴다.</p>
```

### `<pre>` 태그
Pre-formatted text(미리 서식을 지정한 텍스트)를 정의한다. 이 태그 내의 텍스트는 작성한 그대로의 공백과 줄바꿈이 유지된다.

```html
<pre>
  이 텍스트는   공백과
  줄바꿈이     그대로
    유지된다.
</pre>
```

### `<h>` 태그 (헤딩 태그)
제목을 정의하는 데 사용된다. `<h1>`부터 `<h6>`까지 여섯 단계가 있으며, `<h1>`이 가장 중요한(큰) 제목, `<h6>`이 가장 덜 중요한(작은) 제목이다.

```html
<h1>가장 중요한 제목</h1>
<h2>두 번째로 중요한 제목</h2>
<h3>세 번째로 중요한 제목</h3>
<h4>네 번째로 중요한 제목</h4>
<h5>다섯 번째로 중요한 제목</h5>
<h6>여섯 번째로 중요한 제목</h6>
```

### 주석
HTML에서 주석은 `<!-- -->`로 감싸며, 브라우저에 표시되지 않는다.

```html
<!-- 이것은 주석이다. 브라우저에 표시되지 않는다. -->
```

### `<hr>` 태그 (수평선)
주제의 분리를 나타내는 수평선을 삽입한다. 닫는 태그가 없는 빈 요소이다.

```html
<p>첫 번째 주제</p>
<hr>
<p>두 번째 주제</p>
```

### 특수문자
HTML에서는 특정 문자를 표현하기 위해 엔티티(entity) 코드를 사용한다.

- `&nbsp;`: 공백 (Non-breaking space)
- `&lt;`: 작다 기호 (<)
- `&gt;`: 크다 기호 (>)
- `&amp;`: 앰퍼샌드 (&)
- `&quot;`: 따옴표 (")
- `&copy;`: 저작권 기호 (©)
- `&reg;`: 등록 상표 기호 (®)

```html
<p>HTML에서 여러 개의&nbsp;&nbsp;&nbsp;공백을 표시하려면 &amp;nbsp;를 사용해야 한다.</p>
<p>&lt;div&gt; 태그는 HTML의 블록 요소이다.</p>
```

## 3. 문서에 리스트 작성하기

### 번호 없는 리스트 (`<ul>` 태그, `<li>` 태그)
순서가 중요하지 않은 항목들을 나열할 때 사용한다. 기본적으로, 각 항목 앞에 불릿(bullet)이 표시된다.

```html
<ul>
    <li>사과</li>
    <li>바나나</li>
    <li>오렌지</li>
</ul>
```

### 번호 있는 리스트 (`<ol>` 태그, `<li>` 태그)
순서가 중요한 항목들을 나열할 때 사용한다. 각 항목 앞에 번호가 자동으로 매겨진다.

```html
<ol>
    <li>첫 번째 단계</li>
    <li>두 번째 단계</li>
    <li>세 번째 단계</li>
</ol>
```

속성을 통해 번호 유형을 변경할 수 있다:
```html
<ol type="A"> <!-- A, B, C, ... -->
<ol type="a"> <!-- a, b, c, ... -->
<ol type="I"> <!-- I, II, III, ... -->
<ol type="i"> <!-- i, ii, iii, ... -->
<ol type="1"> <!-- 1, 2, 3, ... (기본값) -->
```

### 정의 리스트 (`<dl>` 태그, `<dt>` 태그, `<dd>` 태그)
용어와 그에 대한 설명을 나열할 때 사용한다.

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language의 약자로, 웹 페이지의 구조를 정의하는 언어이다.</dd>
    
    <dt>CSS</dt>
    <dd>Cascading Style Sheets의 약자로, 웹 페이지의 디자인과 레이아웃을 정의하는 언어이다.</dd>
    
    <dt>JavaScript</dt>
    <dd>웹 페이지에 상호작용성을 추가하는 프로그래밍 언어이다.</dd>
</dl>
```

- `<dl>`: Definition List (정의 리스트)
- `<dt>`: Definition Term (정의할 용어)
- `<dd>`: Definition Description (용어에 대한 설명)

## 4. 문서에 이미지 넣기

HTML에서 이미지를 삽입하려면 `<img>` 태그를 사용한다:

```html
<img src="image.jpg" alt="이미지 설명" width="300" height="200">
```

- `src`: 이미지 파일의 경로 (필수 속성)
- `alt`: 이미지를 표시할 수 없을 때 대체 텍스트 (필수 속성)
- `width`: 이미지의 너비 (픽셀 단위)
- `height`: 이미지의 높이 (픽셀 단위)

### 블록 요소와 인라인 요소

HTML 요소는 크게 블록 요소와 인라인 요소로 나뉜다:

#### 블록 요소 (Block Elements)
- 항상 새 줄에서 시작한다
- 가능한 전체 너비를 차지한다
- 위아래로 마진을 가질 수 있다
- 예: `<div>`, `<h1>` ~ `<h6>`, `<p>`, `<ul>`, `<ol>`, `<li>`, `<table>`, `<form>` 등

```html
<div>이것은 블록 요소이다.</div>
<p>이것도 블록 요소이다.</p>
```

#### 인라인 요소 (Inline Elements)
- 줄바꿈 없이 콘텐츠 흐름 내에 표시된다
- 필요한 만큼의 너비만 차지한다
- 위아래 마진을 직접 설정할 수 없다
- 예: `<span>`, `<a>`, `<img>`, `<strong>`, `<em>`, `<code>`, `<br>` 등

```html
이것은 <span>인라인 요소</span>가 포함된 텍스트이다.
이것은 <a href="#">링크</a>와 <strong>강조된 텍스트</strong>이다.
```

## 5. 문서에 링크 넣기

### `<a>` 태그와 `href` 속성
하이퍼링크를 생성하는 데 사용된다.

```html
<a href="https://www.example.com">Example 웹사이트 방문하기</a>
```

- `href`: 링크의 목적지 URL을 지정한다.

### `target` 속성
링크를 클릭했을 때 어디에서 열릴지 지정한다.

```html
<a href="https://www.example.com" target="_blank">새 탭에서 열기</a>
```

- `_self`: 현재 창에서 열기 (기본값)
- `_blank`: 새 탭/창에서 열기
- `_parent`: 부모 프레임에서 열기
- `_top`: 전체 창에서 열기

### `<a>` 태그와 `id` 속성
페이지 내에서 특정 위치로 이동하는 앵커 링크를 만들 때 사용한다.

1. 이동할 위치에 id 속성을 지정한다:
```html
<h2 id="section2">섹션 2</h2>
```

2. 해당 위치로 이동하는 링크를 만든다:
```html
<a href="#section2">섹션 2로 이동</a>
```

### 이메일 링크
`mailto:` 스키마를 사용하여 이메일 클라이언트를 열 수 있는 링크를 만든다.

```html
<a href="mailto:example@example.com">이메일 보내기</a>
```

제목, 본문 등을 미리 지정할 수도 있다:
```html
<a href="mailto:example@example.com?subject=문의사항&body=안녕하세요,">이메일 보내기</a>
```

### 다운로드 링크
`download` 속성을 사용하여 링크를 클릭했을 때 파일을 다운로드하도록 지정할 수 있다.

```html
<a href="document.pdf" download>PDF 다운로드</a>
```

파일명을 지정할 수도 있다:
```html
<a href="document.pdf" download="my-document.pdf">PDF 다운로드</a>
```

### 헤드 섹션에서 `<base>` 태그 사용
모든 상대 URL의 기본 URL과 기본 target 속성을 지정한다.

```html
<head>
    <base href="https://www.example.com/images/" target="_blank">
</head>
<body>
    <!-- 이 링크는 https://www.example.com/images/cat.jpg를 가리킨다 -->
    <a href="cat.jpg">고양이 이미지</a>
</body>
```

## 6. 문서에 테이블 만들기

테이블은 데이터를 행과 열로 구성하여 표시한다.

### 기본 테이블 구조: `<table>`, `<tr>`, `<td>` 태그

```html
<table>
    <tr>
        <td>1행 1열</td>
        <td>1행, 2열</td>
    </tr>
    <tr>
        <td>2행 1열</td>
        <td>2행 2열</td>
    </tr>
</table>
```

- `<table>`: 테이블 전체를 정의한다
- `<tr>`: Table Row, 테이블의 행을 정의한다
- `<td>`: Table Data, 테이블의 데이터 셀을 정의한다

### 테이블의 헤더, 본문, 경계, 제목

```html
<table border="1">
    <caption>학생 성적표</caption>
    <thead>
        <tr>
            <th>이름</th>
            <th>수학</th>
            <th>영어</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>홍길동</td>
            <td>90</td>
            <td>85</td>
        </tr>
        <tr>
            <td>김철수</td>
            <td>80</td>
            <td>95</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>평균</td>
            <td>85</td>
            <td>90</td>
        </tr>
    </tfoot>
</table>
```

- `border`: 테이블 테두리 두께를 지정한다 (HTML5에서는 CSS로 대체 권장)
- `<caption>`: 테이블의 제목을 정의한다
- `<thead>`: 테이블의 헤더 부분을 그룹화한다
- `<tbody>`: 테이블의 본문 부분을 그룹화한다
- `<tfoot>`: 테이블의 푸터 부분을 그룹화한다
- `<th>`: Table Header, 테이블의 헤더 셀을 정의한다 (일반적으로 굵게 표시되고 가운데 정렬됨)

### 테이블의 열과 행의 병합

#### 열 병합 (colspan)
```html
<tr>
    <td colspan="2">이 셀은 두 열을 차지한다</td>
</tr>
```

#### 행 병합 (rowspan)
```html
<tr>
    <td rowspan="2">이 셀은 두 행을 차지한다</td>
    <td>다른 셀</td>
</tr>
<tr>
    <td>다른 행의 셀</td>
</tr>
```

## 7. 문서에 멀티미디어 요소 추가하기

### `<video>` 태그와 `src` 속성
웹 페이지에 비디오를 삽입한다.

```html
<video src="movie.mp4" width="320" height="240" controls>
    브라우저가 video 태그를 지원하지 않는다.
</video>
```

여러 포맷의 비디오 제공:
```html
<video width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.webm" type="video/webm">
    브라우저가 video 태그를 지원하지 않는다.
</video>
```

주요 속성:
- `controls`: 재생, 일시정지, 볼륨 등의 컨트롤을 표시한다
- `autoplay`: 페이지 로드 시 자동 재생한다 (사용자 경험 고려 필요)
- `loop`: 비디오를 반복 재생한다
- `muted`: 음소거 상태로 재생한다
- `poster`: 비디오 로딩 중 표시할 이미지를 지정한다

### `<audio>` 태그와 `src` 속성
웹 페이지에 오디오를 삽입한다.

```html
<audio src="sound.mp3" controls>
    브라우저가 audio 태그를 지원하지 않는다.
</audio>
```

여러 포맷의 오디오 제공:
```html
<audio controls>
    <source src="sound.mp3" type="audio/mpeg">
    <source src="sound.ogg" type="audio/ogg">
    브라우저가 audio 태그를 지원하지 않는다.
</audio>
```

주요 속성:
- `controls`: 재생, 일시정지, 볼륨 등의 컨트롤을 표시한다
- `autoplay`: 페이지 로드 시 자동 재생한다 (브라우저 정책 고려 필요)
- `loop`: 오디오를 반복 재생한다
- `muted`: 음소거 상태로 재생한다

---

이상으로 HTML Chapter 2에서 배운 내용을 정리해보았다. HTML의 기본 요소들을 활용하여 다양한 콘텐츠를 구조화하고 표현하는 방법을 배웠다. 다음 챕터에서는 더 심화된 내용을 공부하겠다!
