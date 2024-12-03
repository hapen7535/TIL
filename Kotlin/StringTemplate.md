### 문자열 템플릿

```kotlin
  println("Hello $name") //kotlin
```
```java
  System.out.println("Hello, " + name + "!"); //java
```
여러 스크립트 언어와 비슷하게 변수를 문자열 안에 사용할 수 있다.</br>
문자열 리터럴의 필요한 곳에 변수를 넣되 변수 앞에 '$' 를 추가한다.</br>

자바와 다르게 좀 더 간결하며, 자바 문자열 접합 연산과 동일하게 효율적이다</br>
```kotlin
  println("Hello ${args[0]}!") 
```
복잡한 식도 중괄호로 둘러싸서 문자열 템플릿 안에 넣을 수 있다</br>
</br>

코틀린에서는 모든 유니코드 문자를 식별자에 사용할 수 있으므로 변수 이름에 한글이 들어갈 수 있다.</br>
다만 문자열 템플릿 안에 '$'로 변수를 지정할 때 변수명 바로 뒤에 한글을 붙이면 컴파일러는 영문자와 한글을 한꺼번에 식별자로 인식하여 unresolved reference 오류를 발생시킨다</br>
```kotlin
  println("$name님 반가와요!")
```
```kotlin
  println("${name}님 반가와요!") //중괄호를 사용하면 된다
```

출처 : Kotlin in Action 2장
