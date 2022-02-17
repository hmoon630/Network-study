# TCP 데이터 전송 과정

TCP로 데이터를 주고 받는 과정은 크게 3단계로 구분된다. 연결 설정, 데이터 전송, 연결 해제이다.

## 연결 설정
![3wayhandshake](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fdn8er2%2Fbtrbe6Jzug6%2FhHB5DK5ApKhZHfY84M3kwk%2Fimg.png)

TCP로 통신하기 위해서 먼저 두 프로세스 간에 연결 설정을 하게 된다. 이 과정을 3-way handshake라고 부른다.

TCP 3-way handshake는 다음과 같은 절차로 이루어진다.

1. Client > Server SYN
2. Server > Client SYN ACK (이전 단계의 SYN + 1)
3. Client > Server ACK (이전 단계의 SYN + 1)

여기서, SYN은 1238679와 같이 숫자이고, 이를 잘 받았다는 의미로 ACK에 SYN + 1 한 값을 넣어서 다시 보냅니다. 이와 같은 일련의 절차를 거쳐 세션이 수립됩니다.

## 데이터 전송
![datatransfer](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbuXh7b%2FbtrbbS5VUM7%2F5HC4BSuLKO6jxsCWUOUX30%2Fimg.png)

TCP는 양쪽 프로세스가 동시에 데이터를 전송할 수 있는 전이중 방식이다. 
기본적으로 seq(순서, 일련 번호) + 받은 Data의 바이트 수 한 값을 ACK에 담아서 수신하였음을 표현한다.

## 데이터 전송 오류 
![dataerror](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdN6SYZ%2FbtrbhYEhWfd%2FkBESKiQ0jcvsCUw6VWFJMK%2Fimg.png)

TCP는 전송한 데이터가 분실되거나 변형되었을 경우 오류 제어하는 기능이 있다.

위의 이미지에서 A > B 프로세스로 3번 데이터를 전송하였으나, B 프로세스는 2번째 까지만 수신하였다. 이때 A 프로세스는 31이라는 ACK 값을 보고 어디까지 수신하였는지 파악하여 누락된 데이터를 재전송 하게 된다.

## 연결 해제
![4wayhandshake](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcZcPUv%2FbtrbhXS2q17%2F0bq6nuinXQRcIQUH9RMby1%2Fimg.png)
TCP를 연결 해제 하고자 할 때는 4-way handshake를 하게 된다.

TCP 4-way handshake는 다음과 같은 절차로 이루어진다.

1. Client > Server ACK FIN
2. Server > Client ACK 
3. Server > Client ACK FIN
4. Client > Server ACK

연결 해제는 연결 해제를 원하는 측에서 FIN 플래그를 지정하면서 이루어진다.

연결 해제를 요청 받은 프로세스가 아직 보내고자 하는 데이터가 있을 수 있기 때문에, 이 프로세스가 다시 FIN 플래그를 보내기 전 까지는 연결이 유지된다. (2단계와 3단계 사이)

양측이 동의 하게 되면 연결이 해제된다.



## Reference
[TCP 프로토콜을 이용한 데이터 전송](https://ddingz.tistory.com/167)

[TCP (Transmission Control Protocol)](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=printf7&logNo=10170434058)