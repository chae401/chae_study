# TCP (흐름제어 / 혼잡제어)

### TCP 통신이란?
- TCP 통신
	* 네트워크 통신에서 신뢰적인 연결방식
	* TCP는 기본적으로 unreliable network에서, reliable network를 보장할 수 있도록 하는 프로토콜
	* TCP는 network congestion avoidance algorithm을 사용

- reliable network를 보장한다는 것은 4가지 문제점 존재
	* 손실 : packet이 손실될 수 있다
	* 순서 바뀜 : packet의 순서가 바뀌는 문제
	* Congestion : 네트워크가 혼잡한 문제
	* Overload : receiver가 overload 되는 문제

- 흐름 제어/혼잡제어란?
	* 흐름제어(endsystem 대 endsystem)
		* 송신측과 수신측의 데이터 처리 속도 차이를 해결하기 위한 기법
		* Flow Control은 receiver가 packet을 지나치게 많이 받지 않도록 조절하는 것
		* 기본 개념은 receiver가 sender에게 현재 자신의 상태를 feedback 한다는 점
	* 혼잡제어 : 송신측의 데이터 전달과 네트워크의 데이터 처리 속도 차이를 해결하기 위한 기법

- 전송의 전체 과정
	1. `응용 계층(Application Layer)`에서 데이터를 전송할 때, 보내는 쪽(sender)의 애플리케이션은 소켓에 데이터를 쓰게 된다.
	2.  이 데이터는 `전송 계층(Transport Layer)`으로 전달되어 세그먼트(segment)라는 작은 단위로 나누어진다.
	3.  전송 계층은 이 세크먼트를 `네트워크 계층(Network Layer)`에 넘겨준다.
	4.  전송된 데이터는 수신자(receiver) 쪽으로 전달되어, 수신자 쪽에서는 `수신 버퍼(Receive Buffer)`에 저장된다.
		* 이때, 수진자 쪽에서는 수신 버퍼의 용량을 넘치게 하지 않도록 조절해야 한다.
	5.  수신자 쪽에서는 자신의 수신 버퍼의 남은 용량을 상대방(sender)에게 알려주는데, 이를 `수신 윈도우(Receive Window)` 라고 한다.
	6. 송신자(sender)는 수신자의 수신 윈도우를 확인하여 수신자의 수신 버퍼 용량을 초과하지 않도록 데이터를 전송한다.
<br/>

**🧨이를 통해 데이터 전송 중에 수신 버퍼가 넘치는 현상을 방지하면서, 안정적인 데이터 전송을 보장한다. 이를 `Flow Control`이라 한다.**

따라서 플로우 컨트롤은 전송 중에 발생하는 수신 버퍼의 오버플로우를 방지하면서, 안정적인 데이터 전송을 위해 중요한 기술이다.
