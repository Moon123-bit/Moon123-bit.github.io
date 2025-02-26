# HTML Chapter 1 학습 정리

안녕하세요! 오늘은 HTML 첫 번째 수업에서 배운 내용을 정리해보려고 합니다. 웹의 기초부터 HTML 문서 작성까지 다양한 내용을 배웠는데요, 하나씩 살펴보겠습니다.

## 1. 웹의 등장

### 인터넷(Internet)
- 전 세계의 컴퓨터들을 연결하는 거대한 네트워크 시스템
- 1960년대 미국 국방부에서 시작된 ARPANET이 그 시초
- 다양한 프로토콜(HTTP, FTP, SMTP 등)을 통해 정보를 주고받는 통신망

### WWW(World Wide Web)
- 팀 버너스 리(Tim Berners-Lee)가 1989년에 고안
- 인터넷 상에서 하이퍼텍스트 시스템을 기반으로 정보를 공유하는 방식
- 웹은 인터넷의 한 부분이며, 인터넷을 통해 접근 가능한 정보 공간
- 웹 브라우저를 통해 접근하는 웹 페이지, 문서, 멀티미디어 자원들의 집합

## 2. 웹의 기초 기술

### 하이퍼텍스트(Hypertext)
- 문서와 문서를 연결하는 링크 시스템
- 사용자가 한 문서에서 다른 문서로 쉽게 이동할 수 있게 해주는 기술
- HTML(Hypertext Markup Language)이 이를 구현하는 기본 언어

### WWW의 동작 원리
1. 사용자가 웹 브라우저에 URL 입력
2. 웹 브라우저가 DNS 서버에 도메인 이름 조회 요청
3. DNS가 IP 주소 반환
4. 웹 브라우저가 해당 IP 주소의 웹 서버에 HTTP 요청
5. 웹 서버가 요청을 처리하고 응답 반환
6. 웹 브라우저가 받은 HTML, CSS, JavaScript 등을 해석하여 화면에 렌더링

### 풀스택(Full Stack)
- **프론트엔드(Front-end)**
  - 사용자가 직접 보고 상호작용하는 부분
  - HTML, CSS, JavaScript를 이용해 구현
  - 웹 브라우저에서 실행됨

- **백엔드(Back-end)**
  - 서버 측에서 실행되는 부분
  - 데이터 처리, 비즈니스 로직, 데이터베이스 관리 등 담당
  - Java, Python, PHP, Node.js 등의 언어로 구현

### URL(Uniform Resource Locator)
- 웹에서 특정 자원의 위치를 나타내는 주소 체계
- 구성 요소: 프로토콜(http://, https://), 도메인(www.example.com), 경로(/path), 쿼리(?id=123) 등

### 서버의 종류와 역할

#### 웹 서버(Web Server)
- HTTP 프로토콜을 통해 클라이언트 요청에 응답
- 정적 콘텐츠(HTML, CSS, 이미지 등) 제공
- 대표적인 웹 서버: Apache, Nginx, IIS

#### 애플리케이션 서버(Application Server)
- 동적 콘텐츠를 생성하는 비즈니스 로직 처리
- 웹 서버와 데이터베이스 사이에서 중계 역할
- 대표적인 애플리케이션 서버: Tomcat, JBoss, WebLogic

#### 데이터베이스 서버(Database Server)
- 데이터를 저장, 관리, 제공
- 데이터의 무결성과 보안 담당
- 대표적인 데이터베이스: MySQL, PostgreSQL, Oracle, MongoDB

### HTTP(Hypertext Transfer Protocol)
- 웹에서 데이터를 주고받기 위한 프로토콜(통신 규약)
- 클라이언트-서버 모델 기반
- 주요 메소드: GET, POST, PUT, DELETE 등
- 상태 코드: 200(성공), 404(찾을 수 없음), 500(서버 오류) 등

### 클라이언트-서버 모델
- 클라이언트: 사용자 인터페이스를 제공하고 서버에 요청을 보내는 프로그램(웹 브라우저)
- 서버: 클라이언트의 요청을 처리하고 응답을 반환하는 컴퓨터 프로그램

## 3. HTML5 이해하기

### HTML이란?
- Hypertext Markup Language의 약자
- 웹 페이지의 구조와 내용을 정의하는 마크업 언어
- 태그(tag)를 사용하여 문서의 구조를 정의
- HTML5는 최신 버전으로 다양한 멀티미디어 지원 및 향상된 기능 제공

### 웹 페이지의 구성 요소
1. **HTML**: 웹 페이지의 구조와 내용 정의
   ```html
   <h1>제목입니다</h1>
   <p>단락입니다.</p>
   ```

2. **CSS**: 웹 페이지의 디자인과 레이아웃 담당
   ```css
   h1 {
     color: blue;
     font-size: 24px;
   }
   ```

3. **JavaScript**: 웹 페이지의 동적 기능과 상호작용 구현
   ```javascript
   document.getElementById("demo").onclick = function() {
     alert("버튼이 클릭되었습니다!");
   };
   ```

## 4. 크롬 개발자 도구 활용하기

크롬 개발자 도구는 웹 개발에 필수적인 도구로, 다음과 같은 기능을 제공합니다:

- **Elements 패널**: HTML 구조와 CSS 스타일 검사 및 수정
- **Console 패널**: JavaScript 코드 실행 및 오류 확인
- **Network 패널**: 네트워크 요청과 응답 모니터링
- **Sources 패널**: 소스 코드 디버깅
- **Application 패널**: 웹 스토리지, 캐시 등 관리

개발자 도구를 열려면:
- Windows/Linux: `F12` 또는 `Ctrl+Shift+I`
- Mac: `Cmd+Option+I`

## 5. VS Code로 HTML 문서 작성하기

### 메모장에서 HTML 작성
HTML은 단순한 텍스트 파일이므로 메모장에서도 작성 가능합니다:
1. 메모장 실행
2. HTML 코드 작성
3. `.html` 확장자로 저장
4. 웹 브라우저에서 파일 열기

```html
<!DOCTYPE html>
<html>
<head>
  <title>내 첫 HTML 페이지</title>
</head>
<body>
  <h1>안녕하세요!</h1>
  <p>HTML 공부 중입니다.</p>
</body>
</html>
```

### VS Code 설치 및 활용
VS Code는 더 강력한 기능을 제공하는 코드 에디터입니다:

1. [VS Code 공식 웹사이트](https://code.visualstudio.com/)에서 다운로드 및 설치
2. HTML 파일 생성 (`파일 > 새 파일` 후 `.html`로 저장)
3. `!` 입력 후 Tab 키를 눌러 HTML 기본 구조 자동 생성
4. 코드 작성
5. 저장 후 브라우저에서 열기

### VS Code 확장 프로그램 설치
HTML 개발에 유용한 확장 프로그램:

- **Live Server**: 실시간으로 변경 사항을 브라우저에 반영
- **HTML CSS Support**: HTML과 CSS 자동 완성 기능
- **Auto Rename Tag**: 여는 태그와 닫는 태그 동시 수정
- **Prettier**: 코드 자동 포맷팅
- **IntelliSense for CSS**: CSS 클래스 자동 완성

---

이상으로 HTML Chapter 1에서 배운 내용을 정리해보았습니다. 웹의 기본 개념부터 HTML 문서 작성까지 다양한 내용을 배웠는데요, 앞으로도 계속해서 HTML에 대해 공부하고 실습해보겠습니다!
