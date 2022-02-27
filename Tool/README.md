# Network Monitoring Tools

## netstat
네트워크 소켓의 정보를 볼 수 있는 명령어 입니다.
소켓의 연결 상태, 버퍼에 존재하는 바이트 수 등의 정보를 확인할 수 있습니다.

![netstat](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdwmSN7%2FbtqvJKNBSW9%2FagO4MQRsTXZPlodL95Onl1%2Fimg.png)

## ping
상대 호스트가 응답하는지 확인하는 ICMP 패킷을 보냅니다.
호스트에 따라 부하를 막기 위해 ICMP 패킷을 거부할 수도 있습니다.

![ping](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcoXa9c%2FbtqvJUioe1c%2FX8ByFe0ZoSDrg1gWGrKukk%2Fimg.png)

## traceroute
udp 패킷을 생성하여 상대 호스트까지 도달하는 경로를 확인합니다.

![traceroute](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FHT95L%2FbtqvK5YEjN1%2FHHzS07RYvHk8vLCsV49kI0%2Fimg.png)

## tcpdump
송수신되는 패킷을 캡쳐할 수 있습니다. 특정 포트나 호스트로 향하는 패킷을 덤프합니다.

![tcpdump](https://mblogthumb-phinf.pstatic.net/MjAyMDA5MjVfMjk4/MDAxNjAxMDE2NDkwODUw.hmjkkpcl4Z4XP_s09Pd0edmjHAgQD0xMfDPm5B78vFMg.DspIuYmzpAmDeCu7iE1D5H-lLHbjYx6INUuU9qfPJEEg.JPEG.hanajava/tcpdump_cms02_kt.jpg?type=w2)

## ifconfig
네트워크 인터페이스에 관한 정보를 제공합니다.

![ifconfig](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Ifconfig_example_screenshot.png/300px-Ifconfig_example_screenshot.png)

## Reference
[리눅스 네트워크 모니터링 툴 명령어 - 1](https://wlsvud84.tistory.com/30)

[tcpdump 명렁어 활용](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=hanajava&logNo=222099470282)