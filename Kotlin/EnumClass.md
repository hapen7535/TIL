## Enum class(열거형 클래스)
서로 연관된 상수를 정의하는 열거형 클래스다.  
Kotlin 이외에도 C 와 같은 다른 언어에서도 지원하고 있다.  
상수들을 관리할 수 있다.  
상수들을 객체처럼 접근하여 사용할 수 있다.  

코드를 보다 읽기 쉬워지게 만들어 관리에 용이하게 한다.  
```Kotlin
enum class Fruits{
  BANANA, APPLE, ORANGE
}
```
위 코드에서는 BANANA가 Fruits 타입의 객체라고 볼 수 있다.
