# NAT (Network Adress Translation)

NAT는 하나의 Public IP를 여러개의 Private IP로 변환하는 시스템이다.
주로 기업에서 내부망을 운영하는 경우, 내부망의 PC에는 Private IP를 부여하고 외부 인터넷에 연결된 라우터에 Public IP를 부여하여 하나의 IP를 같이 사용하는 형태로 운영한다.

현재 주로 사용되는 IPv4의 경우 주소의 갯수가 약 43억개로 한정되어 있다. 이 상황에서 IPv4 주소를 효율적으로 사용하기 위하여 도입된 시스템이 NAT이다.

## NAT 장점

### IP 주소 절약
상술하였듯이, IPv4 주소의 갯수는 한정되어 있고 각 네트워크 기기마다 IP를 부여하기는 어렵다. NAT는 하나의 Public IP를 여러 대의 기기가 사용하여 IP 주소를 절약할 수 있다.

### 보안
인터넷 망은 외부로부터의 침입, 해킹의 위험이 있다. 그래서 내부와 외부 사이에 방화벽을 두어 내부망을 보호한다. 외부에서는 내부망에 있는 PC에 직접적으로 접근할 수 없는 이유도 이와 같다.

## NAT 동작 원리
![NAT](https://t1.daumcdn.net/cfile/tistory/25618F4D583F70BC0A)

내부망에 있는 PC는 라우터(NAT)를 거쳐 외부와 통신하게 된다. 내부에서 외부로 패킷을 보낼 때는 목적지를 바로 찾을 수 있다. 하지만 외부에서 다시 내부로 패킷을 보낼 때 어떤 PC에 패킷을 되돌려 주어야 하는지 특정할 수 없다. (Public IP밖에 모르기 때문이다.)

그래서 NAT는 패킷이 외부로 나갈 때는 SRC_IP를 자신의 Public IP로 바꾸고 어떤 PC가 패킷을 보냈는지 NAT Table에 기록해 둔다. 다시 패킷이 내부로 들어올 때는 NAT Table을 보고 DST_IP를 원래의 Private IP로 바꾸어 패킷이 잘 전달 될 수 있도록 한다.

## NAPT (Network Adress Port Translation)
![NAPT](https://t1.daumcdn.net/cfile/tistory/2777A649583F70ED1B)

하지만 NAT의 경우 여러대의 PC가 하나의 서버와 통신할 경우 어떤 패킷이 어디서 왔는지 찾을 수 없게 된다. 이를 해결하기 위해 등장한 것이 NAPT이다.

![NAPT2](https://t1.daumcdn.net/cfile/tistory/2172644E583F71D30F)

기존의 NAT는 IP만 변환하였다면, NAPT는 Port도 임의로 지정하여 각각의 PC로부터 오는 패킷이 서로 다른 Port를 이용하여 통신할 수 있도록 한다. 이렇게 할 경우 패킷의 원 주인을 찾을 수 있게 된다.

## Reference
[NAT와 NAPT의 개념과 원리](https://5kyc1ad.tistory.com/254)
