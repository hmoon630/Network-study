## IP 주소
IP 주소는 네트워크 상에서 컴퓨터를 식별하기 위한 주소이다. 

IPv4에서는 32비트를 이용하여 0~255 까지의 숫자 4개를 통해 표현한다. 현재 IPv4는 주소 공간의 고갈 때문에 대안으로 IPv6가 등장하였다.

## 서브넷팅 
서브넷팅은 IPv4에서 IP 주소가 부족해지는 것을 해결하기 위하여 하나의 네트워크를 여러개의 서브 네트워크로 나누는 것이다. 

외부에서 해당 네트워크를 바라보면 단일 네트워크 처럼 보이지만, 내부에서는 여러 개의 네트워크로 나누어져 있다. 

### 서브넷 마스크
서브넷 마스크는 네트워크 아이디와 호스트 아이디를 구분하기 위해 사용한다.

디폴트 마스크(Default Mask)는 C class 기준 255.255.255.0 이다.

네트워크 아이디와 호스트 아이디를 알기 위해서는 IP 주소와 서브넷 마스크를 비트로 AND 연산 하면 된다.

ex)
- IP: 192.168.0.199
- Subnet Mask: 255.255.255.0 
이 경우 네트워크 아이디는 192.168.0.0이 된다.

### 서브넷팅 방식
서브넷팅 하기 위해서는 기본 마스크에서 좌측부터 0을 1로 바꾸어 채워 나가면 된다.

ex)
- Default Mask: 255.255.255.0 (1111 1111 . 1111 1111 . 1111 1111 . 0000 0000)
- Subnet Mask: 255.255.255.192 (1111 1111 . 1111 1111 . 1111 1111 . **11**00 0000)

서브넷의 갯수는 디폴트 마스크에서 0이 1로 바뀐 갯수를 제곱한 만큼 존재한다. 

위의 예제의 경우 24비트에서 26비트가 되었으므로 [2 ^ **2** = 4] 4개의 서브넷이 생겼고, 서브넷 당 [2 ^ 6 - 2 = 62] 62개의 호스트를 사용할 수 있다.
이때, 2개를 빼준 이유는 네트워크 주소와 브로드캐스트 주소 2개는 미리 예약되어 있기 때문이다. (각각 192.168.1.0, 192.168.1.255와 같이 처음과 끝에 해당하는 호스트이다.)


## Reference
- [서브넷 마스크(Subnet Mask), 서브넷팅(Subnetting)](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=twers&logNo=50116961114)