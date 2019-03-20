# JS 33 concept

## 1. CallStack 호출 함수
자바스크립트의 실행환경
- 브라우저는 단순히 엔진 하나만 아닌 DOM, AJAX, setTimeout 등의 Web APIs에서 제공
- Web API의 호출을 통제하기 위한 Event Queue와 Event Loop 존재

자바스크립트를 V8엔진으로 돌아가며 두 부분으로 나뉜다.
###### Memory Heap : 메모리 할당 영역
###### Call Stack : 코드 실행 시, 스택 프레임 생성

콜스택은 현재 작업의 위치를 기록하는 자료구조이다.
함수가 실행되면 순차적으로 콜스택이 쌓이며
해당 함수가 제일 상단으로 올라가고(Push)
실행이 끝나게 되면 해제(Pop)된다.
LIFO방식 - Last In First Out
     
function multiply(x, y) {
    return x * y;
}
function printSquare(x) {
    var s = multiply(x, x);
    console.log(s);
}
printSquare(5);

###### overflow 오버플로우 : 스택의 사이즈를 초과했을 때 발생하는 오류
Uncaught RangeError: Maximum call stack size exceeded

###### 단일 호출 스택 문제점 
- 하나의 함수처리가 매우 느림

###### 해결책 => 비동기 콜백(Asynchronous Callbacks)
비동기 콜백은 특수한 시점에서 실행되므로 스택안에서 push 될 필요가 없습니다.
자바스크립트 실행환경에 이벤트 큐(Event Queue - FIFO방식)를 가지고 있습니다.

Reference Link : https://new93helloworld.tistory.com/358

## 2. Primitive type 원시 자료
오브젝트를 제외한 모든 값은 변경 불가능한 값이다.
(C언어에서는 숫자를 문자열이라고 칭할 수 있으나 JS에서는 불변값이다.)
* Boolean type : true or false
* Null type : null
* Undefined type : 값을 할당하지 않는 변수
* Number type : 정수 or 실수
* String type : 문자열
* Symbol type : 기호

    
