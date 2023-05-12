## Android 애플리케이션 기본 앱 구성 요소
안드로이드 4대 컴포넌트 : 안드로이드 앱의 기본적인 구성 요소. 각 구성 요소는 시스템이나 사용자가 앱에 들어올 수 있는 진입점(Entry Point)이다.  
manifest 파일을 보면 아래 구성 요소들을 확인할 수 있다.  
  
- Activity : 사용자와 상호작용하는 진입점. UI를 포함한 화면. 
- Service : 백그라운드에서 앱을 실행하기 위한 진입점. UI를 제공하지 않는다. 예를 들어 백그라운드 음악 재생, 앱과 사용자가 상호작용 중에도 네트워킹 작업이 이루어지도록 하는 것을 포함한다.  
  - Foreground : 사용자가 앱과 상호작용하지 않을 때도 실행된다. Foreground 실행 시에는 사용자들에게 실행 중이라는 알림을 보내야 한다.
  - Background : Background는 직접적으로 사용자에게 보이지 않는 작업이다. 
  - Bound : 애플리케이션 컴포넌트와 바인딩할 때 bindService()를 통해 바인딩할 수 있다. 클라이언트와 서버 간의 커뮤니케이션 과정을 제공한다.
  - Service 생성 시 Service의 하위 클래스를 생성하고 몇 가지 콜백 메소드를 재정의해야 한다.
  - 기본적으로 Service는 UI 스레드인 메인 스레드에서 동작한다.
  - Service 내에서 별도의 스레드를 생성하여 작업한다.
  - 서비스는 생명주기를 갖고 있다.
- Broadcast Receiver : 이벤트를 앱에 전달한다. 앱이 시스템 전체의 알림에 응할 수 있도록 한다. 예를 들어, 비행기 모드와 같이 시스템 이벤트가 발생하면 시스템은 자동으로 브로드캐스트 메시지를 전송한다.  
  - manifest 파일에 직접 등록하거나 코틀린 코드 레벨에서 등록할 수 있다.
  - manifest 파일에 등록한 것은 정적 Broadcast Receiver이며, 코드 레벨에서 작성한 것은 동적 Broadcase Receiver 이다.
- Content Provider : 파일 시스템, SQLite 등 앱 데이터 집합을 관리한다. 다른 앱은 Content Provider를 통해 데이터를 쿼리하거나 가능할 경우 수정도 가능하다. 다른 앱에서 접근하도록 설계되었다. 애플리케이션 데이터 공유 시에 사용. 위젯에 데이터 전송할 때 사용. 앱에서 다른 앱으로 데이터를 copy & paste를 하고 싶은 경우에 사용. 앱의 직접적인 코드 변경 없이도 데이터 접근이 가능하도록 한다. 안전하게 다른 앱들이 데이터에 접근할 권한을 부여한다. 사용하려면 manifest 파일에 등록해야 한다. 
  - Content Provider에서 공유하는 것은 파일, 데이터베이스, SharedPreferences가 있다. 이는 CRUD 동작을 기본으로 한다. Content Provider는 insert(), query(), update(), delete() 메소드를 제공한다. 
  - 다른 앱에서는 ContentResolver를 통해서 ContentProvider에 접근할 수 있다.
  - 여러 ContentProvider 구분을 위해, Authority라는 값을 가진다.
  - Content Provider는 안드로이드 시스템에서 관리되며, 보안 및 권한 관리 기능을 제공하여 데이터의 접근을 제어한다. 그리고 데이터의 공유 범위를 조절하고, 애플리케이션 간의 데이터 보안을 강화한다.
  - 안드로이드에서는 이미 많은 내장 Content Provider가 제공된다. 주소록, 캘린더, 미디어 파일, 설정 등과 같은 데이터에 대한 접근을 제공한다. 또한 개발자가 직접 커스텀 Content Provider를 구현하여 애플리케이션 간 데이터 공유를 구현할 수도 있다.


Activity, Service, Broadcast Receiver는 intent를 통해 활성화된다.  

 
