# HTTP 기본

### **HyperText Transfer Protocol**

지금은 HTML뿐 아니라 이미지, 영상, API 등 거의 모든 형태의 데이터를 전송한다.

서버간의 데이터를 주고 받을 때도 HTTP를 사용한다.

HTTP/1.1을 가장 많이 사용한다.

성능 개선판인 HTTP/2와 /3도 점차 사용하고 있으며, HTTP/3은 UDP 기반이라는 특징이 있다.

### Stateless(무상태 프로토콜 지향)

가방을 사는 중간에 점원이 바뀔 수도 있다는 이야기.

즉 응답 서버를 바꿀 수 있기 때문에 무한한 서버 증설이 가능하다.

스케일 아웃 - 수평 확장에 유리하다.

### Connectionless(비연결성)

HTTP는 기본적으로 연결을 유지하지 않는다.

실제 서버에서 동시에 처리하는 요청은 매우 작기 때문에 서버 자원을 효율적으로 사용 가능하다.

그러나 요청할 때마다 3 way handshake를 반복해야하냐는 문제점이 발생한다.

→ 여러 데이터를 받는 동안 연결을 유지하는 **HTTP 지속 연결** 및 **UDP**를 활용하여 해결

## HTTP 메시지

![loading-ag-173](HTTP%20기본_assets/cc836f29e3824fdae45841f2bd15d4bc219cb612.png)

### 시작 라인

- 요청 메시지
  
    HTTP 메서드 + 요청 대상 + HTTP version으로 이루어짐.
  
  - HTTP 메서드 → GET, POST, PUT, DELETE etc..
  - 요청 대상 - 절대경로 ‘/’로 시작하는 경로

- 응답 메시지
  
    HTTP 버전 + HTTP 상태 코드 + 이유로 구성
  
  - HTTP 상태 코드 - 200: 성공  400: 요청 오류  500: 서버 내부 오류

### HTTP 헤더

- field-name + ‘:’ + field-value
  
    ㄴ field-name은 대소문자를 구분하지 않는다.

- HTTP 전송에 필요한 부가정보, 메타 데이터를 담는다.

### HTTP 메시지 바디

- 실제 전송할 데이터
- HTML 문서, 이미지, 영상, JSON 등등 모든 데이터를 전송할 수 있다.