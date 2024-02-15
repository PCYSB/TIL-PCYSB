# 제목 없음

43 HTTP/HTTPS

# HTTP

Hyper Text Transfer Protocol의 약자로 주로 HTML과 같은 HyperText문서를 주고 받기 위해 만들어졌으며 최근에는 HTML뿐 아니라 모든 웹 관련 API통신에 이용하고 있는 통신 프로토콜이다.
HTML은 HyperText Markpup Langauge로 HTML의 파일을 주고 받을 수 있는 프로토콜이 HTTP이다. HTML은 hpyertext를 표현할 수 있는 언어이다.

## 특징

**비연결성**

> 처음 연결을 맺은 후 요청과 한번의 응답 이후 연결이 종료되며 매 요청마다 다시 연결을 맺는다.
> 

**무상태성**

> 프로토콜에서 Client의 상태를 기억하지 않는다. Client의 상태를 보관하기 위해 쿠키나 세션, JWT토큰 등을 이용하여 Client의 상태를 유지한다.
> 
- 비연결성과 무상태성이라는 특징이 통신을 하기위한 소프트웨어 구조를 단순하게 만들어주어 몇몇 선능적 이슈가 있음에도 가장 인기있는 통신 프로토콜이 되게 해주었다.

**단점**

> 요청이 많아질 경우 상당히 비효율 적이다. 3handshake -> HTTP 요청 -> HTTP 응답 이 행동을 엄청나게 반복하게 된다. 즉 요청이 많아질 경우에는 요청을 처음 시도할 때 거치는 행동들을 계속해서 반복하기에 이러한 경우에는 요청을 유지하고 있는 편이 오히려 효율적이다.
> 

## 요청 메세지

요청 메세지는 **start-line**, **header**, **empty-line**, **body**로 구성된다.

**start-line**

> HTTP METHOD와 URL, 그리고 protocol version 에 대해서 기술되어 있다. 어떤 요청을 하는지에 대한 내용이 기술되어있다.
> 
- HTTP METHOD: GET, POST, PATCH, PUT, DELETE와 같은 HTTP METHOD를 적는 부분
- URL: 리소스를 요청하는 주소를 의미한다.
- protocol version: HTTP의 버전을 의미한다. HTTP1.1을 가장 많이 사용하며 최근에는 HTTP/2의 사용이 늘고 있다.
- Header: 요청에 대한 정보, 응답에 대한 요청, 인증 정보, 접속 정보 등 요청에 필요한 다양한 요소를 담을 수 있는 공간. key, value로 구성 많이쓰는 구성은 밑에 작성
    - Content-Type: Body에 들어가는 요청의 Type을 의미 ex)json
    - Accept: 응답 받을 메세지 타입을 명시
    - conection: 주로 keep-alive를 셋업 매 요청시 커넥션을 다시 맺지 않고 커넥션을 유지하기에 성능향상을 기대할 수 있다.
    - User-Agent: 사용자의 기기를 식별. 기기/OS/브라우저 별 예외를 처리할 때 많이 사용, 사용자의 통계를 수집하기 위해서도 사용
    - Authorization: 인증 정보를 담을때 사용하는 Header 주로 인증 토큰을 Authorization Header에 담아보낸다.
- empty-line: Header와 body를 구분하는 부분

참고: [https://velog.io/@couchcoding/HTTP에-대해서-알아보자정의와-구조](https://velog.io/@couchcoding/HTTP%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C-%EC%95%8C%EC%95%84%EB%B3%B4%EC%9E%90%EC%A0%95%EC%9D%98%EC%99%80-%EA%B5%AC%EC%A1%B0)

# HTTPS

HyperText Transfer Protocol Secure의 약자로 HTTP에서 Secure이 추가되었다. 일반적으로 기존 HTTP보다 안전하다고 한다.

## 무엇으로 부터 안전한가?

내가 사이트에 보내는 정보들을 제 3자가 못 보게 한다.

- 데이터를 보낼때 암호화 하여 보냄
접속한 사이트가 신뢰할 수 있는 사이트인지 판별해 준다.
- 기관으로 부터 검증받은 기관만 HTTPS를 사용할 수 있고 그렇지 않은 경우 위험 경고를 띄어준다.

참고: [https://www.youtube.com/watch?v=H6lpFRpyl14](https://www.youtube.com/watch?v=H6lpFRpyl14)

# 스테이트리스

웹 브라우저 및 웹 서버의 요청과 응답은 전후 통신에 관계없이 매번 독립적으로 처리된다. 이런 통신을 스테이트리스라고한다. 서버가 클라이언트의 상태를 기억하느냐 못하느냐로 스테이트리스와 스테이트풀 상태를 나눈다.

- 같은 웹 페이지를 여러 번 반복해서 요청해도 같은 HTML 파일이 전송된다. 매우 비효율적임
- HTTP가 스테이트리스인 이유는 웹 서버가 불특정 다수의 웹 브라우저 요청을 처리하는 동안 접속별로 상태를 유지하기 어렵기 때문
- 해당 문제는 웹 브라우저에서 캐시를 사용해 해결할 수 있다.

# 스테이트풀

스테이트리스와 다르게 컨텍스트와 내역이 저장되어 중단되어도 중단된 곳 부터 다시 시작할 수 있다.

참고: [https://bumday.tistory.com/118](https://bumday.tistory.com/118)