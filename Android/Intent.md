## Intent
4대 컴포넌트끼리 정보를 전달할 수 있도록 도와준다.
### 용도
  - Activity 시작
    - Activity를 시작하기 위해서 Intent를 startActivity()로 전달한다. 이때 Intent에는 시작할 Activity에 대한 설명과 필요한 데이터를 넣는다.
  - Service 시작
    - API 21 이하의 경우 Intent를 startService()에 전달하여 Service를 시작한다. 이 Intent에는 시작할 Service에 대한 설명과 필요한 데이터를 넣는다.
  - Broadcast 전달
    - Intent를 sendBroadcast() 혹은 sendOrderedBroadcast()에 전달하면 다른 앱에 Broadcast를 전달할 수 있다.

### 암시적 인텐트
  - Intent에 데이터를 지정했지만 호출할 대상이 달라질 수 있는 경우에 사용한다.
  - 클래스 명이 아니라 어떤 작업을 수행할 것인지 지정하여 다른 앱의 컴포넌트가 해당 작업을 수행하도록 한다.

### 명시적 인텐트
  - 특정 컴포넌트의 이름을 지정하여 호출할 대상을 명확하게 실행해야 할 때 사용한다.
  - 시작하려는 Activity나 컴포넌트 클래스 명을 알고 있을 때 사용한다.

### 인텐트 필터 
  - manifest 파일에 들어가 있는 표현이다.
  - 해당 구성 요소가 수신하고자 하는 Intent의 유형을 나타낸다.
  - Activity에 대한 인텐트 필터를 지정하지 않는 경우, 명시적 인텐트를 통해서만 Activity를 시작할 수 있다.

### 인텐트 구성
  - 컴포넌트 이름 : 시작할 구성 요소의 이름. 명시적 인텐트를 사용할 때 필요한 정보다. 이 구성 요소가 없다면 암시적 인텐트가 된다.
  - Action : 수행할 작업을 나타내는 문자열. setAction(), Intent 생성자를 통해 Action을 지정할 수 있다.  ACTION_VIEW(Activity가 사용자에게 표시할 정보를 가지고 있을 때 사용), ACTION_SEND(다른 앱을 통해 공유할 데이터가 있을 때 사용), ACTION_EDIT가 있다.
  - Data : Action을 수행할 데이터 혹은 데이터의 MIME 유형을 나타내는 URI. * MIME type : 이 데이터가 어떤 형식의 데이터인지 설명하는 이름

### Extras
  - 작업을 수행할 때 필요한 추가 정보를 넣을 때 사용하는 키-값 쌍. putExtra() 메소드를 통해 정보를 추가할 수 있다. 해당 메소드 사용 시에는 키 이름과 값을 매개변수로 넣으면 된다.

### Flag
  - Intent에 대한 메타데이터 역할을 한다. 예를 들어 Android 시스템에 Activity를 어떤 방식으로 시작하는지에 대한 정보(Activity가 어느 Task에 소속되어야 하는지와 같은 정보)를 포함한다.
 
