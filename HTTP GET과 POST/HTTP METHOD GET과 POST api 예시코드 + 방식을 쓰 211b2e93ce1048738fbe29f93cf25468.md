# HTTP METHOD GET과 POST api 예시코드 + 방식을 쓴 이유

```swift
사용자는 단순히 URL(Uniform Resource Locator)을 입력하였지만 서버 내부에서는 클라이언트의 요청에 응답(웹페이지로 표현)하기 위해서 처리를 해주어야 한다. 

HTTP METHOD에는 get, post, put, delete 가 있습니다. GET이라는 단어는 "가져오다, 얻다"라는 뜻을 가지고 있다. GET 메서드는 클라이언트에서 서버로 어떠한 리소스로부터 정보를 요청하기 위해 사용되는 메서드이다. 조금 더 쉽게 말하면 데이터를 읽거나 검색할때 사용하는 메서드이다.

GET은 요청을 전송할때 URL주소 끝에 파라미터로 포함되어 전송되며 이 부분울 쿼리 스트링이라고 부른다. 또한 GET요청은 오로지 데이터를 읽을때만 사용되고 수정할때는 사용하지 않는다. 이 이이유로 사용하면 안전하다고 간주한다. 데이터의 변형의 위험없이 사용할 수 있다.
-GET은 불필요한 요청을 제한하기 위해 요청이 캐시 될 수 있다.
- 파라미터에 내용이 노출되기 때문에 민감한 데이터를 다룰떄 GET요청을 사용해서는 안된다. ( 보안에 취약하다)
- GET요청은 브라우저 기록에 남고 북마크에 추가도 가능하다.
-GET은 성공시 200(OK) HTTP 응답코드를 XML JSON 뿐만 아니라 여러데이터(html,txt 등) 여러 형식의 데이터와 함게 반환한다.
- GET요청은 멱등하다.
GET방식을 사용하여 데이터를 노출시키는 경우는 개인정보가 포함되지 않은 상황에서 캐싱을 하여 속도를 높이거나 즐겨찾기를 편리하기 위해 사용한다.
캐싱 - 캐싱은 한번 접근 후 또 요청할시 빠르게 접근하기 위해 레지스터에 데이터를 저장시켜놓는것이다.

먹등 - 연산을 여러번 적용하더라도 겨로가가 달라지지 않는 성질을 의미한다.
GET은 Idempotent, POST는 Non-idempotent하게 설계되었습니다.
GET이 idemportent하도록 설계되었다는 것은 GET으로 서버에게 동일한 요청을 여러번 전송하도록 동일한 응답이 돌아아와야 한다는것을 의미, GET은 설꼐원치겡 따라 서버의 데이터나 상태를 변경시키지 않아야 Idempotent하기 때문에 주로 조회를 할때에 사용해야 한다.

브라우저에서 웹페이지를 열어보거나 게시글을 읽는 등 조회를 하는 행위는 GET으로 요청하게 된다.

반대로 POST는 Non-ideportent하기 때문에 서버에게 동일한 여러번 전송해도 응답은 항상 다를 수 있다. POST는 서버의 상태나 데이터를 변경시킬때 사용한다. 리소스를 생성/업데이트 하기 위해 서버에 데이터를 보내는데 사용하는 메서드 , GET과 달리 전송해야 될 데이터를 HTTP메시지의 Body에 담아서 전송한다. 그리고 그 Body의 타입은 요청 헤더의 Content-Type에 요청데이터의 타입을 표시따라 결정된다. 
-POST 요청에는 데이터 길이에 대한 제한이 없다.
- Post 요청 중 자원생성은 201(Created) HTTP응답코드를 반환
- POST요청은 먹등하지 않는다.



get은 클라이언트에서 서버로 어떠한 리소스로부터 정보를 요청하기 위해 사용되는 method입니다. 즉, 서버에서 어떤 데이터를 가져와서 보여줄때 값이나 내용, 상태등을 바꾸지 않는 경우에 사용합니다.

post는 리소스를 생성/업데이트 하기 위해 서버에 데이터를 보내는데 사용되는 method입니다. 서버상의 데이터 값이나 상태를 바꾸기 위해서 사용됩니다. 주요 차이점으로는 get 요청은 캐시가 되나 post는 캐시되지 않습니다. get은 브라우저에 기록되지만 post는 기록되지 않습니다.

```

> Get Mapping
 
- dashBoard/dispatcher.api 는 카카오 로그인 이후 리다이랙트 처리를 하여 session값과 쿠키값을 가져오는 역할을 한다.
- 카카오 회원가입에서도 /auth/register.api를 getMapping으로 사용한다.

```swift
카카오 회원가입/로그인은 get과 post둘다 되는걸로 알고있다. post와 get을 쓰는 이유 , 각각의 이점 알아보기
```

- /fileDownload.api 에서 사용하는 방법 이해하기

> Post Mapping
 

```swift
예를들어 회원가입을 위한 코드를 작성할 경우 register를 위에서 잡아주고

 

작성은 get 등록은 post로 적어줘서 코드의 효율성을 올릴 수 있게된다

 

겟방식은 바디가 없어서 가벼운대신 용량제한이있고 URL에 값이 노출되어서 

 

보통 공유하기 목적이나 쇼핑몰 링크같은 경우 사용하기 용의하다 단순한 작업

 

반면 포스트방식은 URL에 노출되지 않고 용량제한이 없으며 바디안에 값이 담겨서 조금 더 보안적이지만 

 

겟방식에 비해 조금 무겁다는 단점이 있다 
```