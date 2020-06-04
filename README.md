# React_hook_redux_Study

<h2>React</h2>
+ 단위: element < component   
+ JSX: JS를 확장하여 XML 기능 또한 가지고 있는 문법. UI를 표현.   
+ Babel: JS 컴파일러로 JSX를 React.createElement() 호출로 컴파일.     
   
React DOM: 내부에 모든 element를 관리.   
    render() 함수를 통해 root Dom node에 렌더링하고, element와 root node를 매개변수로 전달해야 한다.
React element: 불변객체. 변경하지않고 새로운 것을 쌓아야 한다.   
<pre><code>const element = <div />;</code></pre>
React component: React가 사용자정의 component를 발견하면 JSX attr와 children을 단일객체로 전달(props).   
<pre><code>const element = <Welcome name="Sara" />;</code></pre>
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

