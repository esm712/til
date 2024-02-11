## HTTP

HyperTextTransferProtocol

- HTML, TEXT
- IMAGE, 음성, 영상, 파일
- JSON, XML
- 거의 모든 형태의 데이터 전송 가능

## 기반 프로토콜

TCP : HTTP/1.1, HTTP/2  
UDP : HTTP/3

## HTTP 특징

- 클라이언트 서버 구조
- Stateless
- 비연결성

## 클라이언트 서버 구조

- Request Response 구조
- 클라이언트 : UI 랜더링에 집중
- 서버 : 비지니스 로직, 데이터 집중

## Stateful와 Stateless 비교

| Stateful         | Stateless      |
| ---------------- | -------------- |
| 서버 증설 불가능 | 서버 증설 가능 |

## Stateless의 단점

- 모든 경우를 Stateless로 설계할 수 없는 경우가 있다.(로그인)
- 많은 정보가 패킷에 담긴다.
- Stateful은 최소한으로 사용해야한다.

## 비연결성

- 빠른 속도 응답 가능
- 서버의 자원을 효율적으로 사용 가능

## 비연결성 한계와 극복

- 페이지 이동이 이루어지면 TCP/IP 연결을 새로 맺어야 함
- 위의 문제를 Persistent Connections로 문제 해결
- HTTP/2, HTTP/3에서 더 많은 최적화

## 시작라인

request-line = method SP(공백) request-target SP HTTP-version CRLF(엔터)  
status-line = HTTP-version SP status-code SP reason-phrase CRLF

## HTTP 헤더

field-name ":" OWS field-value OWS (OWS : 띄어쓰기 허용)

- 용도 : 메시지 바디의 내용, 메세지 바디의 크기, 압축, 인증, 요청 클라이언트 정보, 서버 클라이언트 정보, 캐시 관리 정보 ...

## HTTP 메시지 바디

실제 전송할 데이터
