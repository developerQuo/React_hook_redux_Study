# React_hook_redux_Study

<h2>React</h2>   

1. 첫번째 원칙. 모든 React 컴포넌트는 자신의 props를 다룰 때 반드시 순수 함수처럼 동작해야 한다. 순수 함수란 매개변수를 변화시키지 않는다.

2. 두번째 원칙. 단방향으로 데이터가 흐른다. 해당 방향의 컴포넌트에만 영향을 미친다.
   
+ 단위: element < component   
   
+ JSX: JS를 확장하여 XML 기능 또한 가지고 있는 문법. UI를 표현.   
   
+ Babel: JS 컴파일러로 JSX를 React.createElement() 호출로 컴파일.     
   
React DOM: 내부에 모든 element를 관리.   
		    render() 함수를 통해 root Dom node에 렌더링하고, element와 root node를 매개변수로 전달해야 한다.   
React element: 불변객체. 변경하지않고 새로운 것을 쌓아야 한다.   
```
const element = <div />;
```   
   
React component: React가 사용자정의 component를 발견하면 JSX attr와 children을 단일객체로 전달(props).   
   
```
const element = <Welcome name="Sara" />;
```
+ function type: props 사용가능.
+ class type: props, state 사용가능.   
   
state & props: 상위 component의 state => 하위 component의 props (top-down, 단방향식)
+ 모든 React component의 매개변수(props)는 수정해서는 안된다.

<h3>reactjs.org doc</h3>
주요 개념
+ JSX: JS문법에 마크업을 담은 형태. JSX는 컴파일 후 JS객체로 인식됨. React는 이들을 React Element로 변환하여, 이 객체들을 관리한다.
+ React Element Rendering: React Element는 불변객체로 이를 변경할 수 없다. UI 업데이트를 위해 새로운 엘리먼트를 생성하고 ReactDom에 전달해야 한다.
+ Component & Props
	** component는 다른 componenet의 함께 출력할 수 있다. 또한 재사용 가능하다.
	** props는 read only이다. 즉, props를 다룰 때에는 순수함수처럼 동작하도록 해야한다.
+ State & Lifecycle
	** state는 component에 의해 제어된다.
	** 동일한 DOM 노드에서 component를 렌더링할 경우, 해당 component의 단일 인스턴스만 사용하므로써 life cycle 기능을 사용할 수 있게 한다.
+ component rendering과 mounting 차이
	** mounting: Component가 처음 DOM에 rendering
	** rendering: 
+ 조건부 렌더링
	** if else
	** 조건문 ? true일 때 : false일 때
	** component의 null 반환
+ list와 key
	** es6와 동일하게 "새로운 배열 = 기존배열.map((item) => logic)"로 표현가능
	** 이 때, element list라면 key 값을 포함시켜주어야 한다. element의 unique를 지원. 단, 형제 사이에서만 unique하면된다.

+ form
	** 기존 html폼은 submit를 하면 새로운 페이지로 이동.
	** controlled component: 폼의 값을 제어할 수 있도록 state를 사용. 이 state는 신뢰 가능한 단일 출처가 됨.

+ state 끌어올리기
	** state를 컴포넌트 간에 공통으로 사용하기 위해서는 공통 부모로 state를 끌어올리고, state와 setState()를 prop으로 건네받아 사용할 수 있다.

+ 합성 vs 상속
	** 컴포넌트의 prop으로 전달할 수 있는 것에는 제한이 없다.
	** 특수화: 더 구체적인 컴포넌트가 일반적인 컴포넌트를 구현.
	** 합성하여 사용하는 것을 권장.

+ React로 생각하기
	** 단일 책임 원칙: 하나의 컴포넌트 한 가지 일을 할 수 있도록 -> 컴포넌트가 커지면 작은 하위 컴포넌트로 분리해야 한다.
	** 앱을 만들 때, 정적인 작업과 동적인 작업을 나눠서 생각해보기 -> state는 동적인 작업을 할 때, 필요하다는 사실을 고민해보기
	** 중복배제 원칙: state는 최소한으로 사용하고, 가능한한 계산하여 사용하기
	** state가 있어야할 컴포넌트 찾기
	1. state 관련 컴포넌트 찾기
	2. 공통으로 사용할 수 있는 컴포넌트 찾기 (상위 컴포넌트)
	3. 공통 컴포넌트에 위치시키거나, 만약 없다면 공통 컴포넌트 만들어서 추가

고급안내서 
+ 접근성 
	++ 프로그래밍적으로 포커스 관리하기
		** 마우스 이벤트 사용자에 너무 취중하면 키보드 사용에 편의성을 전혀 고려 못할 수 있다.
	++ 더 복잡한 위젯
		** HTML에 맞게 코딩하면 접근성을 쉽게 지원할 수 있다.

+ 코드 분할
	** React.lazy: import를 사용해서 동적으로 컴포넌트를 렌더링 가능. Suspense 컴포넌트 하위에 위치하며, lazy 컴포넌트가 로드 되는 동안 Suspense 컴포넌트는 fallback prop을 렌더링

+ Context
	** 상위 컴포넌트에서 하위 컴포넌트로 깊숙히 전달. 원하는 데이터를 일일이 전달할 필요가 없음.
	** redux 와 기능이 유사.

+ Error Boundary
	** js 에러가 app을 중단시키는 것을 방지한다. js 에러 발생 -> error 기록 -> fallback UI 반환

고급안내서 중단. (api 참고서, hook 완료하고) Ref 전달하기 부터 시작

API 참고서
+ React
	** 컴포넌트: UI를 독립적으로, 재사용 가능하게 만듦.
	** Suspense: 다른작업을 기다릴 수 있음. lazy와 단짝.
	** memo: 렌더링 결과를 memorizing하여 재사용한다. prop의 변화가 있을 경우만 다시 렌더링한다. 성능 최적화를 목적으로 사용.

+ React.Component
	** setState: 갱신된 state를 사용해야한다고 요청. 즉각적으로 반영되지는 않을 수 있음. setState의 즉각적인 갱신효과를 보고싶다면 콜백함수로 구현.
	** props: 컴포넌트를 호출한 곳에서 정의한 props를 포함. props.children은 JSX 표현으로 된 자식태그로 정의되는 경우가 많음.
	** state: 시간이 지남에 따라 값이 변화할 수 있는 특정 컴포넌트에 한정해서 사용되는 데이터. state를 직접변경하면 안되고 setState() 함수를 활용해야한다.  immutable data로 취급.

+ ReactDOM
	** render(): 전달받은 React 엘리먼트를 container DOM에 렌더링. 이미 React 엘리먼트가 렌더링되어 있다면 container를 나두고 container 하위노드만 수정.

+ DOM 엘리먼트
	** React는 독립적인 DOM 시스템을 구현.
	** HTML과의 attribute 차이
		1. className: CSS class 사용 (권장)
		2. style: 캐멀케이스로 CSS 스타일링 (보조 사용)

+ 합성 이벤트
	** 이벤트를 동일하게 처리하기 위해 SyntheticEvent 객체를 전달받음.
	** onFocus: 엘리먼트(또는 자식)가 포커스될 때 호출.
	** onBlur: 엘리먼트에서 포커스가 사라졌을 때 호출.

+ React 기술 용어 모음
	** SPA(single-page application): 하나의 HTML페이지와 애플리케이션 실행에 사용되는 모든 자원을 로드. 페이지의 상호작용으로 페이지가 다시 로드되진 않는다.  기존 웹사이트와 함께 사용이 가능.
	** 컴파일러: 코드를 변환하여 다른형식으로 코드를 반환. 일반적으로 구형 브라이저에서 최신 문법을 사용할 수 있도록 도와준다. ex) Babel
	** 번들러: 분리된 JS와 CSS 모듈코드를 브라우저에 최적화된 여러 개의 파일로 결합. ex) Webpack

패키지 관리자부터


<h2>React hook</h2>
+ useState:

+ useEffect:

	** side-effect: 

+ useMemo: memoization된 value를 반환한다. -> 특정 결과값 재사용.   

	- 함수와 의존성 값을 배열로 전달하면 의존성 값이 변경되었을 경우에만 memoization 값을 계산한다. 
<pre><code>const memoizedValue = 
useMemo(
  () => computeExpensiveValue(a, b), [a, b]
);
</code></pre>   

	** rendering 중에만 실행된다.   

	** memoization: 컴퓨터 프로그램이 동일한 계산을 반복할 때, 이전에 계산된 값을 메모리에 저장하여 반복수행을 줄인다.   
		-> 연산속도가 빨라진다.

+ useCallback: memoization된 callback을 반환한다. -> 특정 함수 재사용.   
	- 함수와 의존성 값을 배열로 전달하면 의존성 값이 변경되었을 경우에만 memoization 함수를 실행한다.
<pre><code>const memoizedCallback =
useCallback(
  () => {
    doSomething(a,b);
  }, [a, b],
);
</code></pre>   

	** state가 바뀌면 새로 함수를 실행한다.

	** callback: 다시부른다??


+ useForm: 


<h2>Electron</h2>
Node.js 기반으로 desktop application을 만드는 platform.

compile 순서:
1. 도구 설치
 - npm add electron electron-builder --dev
 - npm add concurrently wait-on cross-env --dev
 - npm install electron-packager --dev
```
concurrently: 여러 명령어를 병렬적으로 실행
wait-on: 특정 포트, 파일, HTTP 자원 등이 활성화될 때까지 기다려주는 크로스 플랫폼 명령어
cross-env: 프로그램을 CLI 환경에서 실행시킬 때, os에 관계없이 환경변수를 설정
electron-packager: 실행가능한 파일로 변환
```
2. Electron 실행 코드 작성
 - electron.ts에 실행코드를 작성하고 app의 index 페이지를 로드한다.
3. package.json 파일 수정
 - main: 시작점을 electron.ts로 변경
 - start:"concurrently \"cross-env BROWSER=none npm craco start \" \"wait-on http://localhost:3000 && electron .\" "
```
start: 클라이언트 서버와 electron을 실행한다.
```
4. 실행파일로 변환
 - window 64bit: electron-packager . --asar --platform=win32 --arch=x64
 - linux 64bit: electron-packager . --asar
```
window 64bit: 스크립트명령어 소스경로 소스암호화옵션 os선택옵션 os버전선택옵션
linux 64bit: 스크립트명령어 소스경로 소스암호화옵션 (별도로 옵션을 넣지않으면 본인의 pc사양에 맞춰서 똑같이 세팅된다.)
```

<h2>craco</h2>
+ create-react-app의 환경설정을 도와주는 모듈.
	- 환경설정을 eject 없이 커스터마이징할 수 있고, craco.config.js 파일을 사용한다.
	- 그 밖에 eslint, babel 등의 환경설정도 가능하다.

