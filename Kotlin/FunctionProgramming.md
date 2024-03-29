## Kotlin의 함수형 프로그래밍
**함수형 프로그래밍** : 순수 함수를 작성하여 프로그래밍의 부작용을 줄이는 프로그래밍 기법  
함수형 프로그래밍을 통해 코드를 간략화하고 테스트, 재사용성에 유리하게 된다.  
Kotlin은 함수형 프로그래밍과 객체지향 프로그래밍을 모두 지원하는 언어다.

함수형 프로그래밍의 핵심 개념은 다음과 같다.
- 일급 시민(First-class citizen) 함수
- 불변성 함수 프로그래밍 : 만들어지고 나면 내부 상태가 절대로 바뀌지 않는 불변 객체를 사용해 프로그램을 작성한다
- 부수 효과(side effect) 없음 : 입력이 같으면 항상 같은 출력을 내놓는다. 이를 위해 순수함수를 사용한다

Kotlin에서는 이러한 함수형 프로그래밍을 위해 람다식을 사용하고 있다.
### 람다식
- 이름이 없어도 함수 역할을 하는 익명 함수의 형태
- 화살표 표기법을 사용한다
- 예를 들어 다음과 같은 형태가 람다식이다
```
{x, y -> x + y}
```
- 2개 이상의 입력을 1개의 출력으로 단순화하는 개념인 람다 대수에서 비롯되었다
- 람다식에는 다양한 형태가 있다
1. 인자가 없는 익명 함수
```Kotlin
{ print("a") }
```
2. 인자 값을 받고 값을 리턴하는 익명 함수
```Kotlin
{x:Int, y:Int -> x + y}
```
3. 인자가 1개일 경우 인자 선언을 생략하는 익명 함수
```Kotlin
val a: (String) -> String = { "aaa + $it" }
```

### 순수함수
- 함수의 실행이 외부에 영향을 주지 않는 함수
- 함수에 동일한 인자를 주었을 때 항상 같은 값을 return하는 함수, 부작용이 없는 함수

### 일급시민(First-class citizen)
Kotlin에서 함수는 일급객체(First-class Object)로 취급된다. 일급시민이 되기도 한다.  
일급시민은 일급객체의 속성 중 하나를 말한다.  
함수형 언어에서 일급시민(First-class citizen)은 높은 수준의 추상화와 모듈화를 시행할 수 있도록 한다.  
일급시민인 함수는 다음과 같은 특징을 가진다.  
- 함수를 일반 값처럼 다룰 수 있다
- 함수를 변수에 저장할 수 있다
- 함수를 인자로 다른 함수에 전달할 수 있다
- 함수에서 새로운 함수를 만들어 반환할 수 있다

### 고차함수
다른 함수를 인자로 받거나 함수를 반환하는 함수.  
Kotlin에서는 람다나 함수 참조를 사용해 함수를 값으로 표현할 수 있다.  
일급객체를 주고받을 수 있는 함수가 고차함수가 된다.


