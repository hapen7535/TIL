## LiveData
데이터 홀더 클래스.  
MVVM 패턴에서 ViewModel과 View 간의 데이터 통신을 쉽게 구현할 수 있도록 한다.  
데이터의 변화를 관찰하고, 이에 따라 연결된 Observer들에게 자동으로 업데이트 이벤트를 발생시킨다.  
이를 통해 UI 업데이트를 한다.  
  
LiveData는 LifecycleOwner에 바인딩되어 있어,  
해당 LifecycleOwner의 활성 상태에 따라 값이 업데이트된다.  
  
만약 Activity의 상태가 onPause() 상태가 된다면,  
LifecycleOwner가 비활성화 되어,  
LiveData의 값이 ViewModel에서 바뀌더라도 Activity가 모르게 된다.
