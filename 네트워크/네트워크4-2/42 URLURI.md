# 제목 없음

42 URL/URI

# URL(Uniform Resource Locator)

- URL은 네트워크 상에서 리소스가 위치한 정보를 나타낸다.
- HTTP 프로토콜뿐만 아니라 FTP, SMTP 등 다른 프로토콜에서도 사용할 수 있다.
- URL은 웹 상의 주소를 나타내는 문자열이기 때문에 더 효율적으로 리소스에 접근하기 위해 클린 한 URL 작성을 위한 방법론이다.

## URL 구조

- 스키마: 사용할 프로토콜을 뜻하며 웹에서는 http 또는 https를 사용
- 도메인 네임: IP 주소를 갖는 서버를 사용자가 쉽게 찾을 수 있도록 만들어준 서비스
- 포트: 포트 번호를 통해 어떤 서버를 이용할지 결정하며 웹 서버가 HTTP 프로토콜의 표준 포트를 사용하는 경우 일반적으로 생략된다.
- 경로: 파일의 경로를 가리킨다. 폴더 내에 파일과 폴더를 계속 만드는 것과 비슷한 개념으로 생각하자
- 파라미터: 쿼리 스트링이라고도 부르며 ?key=value 형태로 이루어진다.
- Anchor(Fragment): 프래그먼트, 해시태그라고도 부르며 특정 요소를 지시할 수 있다.

**URL 예시**[https://developer.mozilla.org](https://developer.mozilla.org/)[https://developer.mozilla.org/ko/docs/Learn/](https://developer.mozilla.org/ko/docs/Learn/)[https://developer.mozilla.org/en-US/search?q=URL](https://developer.mozilla.org/en-US/search?q=URL)

**구조**
이러한 URL이 있다고 가정하고 구조를 살펴보자
[https://hstory0208.tistory:3000/category?category=network&page=5#url차이](https://hstory0208.tistory:3000/category?category=network&page=5#url%EC%B0%A8%EC%9D%B4)

스키마

- https
- 브라우저가 리소스를 요청하는 데 사용해야 하는 프로토콜을 나타낸다.

**권한**

# URN

- Uniform Resource Name의 약자로 인터넷 상의 장원을 나타내는 또 다른 식별자이다.
- 해당 자원의 위치나 접근 방법을 나타내지 않고, 자원의 고유한 이름으로 식별한다.

# URI(Uniform Resource Identifier)

우리말로 ‘통합 자원 식별자’

- Uniform은 리소스를 식별하는 통일된 방식을 말한다.
- Resource란, URI로 식별이 가능한 모든 종류의 자원(웹 브라우저 파일 및 그 이외의 리소스 포함)을 지칭한다.
- Identifier는 다른 항목과 구분하기 위해 필요한 정보이다.
즉, URI는 인터넷상의 리소스 “자원 자체”를 식별하는 고유한 문자열 시퀀스이다.