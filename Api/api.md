## API 설계

**리소스**에 **집중**해라

**URI**는 **리소스**만 식별

리소스 : URI  
행위 : 메서드

## 예시

리소스 : 회원  
행위 : GET, POST, PUT, PATCH, DELETE, ...

## GET

리소스 조회  
쿼리 파라미터나 쿼리 스트링으로 요청

## POST

요청 데이터 처리, 리소스 등록  
**메시지 바디**를 통해 서버로 요청 데이터 전달

## PUT

리소스 대체, 리소스가 없다면 생성  
클라이언트가 리소스를 알고있어야한다.(POST와 차이점)

## PATCH

리로스 부분 변경

## DELETE

리소스 삭제

## 안전 Safe

호출해도 리소스를 변경하지 않는다.  
ex) GET, HEAD

## 멱등 Idempotent

f(f(x)) = f(x)  
몇 번을 호출하더라도 동일한 결과가 나온다.  
자동 복구 메커니즘
ex) GET, PUT, DELETE

## 캐시가능 Cacheable

응답 결과 리소스를 캐시해서 사용해도 되는가?  
ex) GET, HEAD, POST, PATCH 캐시 가능하지만 실제로는 GET, HEAD 정도만 캐시로 사용
