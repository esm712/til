## TCP/IP 4계층

- 현재 인터넷에서 사용되는 프로토콜
- OSI 7계층에 비해 좀 더 실무적이면서 프로토콜 중심으로 단순화된 모델

### TCP/IP 4계층 구조

- 애플리케이션 계층(Application Layer): HTTP, FTP
- 전송 계층(Transport Layer) : TCP,UDP
- 인터넷 계층(Network Layer) : IP
- 네트워크 인터페이스 계층(Link Layer)

## IP 패킷 정보

- 출발지 IP
- 목적지 IP

## TCP 세그먼트 정보

- 출발지 PORT
- 목적지 PORT
- 전송 제어 정보
- 전송 순서 정보
- 검증 정보

## TCP의 특징

- 연결지향 : TCP 3 way handshake
- 데이터 전달 보장
- 순서 보장
- 신뢰 프로토콜

## TCP 3 way handshake

SYN(접속 요청), ACK(요청 수락)

3 way handshake의 과정

1. 클라이언트가 서버에 SYN를 보낸다.
2. 서버가 클라이언트네 SYN과 ACK를 보낸다.
3. 클라이언트가 서버에 ACK를 보낸다.
4. 서로 데이터를 주고 받는다.
