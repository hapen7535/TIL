## LiveData
데이터 홀더 클래스.  
MVVM 패턴에서 ViewModel과 View 간의 데이터 통신을 쉽게 구현할 수 있도록 한다.  
데이터의 변화를 관찰하고, 이에 따라 연결된 Observer들에게 자동으로 업데이트 이벤트를 발생시킨다.  
이를 통해 UI 업데이트를 한다.  

### 장점
1. UI와 데이터 일치
2. 메모리 누수 방지
3. 생명 주기 자동으로 인식하여 관리
4. Activity가 중지되었을 때 비정상 종료 방지
5. 최신 데이터 유지
6. Configuration change 시 데이터 
7. 리소스 공유

LiveData는 LifecycleOwner에 바인딩되어 있어,  
해당 LifecycleOwner의 활성 상태에 따라 값이 업데이트된다.  
  
생명주기 상태가 STARTED, RESUMED라면 LifecycleOwner가 활성되며 LiveData가 업데이트될 수 있다.  
만약 Activity가 onPause() 메소드를 호출하는 상태가 된다면,  
LifecycleOwner가 비활성화 되어,  
LiveData의 값이 ViewModel에서 바뀌더라도 Activity가 모르게 된다.  

