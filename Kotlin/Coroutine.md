## Coroutine
- launch : 코루틴 빌더. 새로운 코루틴을 실행한다. 동시에 코루틴 외의 코드도 동시에 실행된다.
- async : launch와 마찬가지로 코루틴 빌더다. 현재 실행되고 있는 스레드에 상관없이 즉시 코루틴을 실행시킨다. async는 suspend 함수 내에서만 사용이 가능하다.
- delay : 잠시 중단할 때 사용하는 함수. 코루틴을 특정 시간 동안 중단시킨다. 코루틴을 중단시켜도 기본 스레드는 차단되지 않는다.  
  그리고 중단시킨 스레드 외에 다른 스레드를 기본 스레드에서 실행시킬 수 있다. 일반 함수에서는 delay를 사용할 수 없고 suspend 함수에서만 사용할 수 있다.  
- join : 여러 개의 launch 블록이 있어, 동시에 여러 개의 코루틴이 실행될 경우 순서를 정해야 할 때 사용한다. join을 활용하여 순차적으로 실행될 수 있도록 할 수 있다.
- runBlocking : 코루틴 코드와 그 외 코드를 연결시켜주는 빌더. 현재 스레드를 작업이 완료될 때까지 blocking 한다. suspend 함수가 아니다.
- coroutineScope : runBlocking과 비슷하게 코루틴 빌더다. 다만 coroutineScope의 경우, suspend 함수에 해당하며 스레드를 blocking하는 것과는 다른 개념이다. 자식들이 종료를 기다리는 동안 스레드를 blocking하지 않는다. runBlocking과 반대다.
- Coroutine Context : 
  - Main : 메인스레드에 대한 context. UI와 관련된 작업에 사용
  - IO : 네트워킹과 같이 백그라운드에서 하는 작업에 사용
  - Default : 크기가 큰 배열을 다루는 것과 같이 무거운 연산을 할 때 사용
