## Intent
4대 컴포넌트끼리 정보를 전달할 수 있도록 도와준다.
### 용도
  - Activity 시작
    - Activity를 시작하기 위해서 Intent를 startActivity()로 전달한다. 이때 Intent에는 시작할 Activity에 대한 설명과 필요한 데이터를 넣는다.
  - Service 시작
    - API 21 이하의 경우 Intent를 startService()에 전달하여 Service를 시작한다. 이 Intent에는 시작할 Service에 대한 설명과 필요한 데이터를 넣는다.
  - Broadcast 전달
    - Intent를 sendBroadcast() 혹은 sendOrderedBroadcast()에 전달하면 다른 앱에 Broadcast를 전달할 수 있다.

### 인텐트 필터 
  - manifest 파일에 들어가 있는 표현이다.
  - 해당 구성 요소가 수신하고자 하는 Intent의 유형을 나타낸다.
  - Activity에 대한 인텐트 필터를 지정하지 않는 경우, 명시적 인텐트를 통해서만 Activity를 시작할 수 있다.
