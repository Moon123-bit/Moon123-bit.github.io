## 1. iframe

### iframe 태그란?
`<iframe>` 태그는 인라인 프레임(Inline Frame)의 약자로, 현재 HTML 문서 안에 다른 HTML 문서를 삽입할 수 있게 해주는 요소이다. 웹 페이지 내에 또 다른 웹 페이지를 넣는 창을 만들 수 있다.

```html
<iframe src="https://www.example.com" width="500" height="300" title="Example Website"></iframe>
```

주요 속성:
- `src`: 포함할 문서의 URL
- `width`, `height`: iframe의 너비와 높이
- `title`: 접근성을 위한 iframe의 제목
- `frameborder`: 테두리 표시 여부 (0: 없음, 1: 있음)
- `sandbox`: 보안 제한사항 설정

### iframe의 보안 문제
iframe은 편리하지만 몇 가지 보안 위험을 가지고 있다:

1. **클릭재킹(Clickjacking)**: 사용자가 보이는 페이지 위에 투명한 iframe을 놓아 의도치 않은 버튼을 클릭하게 하는 공격
2. **Cross-Site Scripting(XSS)**: 악성 스크립트가 포함된 페이지를 iframe으로 삽입하는 공격
3. **데이터 유출**: iframe 내 콘텐츠가 부모 페이지의 데이터에 접근할 수 있는 위험

보안 강화 방법:
```html
<iframe src="https://trusted-site.com" sandbox="allow-scripts allow-same-origin" referrerpolicy="no-referrer"></iframe>
```

## 2. \<div> 태그로 논리적인 구역 나누기

### \<div>와 \<span> 태그
- **div 태그**: 블록 레벨 요소로, 콘텐츠의 논리적 구역을 나눌 때 사용한다. 새 줄에서 시작하며 가능한 전체 너비를 차지한다.
- **span 태그**: 인라인 요소로, 텍스트의 일부분에만 스타일을 적용할 때 사용한다. 줄 바꿈 없이 텍스트 흐름 내에서 존재한다.

### \<div> 예제

```html
<div class="container">
  <div class="header">
    <h1>웹사이트 제목</h1>
  </div>
  
  <div class="content">
    <p>여기에 <span class="highlight">중요한</span> 내용이 들어간다.</p>
  </div>
  
  <div class="footer">
    <p>저작권 정보 © 2025</p>
  </div>
</div>
```

이 구조를 CSS와 함께 사용하면 웹페이지의 레이아웃을 구성할 수 있다:

```css
.container {
  width: 80%;
  margin: 0 auto;
}

.header {
  background-color: #f0f0f0;
  padding: 20px;
}

.content {
  min-height: 400px;
  padding: 15px;
}

.footer {
  background-color: #333;
  color: white;
  padding: 10px;
}

.highlight {
  color: red;
  font-weight: bold;
}
```

## 3. HTML 문서 구조화와 시맨틱 요소

### 시맨틱 웹
시맨틱 웹은 웹 콘텐츠에 의미를 부여하여 검색 엔진, 브라우저, 개발자가 콘텐츠의 의미를 더 잘 이해할 수 있게 하는 개념이다. 시맨틱 요소는 그 이름만으로도 콘텐츠의 역할과 의미를 명확히 한다.

### 시맨틱 요소
HTML5에서 추가된 주요 시맨틱 요소들:

- `<header>`: 페이지나 섹션의 헤더 영역
- `<nav>`: 네비게이션 링크 모음
- `<main>`: 페이지의 주요 콘텐츠
- `<article>`: 독립적인 콘텐츠 단위
- `<section>`: 주제별 콘텐츠 그룹화
- `<aside>`: 주요 콘텐츠와 간접적으로 연관된 콘텐츠
- `<footer>`: 페이지나 섹션의 바닥글 영역
- `<figure>`: 이미지, 다이어그램 등 자체적으로 참조될 수 있는 콘텐츠
- `<figcaption>`: figure 요소에 대한 설명

### 기존 웹과 시맨틱 웹의 차이

**기존 방식 (div만 사용)**:
```html
<div class="header">
  <h1>웹사이트 이름</h1>
  <div class="nav">
    <ul>
      <li><a href="#">홈</a></li>
      <li><a href="#">소개</a></li>
    </ul>
  </div>
</div>

<div class="content">
  <div class="article">
    <h2>글 제목</h2>
    <p>글 내용...</p>
  </div>
  <div class="sidebar">
    <h3>관련 링크</h3>
    <ul>
      <li><a href="#">링크1</a></li>
    </ul>
  </div>
</div>

<div class="footer">
  <p>Copyright 2025</p>
</div>
```

**시맨틱 요소 사용**:
```html
<header>
  <h1>웹사이트 이름</h1>
  <nav>
    <ul>
      <li><a href="#">홈</a></li>
      <li><a href="#">소개</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <h2>글 제목</h2>
    <p>글 내용...</p>
  </article>
  <aside>
    <h3>관련 링크</h3>
    <ul>
      <li><a href="#">링크1</a></li>
    </ul>
  </aside>
</main>

<footer>
  <p>Copyright 2025</p>
</footer>
```

시맨틱 태그를 사용하면:
1. 검색 엔진이 콘텐츠를 더 잘 이해하고 색인화할 수 있다 (SEO 향상)
2. 스크린 리더 등 보조 기술이 페이지 구조를 더 잘 해석할 수 있다 (접근성 향상)
3. 코드 가독성과 유지보수성이 향상된다
4. 개발자 간 협업이 용이해진다

### 시맨틱 태그와 CSS 함께 사용

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>시맨틱 웹 예제</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
    }
    
    header {
      background-color: #333;
      color: white;
      padding: 1rem;
    }
    
    nav ul {
      display: flex;
      list-style: none;
      padding: 0;
    }
    
    nav li {
      margin-right: 1rem;
    }
    
    nav a {
      color: white;
      text-decoration: none;
    }
    
    main {
      display: flex;
      margin: 1rem;
    }
    
    article {
      flex: 3;
      padding: 1rem;
    }
    
    aside {
      flex: 1;
      background-color: #f0f0f0;
      padding: 1rem;
    }
    
    footer {
      background-color: #333;
      color: white;
      text-align: center;
      padding: 1rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>블로그 제목</h1>
    <nav>
      <ul>
        <li><a href="#">홈</a></li>
        <li><a href="#">글 목록</a></li>
        <li><a href="#">소개</a></li>
        <li><a href="#">연락처</a></li>
      </ul>
    </nav>
  </header>
  
  <main>
    <article>
      <h2>HTML 시맨틱 태그의 중요성</h2>
      <p>시맨틱 태그는 웹 페이지의 구조를 명확하게 정의하는 데 도움을 준다...</p>
      <figure>
        <img src="semantic.jpg" alt="시맨틱 구조 다이어그램">
        <figcaption>HTML5 시맨틱 구조의 예</figcaption>
      </figure>
    </article>
    
    <aside>
      <h3>관련 글</h3>
      <ul>
        <li><a href="#">CSS 레이아웃 기초</a></li>
        <li><a href="#">웹 접근성 향상 방법</a></li>
      </ul>
    </aside>
  </main>
  
  <footer>
    <p>© 2025 내 블로그. 모든 권리 보유.</p>
  </footer>
</body>
</html>
```

## 4. HTML 입력 양식

### 입력 양식(form) 사용하기
HTML 폼은 사용자로부터 데이터를 수집하기 위한 인터페이스를 제공한다. 웹 페이지에서 사용자 입력을 받을 수 있는 다양한 컨트롤을 포함할 수 있다.

### 입력 양식(form)의 작동 방식
1. 클라이언트(브라우저)가 폼을 표시한다
2. 사용자가 데이터를 입력한다
3. 사용자가 제출 버튼을 클릭한다
4. 브라우저가 데이터를 웹 서버로 전송한다
5. 서버가 데이터를 처리하고 응답을 보낸다
6. 브라우저가 서버의 응답을 표시한다

### \<form> 태그로 HTML 양식 생성하기

```html
<form action="/submit-form" method="post">
  <!-- 여기에 입력 요소들이 들어간다 -->
  <input type="text" name="username" placeholder="사용자 이름">
  <input type="password" name="password" placeholder="비밀번호">
  <input type="submit" value="로그인">
</form>
```

주요 속성:
- `action`: 폼 데이터를 제출할 URL
- `method`: 데이터 전송 방식 (GET 또는 POST)
- `name`: 폼 식별자
- `target`: 응답을 표시할 위치
- `enctype`: 데이터 인코딩 방식

### GET 방식과 POST 방식

**GET 방식**:
- URL에 폼 데이터가 쿼리 문자열로 추가된다 (`?key1=value1&key2=value2`)
- 데이터 크기에 제한이 있다 (브라우저마다 다르지만 보통 2,048자)
- 북마크 가능하고 브라우저 히스토리에 남는다
- 민감한 정보에는 적합하지 않다
- 주로 검색, 필터링 등에 사용된다

```html
<form action="/search" method="get">
  <input type="text" name="query">
  <input type="submit" value="검색">
</form>
```

**POST 방식**:
- HTTP 요청 본문에 데이터가 포함된다
- 데이터 크기 제한이 없다
- 북마크할 수 없고 브라우저 히스토리에 남지 않는다
- 더 안전하며 민감한 정보 전송에 적합하다
- 주로 로그인, 회원가입, 데이터 추가/수정 등에 사용된다

```html
<form action="/login" method="post">
  <input type="text" name="username">
  <input type="password" name="password">
  <input type="submit" value="로그인">
</form>
```

## 5. 입력 요소

### \<input> 형식
`<input>` 태그는 사용자 입력을 받기 위한 가장 기본적인 요소이다. 다양한 속성을 통해 여러 형태의 입력을 받을 수 있다.

주요 속성:
- `type`: 입력 필드의 유형 (text, password, checkbox 등)
- `value`: 입력 필드의 초기값
- `name`: 폼 데이터 제출 시 사용되는 식별자
- `placeholder`: 입력 필드에 표시되는 힌트 텍스트
- `required`: 필수 입력 필드 지정
- `disabled`: 비활성화된 입력 필드
- `readonly`: 읽기 전용 입력 필드

### 텍스트 입력하기

**일반 텍스트**:
```html
<input type="text" name="username" placeholder="사용자 이름">
```

**비밀번호**:
```html
<input type="password" name="password" placeholder="비밀번호">
```

### 체크박스와 라디오 사용하기

**체크박스** (여러 항목 선택 가능):
```html
<p>관심사:</p>
<input type="checkbox" name="interest" value="html" id="html">
<label for="html">HTML</label><br>

<input type="checkbox" name="interest" value="css" id="css">
<label for="css">CSS</label><br>

<input type="checkbox" name="interest" value="js" id="js">
<label for="js">JavaScript</label>
```

**라디오 버튼** (하나의 항목만 선택 가능, 동일한 name 속성 필요):
```html
<p>성별:</p>
<input type="radio" name="gender" value="male" id="male">
<label for="male">남성</label><br>

<input type="radio" name="gender" value="female" id="female">
<label for="female">여성</label><br>

<input type="radio" name="gender" value="other" id="other">
<label for="other">기타</label>
```

### 제출 버튼과 초기화 버튼

```html
<form action="/submit" method="post">
  <input type="text" name="name" placeholder="이름">
  <input type="email" name="email" placeholder="이메일">
  
  <input type="submit" value="제출">
  <input type="reset" value="초기화">
</form>
```

### \<input type="button">과 \<button> 요소

**input 버튼**:
```html
<input type="button" value="클릭하세요" onclick="alert('안녕하세요!')">
```

**button 요소** (더 유연한 콘텐츠와 스타일링 가능):
```html
<button type="button" onclick="alert('안녕하세요!')">
  <img src="icon.png" alt=""> 클릭하세요
</button>
```

### \<select> 요소
드롭다운 목록을 만들 때 사용한다:

```html
<label for="country">국가:</label>
<select name="country" id="country">
  <option value="">선택하세요</option>
  <option value="kr">대한민국</option>
  <option value="us">미국</option>
  <option value="jp">일본</option>
  <option value="cn">중국</option>
</select>
```

그룹화한 옵션:
```html
<select name="car">
  <optgroup label="국산차">
    <option value="hyundai">현대</option>
    <option value="kia">기아</option>
  </optgroup>
  <optgroup label="수입차">
    <option value="bmw">BMW</option>
    <option value="benz">벤츠</option>
  </optgroup>
</select>
```

### \<datalist> 요소
자동완성 기능이 있는 입력 필드를 만들 때 사용한다:

```html
<label for="browser">브라우저:</label>
<input list="browsers" name="browser" id="browser">
<datalist id="browsers">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Safari">
  <option value="Edge">
</datalist>
```

### \<fieldset> 요소
관련된 폼 요소들을 그룹화할 때 사용한다:

```html
<form>
  <fieldset>
    <legend>개인 정보</legend>
    <label for="name">이름:</label>
    <input type="text" id="name" name="name"><br>
    
    <label for="email">이메일:</label>
    <input type="email" id="email" name="email">
  </fieldset>
  
  <fieldset>
    <legend>추가 정보</legend>
    <label for="comments">코멘트:</label>
    <textarea id="comments" name="comments"></textarea>
  </fieldset>
  
  <input type="submit" value="제출">
</form>
```

### \<label> 요소
입력 요소에 레이블을 연결하여 접근성을 향상시킨다:

```html
<label for="username">사용자 이름:</label>
<input type="text" id="username" name="username">
```

### 파일 업로드 버튼

```html
<form action="/upload" method="post" enctype="multipart/form-data">
  <label for="file">파일 선택:</label>
  <input type="file" id="file" name="file">
  <input type="submit" value="업로드">
</form>
```

여러 파일 업로드:
```html
<input type="file" multiple>
```

특정 파일 유형만 허용:
```html
<input type="file" accept=".jpg, .jpeg, .png">
```

## 6. HTML5에 추가된 입력 요소

### 추가된 속성
- `placeholder`: 입력 필드의 힌트 제공
- `required`: 필수 입력 필드 지정
- `autofocus`: 페이지 로드 시 자동 포커스
- `pattern`: 정규식을 이용한 유효성 검사
- `min`, `max`: 최소/최대값 설정
- `step`: 증가/감소 간격 설정

### 시간 입력 요소들

**날짜 선택**:
```html
<input type="date" name="birthday">
```

**날짜와 시간**:
```html
<input type="datetime-local" name="meeting">
```

**월 선택**:
```html
<input type="month" name="expiry">
```

**주 선택**:
```html
<input type="week" name="weeknum">
```

**시간 선택**:
```html
<input type="time" name="appointment">
```

### 색상 입력
색상 선택기를 표시한다:
```html
<input type="color" name="theme" value="#ff0000">
```

### 편리한 숫자 데이터 입력
숫자 입력 필드를 생성한다:
```html
<input type="number" name="quantity" min="1" max="10" step="1" value="1">
```

범위 슬라이더:
```html
<input type="range" name="volume" min="0" max="100" step="1" value="50">
<output for="volume">50</output>
```

### 이메일 타입
이메일 주소 입력을 위한 필드:
```html
<input type="email" name="email" placeholder="name@example.com" required>
```

### URL 타입
웹 주소 입력을 위한 필드:
```html
<input type="url" name="website" placeholder="https://example.com">
```

### 정규식(Pattern 속성)
입력 데이터의 형식을 검증한다:
```html
<input type="text" name="username" pattern="[a-zA-Z0-9]{5,}" title="5자 이상의 영문자와 숫자만 사용 가능합니다">
```

### 전화번호 타입
전화번호 입력을 위한 필드:
```html
<input type="tel" name="phone" pattern="[0-9]{3}-[0-9]{4}-[0-9]{4}" placeholder="010-1234-5678">
```

특히 시맨틱 태그의 사용은 단순히 디자인을 넘어 웹의 의미적 구조를 강화하는 중요한 발전이며, HTML5에서 추가된 다양한 입력 요소들은 사용자 경험을 크게 향상시킨다.

이러한 요소들을 적절히 활용하면 더 접근성 있고, 검색 엔진 친화적이며, 사용자 친화적인 웹 사이트를 구축할 수 있다.
