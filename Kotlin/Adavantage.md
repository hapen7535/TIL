## Kotlin의 장점
1. Null 안정성
  - NullPointerException을 예방할 수 있도록 Kotlin에서는 Nullable과 non-null 타입을 구분해두었다.  
    따라서 Kotlin은 NullPointerException에서 자유로운 언어로 표현되기도 한다.  
    Nullable 변수는 자료형 뒤에 ? 를 붙이면 된다.  
    ? 을 붙이지 않은 변수에 null을 넣으면 오류가 난다.
2. 함수형 프로그래밍 지원
  - Kotlin에서는 함수형 프로그래밍과 객체지향 프로그래밍을 둘다 지원하는 언어다.   
    순수함수, 람다식, 고차함수를 사용하여 함수형 프로그래밍을 할 수 있다.  
    또한 Kotlin에서 불변성을 지향하므로 변수의 값이 변경되지 않도록 하고,  
    데이터의 변경이 필요한 경우에는 새로운 객체를 생성하는 방식으로 구현한다.
3. Java와의 호환
  - Java와 Kotlin은 모두 컴파일 시 Byte Code가 되어 서로 호환이 가능해진다.
4. 간결한 코드 작성
  - Java와 비교했을 때, Kotlin는 간결하게 작성할 수 있다.  
    Kotlin의 data class의 경우에도 Java처럼 getter, setter, 생성자를 만들어줄 필요가 없이 데이터를 다룰 수 있다.  
5. Coroutine의 사용
  - 비동기 실행 코드를 작성할 때 매우 유용한 Coroutine을 Kotlin에서 사용할 수 있다.
    Coroutine을 사용하면 경량 스레드로 성능면에서도 유리하며,  
    메모리 누수를 감소시킬 수 있다는 장점이 있다.
6. 타입 추론
  - Kotlin은 타입을 명시하지 않아도, 할당된 값으로 어떤 자료형인지 추론해준다.
