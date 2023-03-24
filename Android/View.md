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
2. onAttachedToWindow(): View가 윈도우에 연결된다. View를 그리기 위한 surface를 가진다.  
3. onDetachedFromWindow(): View가 윈도우에서 분리된다. 여기서는 surface가 없어진다.  
4. onMeasure(int, int): View의 크기를 측정한다. measure()에서 호출하는 콜백 메소드다. setMeasuredDimenstion() 호출하여 명시적으로 너비와 높이 설정한다.  
5. onLayout(boolean, int, int, int, int): View의 자식 뷰들을 배치한다. View의 크기와 위치를 지정하여 화면에 배치한 후에 호출한다. 아직 View가 그려지는 단계는 아니다.  
6. dispatchToDraw() : View가 다시 그려져야 할 경우 자식 View도 싹 다 다시 그려지게 한다.
7. onDraw(Canvas): View를 그린다. 이전에 계산된 크기와 위치를 기준으로 View를 그린다. 
