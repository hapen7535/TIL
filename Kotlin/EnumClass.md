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

### Sealed class
enum class의 확장 개념으로 표현된다.  
sealed class는 abstract class이다.  
또한 private 생성자만 갖는다.  
sealed class의 서브 클래스들은 같은 패키지 내에 선언되어야 한다.  
서브 클래스는 object, data class, class가 될 수 있다.  
  
enum class와는 다르게, 여러 개의 인스턴스를 생성할 수 있다.  
enum class는 상수들이 단일 인스턴스로만 존재한다.  
  
sealed class는 상태관리에 용이하다.  
로딩 상태, 완료 상태, 실패 상태와 같은 상태에 대한 클래스를 사용할 때 많이 사용된다. 
  
또한 when과 같이 사용할 때 매우 유용하다.  
when 식에서 sealed class 서브 클래스에 대한 분기 처리를 할 때,  
컴파일러가 모든 서브 클래스에 대해서 처리를 해주었는지 확인을 해준다.  
```Kotlin
sealed class Fruit{
  object Banana: Fruit()
  object Apple: Fruit()
  object Orange: Fruit()
}
```
```Kotlin
val fruit: Fruit = Fruit.Banana
val result: String = when(fruit){
  is Fruit.Banana -> "banana"
  is Fruit.Apple -> "apple"
  is Fruit.Orange -> "orange"
}
```
위와 같이 모든 서브 클래스에 대해서 처리를 해주었다면 컴파일 에러가 나지 않지만,  
다음과 같은 코드에서는 에러가 난다.
```Kotlin
val fruit: Fruit = Fruit.Banana
val result: String = when(fruit){
  is Fruit.Banana -> "banana"
  is Fruit.Apple -> "apple"
}
```
