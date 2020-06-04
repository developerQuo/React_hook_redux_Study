# React_hook_redux_Study

+ useState:

+ useEffect:

** side-effect: 

+ useMemo: memoization된 value를 반환한다. -> 특정 결과값 재사용.
	-- 함수와 의존성 값을 배열로 전달하면 의존성 값이 변경되었을 경우에만 memoization 값을 계산한다. 
<pre><code>
const memoizedValue = 
useMemo(
  () => computeExpensiveValue(a, b), [a, b]
);
</code></pre>

** rendering 중에만 실행된다.

** memoization: 컴퓨터 프로그램이 동일한 계산을 반복할 때, 이전에 계산된 값을 메모리에 저장하여 반복수행을 줄인다. -> 연산속도가 빨라진다.

+ useCallback: memoization된 callback을 반환한다. -> 특정 함수 재사용.
	-- 함수와 의존성 값을 배열로 전달하면 의존성 값이 변경되었을 경우에만 memoization 함수를 실행한다.
<pre><code>
const memoizedCallback =
useCallback(
  () => {
    doSomething(a,b);
  }, [a, b],
);
</code></pre>

** state가 바뀌면 새로 함수를 실행한다.

** callback: 다시부른다??


+ useForm: 

