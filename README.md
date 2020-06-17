# React_hook_redux_Study

<h2>React</h2>   
   
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

<h2>recoil</h2>
