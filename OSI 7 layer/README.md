# OSI 7 계층
OSI 모델은 컴퓨터 네트워크 프로토콜을 계층으로 나누어 설명한 것이다. 각 계층은 하위 계층의 기능을 이용하고, 상위 계층에게 기능을 제공한다. 일반적으로 하위 계층은 하드웨어, 상위 계층은 소프트웨어로 구현된다.

## 1 - 물리 계층(Physical Layer)
물리 계층은 기본 네트워크 하드웨어 전송 기술로 구성된 계층이다. 이 계층에서 사용되는 통신단위는 **비트**로, 1과 0(On, Off)으로 표현된다.

이 계층은 단순히 데이터를 전달하기만 하고, 데이터의 내용과 에러에 대해서는 신경쓰지 않는다. 

EX) 
- 네트워크 어댑터(랜 카드)

![네트워크 어댑터](https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Network_card.jpg/220px-Network_card.jpg)

- 이더넷 허브

![이더넷 허브](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/4_port_netgear_ethernet_hub.jpg/230px-4_port_netgear_ethernet_hub.jpg)


## 2 - 데이터 링크 계층(Data Link Layer)
데이터 링크 계층은 물리 계층을 이용하여 네트워크 상의 주변 장치 간 데이터를 전송하는 계층이다. 

크게 두가지의 기능을 한다.
- **주소 할당**: 물리 계층으로부터 받은 신호를 네트워크 상의 장치에 올바르게 보낼 수 있도록 한다. MAC 주소를 사용한다.
- **오류 감지**: 신호가 전달 되는 동안 오류가 포함되는지 감지하고, 수정하는 데에 필요한 수단을 제공한다.

EX)
- 브릿지

![브릿지](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e8/Network_Bridging.png/400px-Network_Bridging.png)

- L2 스위치

![L2 스위치](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fb8RKvv%2FbtqMhu1Q6Yh%2FzKtVm2Y4xhASXRJGje5gX1%2Fimg.png)


## 3 - 네트워크 계층(Network Layer)
네트워크 계층은 라우팅을 포함하여 패킷 포워딩을 담당한다. 
이 계층은 IP 주소를 사용하여 경로를 선택하고 경로에 따라 패킷을 전달해준다.

### IP(Internet Protocol)
IP는 두 호스트가 패킷 교환 네트워크에서 정보를 주고 받는데 사용하는 규약이다. 네트워크 계층에서 호스트의 주소 지정과 패킷 분할 및 조립을 담당한다. 

IP는 비 신뢰성과 비연결성이 특징이다. 전송과정에서 패킷이 손상되거나 순서가 뒤죽박죽이 될 수도 있다. 패킷 전송과 정확한 순서를 보장하려면 TCP 프로토콜과 같은 상위 프로토콜을 이용해야 한다.

### ICMP(Internet Control Message Protocol)
ICMP는 운영체제에서 오류 메시지를 전송하는 데 주로 쓰이며 IP에 의존하여 작업을 수행한다.

## 4- 전송 계층(Transport Layer)
전송 계층은 계층 구조의 네트워크 구성 요소와 프로토콜 내에서 송신자와 수신자를 연결하는 통신 서비스를 제공한다. 전송 계층은 연결 지향 데이터스트림 지원, 신뢰성, 흐름 제어, 다중화와 같은 서비스를 제공한다.

### TCP
TCP는 LAN, 인트라넷, 인터넷에 연결된 컴퓨터에서 프로그램 간에 옥텟을 안정적으로, 순서대로, 에러없이 교환할 수 있도록 하는 프로토콜이다. 

TCP 프로토콜은 3단계에 걸쳐 작동한다.

1. 연결 생성: 연결을 사용하기 위해 3-way handshake를 사용한다.
2. 자료 전송
3. 연결 종료: 연결을 종료하기 위해 4-way handshake를 사용한다. 

### UDP
UDP는 너무 단순하여 서비스의 신뢰성이 낮고, 순서가 바뀌거나 중복될 수 있다. UDP는 일반적으로 오류의 검사와 수정이 필요 없는 애플리케이션에서 수행한다.

ex) DNS, IPTV, 온라인 게임 등

## 5 - 세션 계층(Session Layer)
세션 계층은 세션 연결의 설정, 해제, 메시지 전송 등의 기능을 한다. 세션 계층의 중요한 기능은 동기화이다. 동기는 통신 양단에서 논리적인 공통처리 지점이다. 동기점이 설정되면 그 이전의 통신은 서로 완벽히 처리했다는 것을 의미한다.

### RTP (Real-time Transport Protocol)
RTP는 오디오와 비디오를 전달하기 위한 프로토콜이다. WebRTC를 포함한 스트리밍 미디어를 수반하는 통신에서 사용된다.

RTP는 일반적으로 UDP로 동작한다. RTP는 RTCP(RTP Control Protocol)과 함계 결합하여 사용한다. RTP는 미디어 스트림을 전달하고, RTCP는 전송 통계와 QoS를 모니터링하고 다중 스트림의 동기화를 돕는다. 


## 6 - 표현 계층(Presentation Layer)
표현 계층은 네트워크의 데이터 번역자로서의 역할을 한다. 

### MIME(Multipurpose Internet Mail Extensions)
MIME은 전자 우편을 위한 인터넷 표준 포맷이다. 전자 우편은 7비트 ASCII문자를 사용하여 전송되기 때문에, 8비트 이상의 코드를 사용하는 문자나 이진 파일은 MIME 포맷으로 변환되어 SMTP로 전송된다. 

## 7 - 응용 계층(Application Layer)
응용 계층은 프로세스 간 통신 접속을 위해 설계되어 통신 프로토콜과 방식을 위해 보유된 추상 계층이다. HTTP, FTP, SMTP와 같은 프로토콜이 있다. 

### HTTP(HyperText Trasfer Protocol)
HTTP는 WWW 상에서 정보를 주고받는 프로토콜이다. 주로 HTML 문서를 주고 받는데 사용된다. TCP를 사용하여 동작하고, HTTP/3부터는 UDP를 사용하며, 80번 포트를 사용한다. 

### FTP(File Transfer Protocol)
FTP는 TCP/IP 프로토콜을 가지고 서버와 클라이언트 사이의 파일 전송을 위한 프로토콜이다. 21번 포트를 사용한다. 





## Reference
[OSI 7 계층이란?, OSI 7 계층을 나눈 이유](https://shlee0882.tistory.com/110)