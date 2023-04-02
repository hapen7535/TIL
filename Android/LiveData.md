## LiveData
데이터 홀더 클래스.  
MVVM 패턴에서 ViewModel과 View 간의 데이터 통신을 쉽게 구현할 수 있도록 한다.  
데이터의 변화를 관찰하고, 이에 따라 연결된 Observer들에게 자동으로 업데이트 이벤트를 발생시킨다.  
이를 통해 UI 업데이트를 한다.  

### 장점
1. UI와 데이터 일치 : Observer를 통해 UI를 업데이트 할 수 있다.
2. 메모리 누수 방지 : 생명주기가 끝나면 자동으로 삭제된다.
3. 생명 주기 자동으로 인식하여 관리 : UI에서는 수동으로 생명주기에 따라 LiveData를 관리하지 않고 자동으로 생명주기에 따라 관리가 된다.
4. Activity가 중지되었을 때 비정상 종료 방지 : Activity가 백그라운드에 있을 때 Observer는 LiveData의 이벤트를 받지 않는다.
5. 최신 데이터 유지 : LifecycleOwner가 비활성화되고 다시 활성화되었을 때 최신 데이터를 받는다.
6. Configuration change 시 데이터 : 화면이 회전되었을 때 데이터가 초기화되는 문제가 있었는데, LiveData로 데이터 유지할 수 있다.
7. 리소스 공유 : LiveData 객체가 시스템 서비스에 한 번 연결되고, 리소스가 필요한 Observer는 LiveData 객체를 관찰할 수 있다.  
***안드로이드 시스템 서비스 : 디바이스 제어, 위치 정보 제공, 알람 설정 및 통지 메시지 표시 등과 같이 시스템의 핵심적인 기능 제공***

LiveData는 LifecycleOwner에 바인딩되어 있어,  
해당 LifecycleOwner의 활성 상태에 따라 값이 업데이트된다.  
  
생명주기 상태가 STARTED, RESUMED라면 LifecycleOwner가 활성되며 LiveData가 업데이트될 수 있다.  
만약 Activity가 onPause() 메소드를 호출하는 상태(중지 상태)가 된다면,  
LifecycleOwner가 비활성화 되어,  
LiveData의 값이 ViewModel에서 바뀌더라도 Activity가 모르게 된다.  

Activity A가 onResume() 메소드를 호출하는 상태였다가,
Activity B가 호출돼서 A가 바라보고 있는 LiveData의 값은 setValue를 통해 바뀐다면 바뀌기 이전의 값을 알고 있을 것이다.
Activity B가 호출돼서 A가 onPause()를 호출하는 상태가 되었기 때문이다.
PAUSED 상태라면 해당 LifecycleOwner가 비활성화 되므로 최신 값을 알지 못한다.
