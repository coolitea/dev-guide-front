# 프론트 엔드 개발 가이드

프론트 엔드 개발자를 위한 개발 가이드

## 개요

1. 페이지 구조 선택
   1. [ ] 멀티 페이지
   2. [x] 싱글 페이지 어플리케이션
2. (동적 제어) React 프레임워크 선택
   1. [ ] (대민 서비스에 추천) Next.js - 웹서버의 OS가 리눅스와 같은 환경이라 Node.js를 설치할 수 있는 경우 선택
   2. [ ] Create React App - 웹서버의 OS가 Node.js를 설치할 수 없는 SunOS와 같은 경우 선택
3. (디자인) CSS 프레임워크 선택
   1. [x] (대민 서비스에 추천) Ant Design
   2. [ ] React Bootstrap

## 페이지 구조 선택

### 싱글 페이지 어플리케이션(Single Page Application, 이하 SPA)란

SPA(Single Page Application)은 클라이언트 사이드 렌더링(Client Side Rendering) 방식으로 어플리케이션 생명 주기 중에서 단 한 번만 리소스(HTML, CSS, JavaScript) 를 로딩하고, 그 후에는 데이터를 받아올 때만 서버와 통신합니다. 정리하자면 첫 요청시 딱 한 페이지만 불러오고 페이지 이동시 기존 페이지의 내부를 수정해서 보여주는 방식입니다.

이를 사용자(클라이언트) 관점에서 다시 말하자면 최초 페이지를 로딩한 시점부터는 페이지 리로딩 없이 필요한 부분만 서버로 부터 받아서 화면을 갱신하는 것 입니다. 필요한 부분만 갱신하기 때문에 네이티브 앱에 가까운 자연스러운 페이지 이동과 사용자 경험(UX)을 제공할 수 있습니다.

Angular를 필두로 React, Vue.js 등 걸출한 프론트엔드 기술들이 나오면서 크게 유행하고 있습니다.

- SPA 장점
  - 자연스러운 사용자 경험(UX)
  - 필요한 리소스만 부분적으로 로딩(성능)
  - 서버의 탬플릿 연산을 클라이언트로 분산(성능)
  - 컴포넌트별 개발 용이(생산성)
  - 모바일 앱 개발을 염두에 둔다면 동일한 API를 사용하도록 설계 가능(생산성)

이와 같은 장점이 있지만 아래와 같은 단점도 존재합니다.

- SPA 단점
  - JavaScript 파일을 번들링해서 한 번에 받기 때문에 초기 구동 속도 느림(webpack 의 code splitting으로 해결 가능)
  - 검색엔진최적화(SEO)가 어려움 (서버 사이드 렌더링으로 해결 가능)
  - 보안 이슈 (프론트엔드에 비즈니스 로직 최소화)

> 참고 : 아하 프론트 개발기(1) <https://medium.com/aha-official/아하-프론트-개발기-1-SPA와-SSR의-장단점-그리고-nuxt-js-cafdc3ac2053>

위와 같은 SPA의 장단점을 참고하여 기존의 전통적인 웹사이트 같은 멀티 페이지로 구성할지 싱글 페이지로 구성할 지 선택합니다.

멀티 페이지의 작성은 전통적인 방식의 HTML, CSS, Javascript(이하 JS) 등을 사용하여 개발하게 될 것입니다.

아래는 싱글 페이지로 웹사이트를 구축하는 방법에 대한 가이드입니다.

싱글 페이지를 쉽게 개발하기 위해 React라는 Javascript 프레임워크를 사용하게 될 것입니다.

- React <https://ko.reactjs.org/> : 사용자 인터페이스를 만들기 위한 JavaScript 라이브러리
  - 시작하기 <https://ko.reactjs.org/docs/getting-started.html>

## (동적 제어) React 프레임워크 선택

화면 렌더링 방식에 따라 추천되는 리액트 프레임워크가 다릅니다.
각각의 프레임워크를 위한 내용은 각각의 문서에 설명하도록 하겠습니다.

클라이언트 사이드 렌더링으로 충분한 경우 Create React App가 추천됩니다.
단, 코드의 규모가 크고 검색엔진 최적화 등이 필수인 경우, 서버 사이드 렌더링을 추천합니다.

### 클라이언트 사이드 렌더링을 선택한 경우, Create React App

Create React App 시작하기 <https://facebook.github.io/create-react-app/docs/getting-started>

### 서버 사이드 렌더링을 선택한 경우, Next.js

Next.js 시작하기 <https://nextjs.org/docs>

## (반응형 디자인 & 컴포넌트) CSS 프레임워크

웹의 디자인은 기본적으로 CSS로 지정합니다.

### 인기 많은 부트스트랩을 리액트로 사용할 수 있도록 개발된 디자인 & 컴포넌트

대중적으로 많이 사용하는 CSS 프레임워크 중 하나는 부트스트랩(<https://getbootstrap.com/>)입니다.
부트스트랩을 React 문법을 사용하여 개발할 수 있도록 재빌드 된 라이브러리로 React Bootstrap과 reactstrpa이 있습니다.

- React Bootstrap <https://react-bootstrap.github.io/components/alerts/>
- reactstrap <https://reactstrap.github.io/components/alerts/>
  
### 처음부터 리액트를 위해 개발된 디자인 & 컴포넌트

- Ant Design <https://ant.design/components/button/> : 부트스트랩이 내부 시스템을 위한 디자인 느낌을 준다면, 앤트 디자인은 **기업용** 사이트의 느낌을 주는 세련되고 고급 기능이 가미된 컴포넌트입니다. 컴포넌트의 < > 버튼을 클릭하면 리액트 코드를 바로 확인할 수 있습니다.

## 개발 환경 구축

기본적으로 필요한 프로그램들은 아래와 같습니다.

### 필수 설치 프로그램

동일한 개발 환경을 갖추면, 팀으로 함께 일할 때 효율적입니다.

- Node.js <https://nodejs.org/ko/> : LTS 버전(v 10.15.3)을 다운로드 받아 설치합니다.
- Yarn <https://yarnpkg.com> : Stable 버전(v1.16.0)을 다운로드 받아 설치합니다.
- Git <https://git-scm.com/downloads> : Downloads의 Windows 버전을 선택하여 다운로드 받아 설치합니다.
- Visual Studio Code (이하 VS Code) <https://code.visualstudio.com/> : 코드 에디터를 설치합니다.  
- 크롬 브라우저 (개발자 도구)

### 선택 설치 프로그램

설치 하지 않아도 되지만 설치하면 개발 효율이 증가할 것입니다.

- Git GUI <https://git-scm.com/downloads/guis>
