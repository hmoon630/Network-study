# DNS(Domain Name System)
DNS는 호스트의 도메인 이름을 IP주소로, 혹은 그 반대의 변환을 수행하기 위한 시스템이다. 

### 도메인 네임스페이스 (Domain Namespace)
네임스페이스는 DNS가 관리하는 트리 형태의 계층 데이터베이스이다. 최상위에 루트가 존재하고, 그 아래에 하위 도메인과 호스트들이 존재한다. 
![namespace](https://mblogthumb-phinf.pstatic.net/20140302_208/gaegurijump_1393749511837FuC4e_PNG/DNS.png?type=w2)

### 네임 서버 (Name Server)
도메인 이름을 IP 주소로 변환 시키는 역할을 한다. 이를 위해 네임스페이스를 가지고 있는 서버를 네임 서버라고 한다.

### 리졸버 (Resolver)
리졸버는 요청을 네임서버로 전달하고, 정보를 받는 역할을 수행한다. 만약 해당 네임 서버에 정보가 없다면 다른 네임 서버에 요청을 보내게 된다. 

## DNS 참조 순서
Local Hosts 파일 > DNS cache table > DNS Server 순서로 참조하게 된다. 

## DNS 쿼리(Query)
DNS 쿼리는 재귀적으로, 반복적으로 진행된다. 루트 DNS부터 점차 하위 도메인을 관리하는 DNS서버로 반복적으로 쿼리를 수행한다.
![query](https://mblogthumb-phinf.pstatic.net/20140302_83/gaegurijump_1393757149696l61z9_PNG/DNS4.png?type=w2)


## Reference
[DNS(Domain Name System) 란?](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=gaegurijump&logNo=110186376474)