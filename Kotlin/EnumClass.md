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
```Kotlin
enum class Fruits(val rank: Int){
  BANANA(1),
  APPLE(2),
  ORANGE(3)
}
```
위 코드처럼 enum class의 상수는 프로퍼티를 가질 수 있다.  
enum class는 메소드 또한 가질 수 있다.  

enum class는 interface는 상속받을 수 있지만,  
class는 상속받을 수 없다.  

enum class는 상수 값의 타입 안정성을 보장한다.  
상수 값이 해당 enum class 타입의 값만 할당받을 수 있는 것인지,  
컴파일 타임에 확인이 된다.  
타입 에러가 나더라도 프로그램 실행 전에 고칠 수 있으므로,  
타입 안정성을 보장한다고 볼 수 있다.
