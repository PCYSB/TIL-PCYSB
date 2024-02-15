# 제목 없음

45 ICMP

# ICMP(Internet Control Message Protocol)

인터넷 제어 메시지 프로토콜로 네트워크 컴퓨터 위에서 돌아가는 운영체제에서 오류 메시지를 전송받는데 주로 쓰인다. 프로토콜 구조의 Type과 Code를 통해 오류 메시지를 전송받는다. IP에는 제어 메시지나 오류 메시지를 보내는 내장 메커니즘이 없다.(IP는 비연결 지향 프로토콜) 때문에 ICMP와 같은 프로토콜을 사용하여 오류를 제어한다.
인터넷상의 노드 간에 에러 사항이나 통신 제어를 위한 메시지를 보고하게 할 목적으로 만들어짐
*특정 대상과 내가 통신이 잘되는지 확인하는 프로토콜 L3

## 주요 Type의 종류

Type: Message: Description
0: Echo reply: Echo 메시지 응답
3: Destination unreachable: 도달 불가 Error
4: Source quench: 도달 불가 Error
5: Redirect: 더 빠른 경로가 있다는것을 알림
8: Echo request: Echo 메시지 요청
11: Time exceeded: TTL 초과된 경우
30: Traceroute: 해당 라우터까지의 경로 체크
15~18: 정보 주고받기 관련: DHCP가 이 역할을 대신함

## 특징

- ICMP는 TCP/UDP 헤더를 필요치 않으며 IP헤더와 IP데이터 부분에 ICMP 메시지를 포함하여 패킷을 전송한다.
- ICMP는 라우터가 에러 메시지를 다른 라우터에 전달하는 것을 허용한다.
- Ping은 ICMP echo request & reply를 이용한 응용프로그램이다.
- ICMP redirect 메시지는 라우터에 직접 접속된 네트워크에만 전송된다.
    - ICMP Redirect는 ICMP 프로토콜 중 하나의 타입으로, 더 좋은 경로가 있으면 라우터가 ICMP Redirect 패킷을 보낸다.
    - 라우터가 ICMP Redirect 패킷을 보내면 Host의 라우팅 테이블이 변경된다.
    - ICMP redirect 메시지는 호스트가 목적지 주소로 연결하고자 할 때, 해당 라우터가 최적의 경로임을 호스트에게 알려주기 위하여 라우터로부터 호스트로 보내어지는데 이를 이용하여 해커는 시스템의 정보를 획득할 수 있다.

장애 발생시 코드를 만든다.
type, code, check sum, 가변길이(type, code에 따라 달라짐)