# [TCP] 3 way handshake & 4 way handshake
> 연결을 성리하고 해제하는 과정을 말한다.

## 🎈3 way handshake - 연결 성립
> TCP 3 way handshake는 TCP/IP 프로토콜을 이용해서 통신을 하는 응용프로그램이 데이터를 전송하기 전에 
>  먼저 정확한 전송을 보장하기 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정을 의미한다.

![](https://user-images.githubusercontent.com/83829352/267882095-4aec5a07-448a-4ef9-bf5d-b5c3ee73efea.png)
1. 클라이언트가 서버에게 SYN 패킷을 보냄 (sequence : x)
2. 서버가 SYN(x)을 받고, 클라이언트로 받았다는 신호인 ACK와 SYN 패킷을 보냄 (sequence : y, ACK : x+1)
3. 클라이언트는 서버의 응답은 ACK(x+1)와 SYN(y) 패킷을 받고, ACK(y+1)을 서버로 보냄

이렇게 3번의 통신이 완료되면 연결이 성립된다.
* SYN(Synchronize sequence numbers)
* ACK(acknowledgment)

<br/>

## 🎈4 way handshake - 연결 해제
연결 성립 후, 모든 통신이 끝났다면 해제해야 한다.
![](https://user-images.githubusercontent.com/83829352/267882196-b8ce414a-749a-4358-b38d-c479230606c3.png)

1. 클라이언트는 서버에게 연결을 종료한다는 FIN 플래그를 보낸다.
2. 서버는 FIN을 받고, 확인했다는 ACK를 클라이언트에게 보낸다.(이때 모든 데이터를 보내기 위해 CLOSE_WAIT 상태가 된다.)
3. 데이터를 모두 보냈다면, 연결이 종료되었다는 FIN 플래그를 클라이언트에게 보낸다.
4. 클라이언트는 FIN을 받고, 확인했다는 ACK를 서버에게 보낸다. (아직 서버로부터 받지 못한 데이터가 있을 수 있으므로 TIME_WAIT을 통해 기다린다.)
	* 서버는 ACK를 받은 이후 소켓을 닫는다(Closed)
	* TIME_WAIT 시간이 끝나면 클라이언트도 닫는다(Closed)

이렇게 4번의 통신이 완료되면 연결이 해제된다.


[참고자료](https://bangu4.tistory.com/74)
