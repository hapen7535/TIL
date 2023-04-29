## Retrofit
### Retrofit
okhttp 기반으로 만들어진 네트워킹 라이브러리.  
http API를 interface 형식으로 호출할 수 있도록 도와준다.  
이를 사용하면 connection 설정, input / output stream 생성 및 할당 등과 같은 반복적인 작업들을 하지 않아도 된다.

### Multipart로 이미지 업로드
#### Multipart : http를 통해 파일을 서버로 전송하기 위해 사용되는 Content-type.
Content-type : Body에 들어가는 데이터 타입을 명시해주는 것  
Multipart는 파일을 여러 파트로 나누어 메시지를 전송하는 것

```kotlin
interface PostApi {

    @Multipart 
    @POST("/posts")
    suspend fun writePost(
        @Part id: MultipartBody.Part,
        @Part content: MultipartBody.Part,
        @Part file: MultipartBody.Part?,
        @Part type: MultipartBody.Part?
    ): PostResponse
    
}
```

위 예시와 같이 Multipart 어노테이션을 붙여줘야 한다.  
보낼 데이터는 Part 어노테이션을 붙이고, MultipartBody.Part 타입으로 명시해줘야 한다.  

위 API를 통해서 데이터를 보내기 위해서는 데이터를 MultipartBody로 변경시켜줘야 한다.

참고 : Jungwoon Blog(https://jungwoon.github.io/android/retrofit/2021/02/02/Retrofit-File-Upload.html)
