## View
안드로이드 앱을 실행할 때 가장 먼저 보이는 요소.  
UI를 구성하는 요소.  
  
View는 View를 포함할 수 있다.  
View 중에서 눈에 보이는 것들을 Widget,
보이지 않는 것들을 Layout이라고 한다.  
Layout은 Widget을 배치하는 역할을 한다.  
  
View를 여러 개 포함하고 있는 것들을 ViewGroup이라고 한다.  

View를 생성할 때는 반드시 크기 속성을 정의해주어야 한다.  

View는 Activity처럼 생명주기를 갖고 있다.  
View는 다음과 같은 생명주기를 가진다.

![0_cHmlPwPvhWJ15zU3](https://user-images.githubusercontent.com/79076150/227178712-e6b54c39-4d8b-45b0-a7cf-1b32231d6a51.png)

1. Constructor : 모든 View는 생성자를 통해 생명주기가 시작된다.  
  - 여기서 생성자는 총 4가지로 나뉜다.
  - View(context : Context) : xml이 아닌 동적으로 View를 생성하게 될 경우 사용하는 생성자.
  - View(context : Context, attrs: AttributeSet? = null) : xml에서 View를 inflate할 때 호출되는 생성자. xml에서 지정된 속성을 제공하여 xml에서 View를 구성될 때 호출된다. 기본 스타일인 0을 사용한다.
  - View(context: Context, attrs: AttributeSet? = null, defStyleAttr: Int = 0) : xml에서 View를 inflate를 할 때 호출되는 생성자. defStyleAttr는 View의 스타일 리소스를 참조하는 값.
  - View(context: Context, attrs: AttributeSet? = null, defStyleAttr: Int = 0, defStyleRes: Int = 0) : xml에서 View를 inflate를 할 때 호출되는 생성자. defStyleRes는 defStyleAttr가 0이거나 테마에서 찾을 수 없는 경우에 제공하는 Style 리소스 ID.
3. onAttachedToWindow(): View가 윈도우에 연결된다. View를 그리기 위한 surface를 가진다.  
4. onDetachedFromWindow(): View가 윈도우에서 분리된다. 여기서는 surface가 없어진다.  
5. onMeasure(int, int): View의 크기를 측정한다. measure()에서 호출하는 콜백 메소드다. setMeasuredDimenstion() 호출하여 명시적으로 너비와 높이 설정한다.  
6. onLayout(boolean, int, int, int, int): View의 자식 뷰들을 배치한다. View의 크기와 위치를 지정하여 화면에 배치한 후에 호출한다. 아직 View가 그려지는 단계는 아니다.  
7. dispatchToDraw() : View가 다시 그려져야 할 경우 자식 View도 싹 다 다시 그려지게 한다.
8. onDraw(Canvas): View를 그린다. 이전에 계산된 크기와 위치를 기준으로 View를 그린다. 
9. onFinishInflate() : 모든 자식 View가 추가된 후 호출된다.

참고 : 
- 찰스의 안드로이드 https://www.charlezz.com/?p=29013
- https://proandroiddev.com/the-life-cycle-of-a-view-in-android-6a2c4665b95e
