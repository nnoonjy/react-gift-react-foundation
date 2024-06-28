# react-gift-react-foundation
FE 카카오 선물하기 1주차 과제: React 기초

## Vite를 선택한 이유
갈수록 프로젝트의 규모나 수준이 높아짐에 따라, JavaScript를 기반으로 하는 도구들에게는 성능 병목 현상을 발생하였다.
CRA와는 다르게 Vite는 Go를 기반으로 작성된 ES build를 사용하며 종속성을 미리 묶어 처리함으로서
JS기반의 번들러보다 10~100배 빠른 속도로 종속성을 사전 번들링한다.
위와 같은 이유로 나는 CRA 대신 Vite를 선택하였다.

## 질문 1. webpack은 무엇이고 어떤 역할을 하고 있나요?
- Webpack은 자바스크립트 파일 및 관련 리소스들을 번들링하는 도구이다. 아래는 그것의 역할들이다.
  - 번들링: 여러 개의 자바스크립트 파일 및 CSS 파일, 이미지 등 여러 종류의 파일들을 하나의 번들로 묶어준다. 이는 네트워크 성능을 향상시키고 로딩 속도를 개선하는 데 도움을 준다.
  - 모듈 번들링: 모듈 시스템을 사용하여 import/export 구문을 이해하고, 필요한 모듈들을 정적 자산으로 변환한다.
  - 로더 처리: 다양한 파일 형식(JavaScript, TypeScript, CSS, 이미지 등)을 처리할 수 있는 로더를 통해 파일을 로드하고 변환한다.
  - 트랜스 파일링: 최신 자바스크립트 문법을 구형 브라우저에서도 동작할 수 있는 코드로 변환해준다. 예를 들어, Babel을 통해 ES6+ 코드를 ES5로 변환하는 작업을 수행할 수 있다.
  - 코드 최적화 및 압축: 코드의 크기를 줄이고 성능을 개선하기 위해 코드를 최적화하고 압축한다.
  - 환경 구성: 다양한 환경에서의 빌드 설정을 관리하고, 개발 서버를 제공하여 개발 작업을 용이하게 한다.
- Webpack은 모던 웹 개발에서 필수적인 도구로, React, Vue, Angular 등의 프레임워크와 함께 많이 사용됩니다.

## 질문 2. 브라우저는 어떻게 JSX 파일을 읽을 수 있나요?
JSX(JavaScript XML)는 React에서 사용되는 문법으로, 브라우저에서는 직접적으로 JSX 파일을 이해하고 해석할 수는 없으며, 다음과 같은 과정을 통해 브라우저에서 실행 가능한 자바스크립트 코드로 변환된다.
  1. 트랜스 파일링: 개발 과정에서 JSX 코드는 Babel과 같은 도구를 사용하여 일반적인 자바스크립트 코드로 변환된다. Babel은 JSX 문법을 React.createElement() 함수 호출로 변환하여 React가 이를 이해하고 처리할 수 있도록 한다.
  2. 번들링: 변환된 자바스크립트 파일들은 webpack이나 Parcel과 같은 번들러에 의해 번들링되어 하나의 파일로 묶여서 생성된다. 이 과정에서 CSS 파일, 이미지 등 다양한 자원들과 함께 번들링되어 최종적으로 브라우저가 로드할 수 있는 정적 자산으로 제공된다.
  3. 브라우저 로딩: 브라우저는 번들링된 자바스크립트 파일을 로드하고 실행한다. 이 파일에는 React 라이브러리와 JSX로 작성된 컴포넌트들이 포함되어 있으며, React는 이를 해석하여 가상 DOM을 구성하고 실제 DOM을 업데이트한다.


## 질문 3. React에서 상태 변화가 생겼을 때 어떻게 변화를 알아챌 수 있나요?
1. useState Hook: 함수형 컴포넌트에서 상태를 관리할 때 useState Hook을 사용한. 이 Hook은 상태 값과 상태를 업데이트하는 함수를 반환하며, 컴포넌트가 상태를 변경할 때마다 리렌더링을 트리거한다.
2. useEffect Hook: 상태 변화 후 추가적인 작업을 수행해야 할 때 useEffect Hook을 사용한다. useEffect는 컴포넌트가 렌더링 이후에 실행되며, 지정된 종속성이 변경될 때마다 실행된다.
3. Class Components: 함수형 컴포넌트 대신 클래스 기반 컴포넌트를 사용할 경우 setState 메서드를 사용하여 상태를 업데이트하고, 이후의 렌더링 사이클에서 변경된 상태를 처리한다.
