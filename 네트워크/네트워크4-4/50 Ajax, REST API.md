# 제목 없음

50 Ajax, REST API

# Ajax란?

- Asynchronous JavaScript and XML의 약어
말 그대로 javaScript와 XML을 이용한 비동기적 정보 교환 기법이다. 다만 요즘은 XML보다는 JSON을 주로 사용한다.
브라우저의 XMLHttpRequest를 이용해 전체 페이지를 새로 가져오지 않고도 페이지 일부만을 변경할 수 있도록 javascript를 실행해 서버에 데이터만을 별도로 요청하는 기법이다.
HTTP 프로토콜을 이용한 비동기 통신이며 브라우저는 정적 HTML 파일과 CSS파일, 데이터를 어떻게 요청하면 되는지를 설명한 javascript를 통해 HTML, CSS를 이용해 골격을 먼저 형성하고 ajax 실행 부가 담긴 javascript 영역을 실행하여 데이터를 별도로 가져와 적절한 방법으로 데이터를 끼워 넣은 후 페이지를 로딩한다.

SNS에서 타임라인을 표시하거나, 게임처럼 반응하는 웹 페이지는 모두 Ajax로 구현된 것이다.

# REST API

REST란 Representational State Transfer의 약자로 자원을 이름으로 구분하여 해당 자원의 상태를 주고받는 모든 것을 의미한다.

- HTTP URI를 통해 자원을 명시한다.
- HTTP Method(POST, GET, PUT, DELETE, PATCH 등)를 사용
- 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미한다.

## CRUD Operation 이란

Create, Read, Update, Delete를 묶어서 일컫는 말로 예시로는
Create: 데이터 생성(POST)
Read: 데이터 조회(GET)
Update: 데이터 수정(PUT, PATCH)
Delete: 데이터 삭제(DELETE)

## 구성

- 자원: HTTP URI
- 자원에 대한 행위: HTTP Method
- 자원에 대한 행위의 내용: HTTP Message Pay Load

## 특징

- 서버-클라이언트 구조로 요청 시 응답이 오는 형태이다.
- 무상태-> 클라이언트의 요청이 일어나기 전까지는 연결이 없다
- 캐시 처리가 가능하다
- 계층화
- 인터페이스 일관성

## 장점

- HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구출할 필요가 없다.
- HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
- REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
- 여러 가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
- 서버와 클라이언트의 역할을 명확하게 분리한다.

## 단점

- HTTP Method 형태가 제한적이다.
- 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 정보의 값을 처리해야 하므로 전문성이 요구된다.