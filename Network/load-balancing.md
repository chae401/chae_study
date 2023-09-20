## Load Balancing

### 1. 왜 필요할까?
Client가 한 두명인 경우에는 Server가 요청을 처리하는데 큰 어려움이 없지만 <br/>
Client가 수천만명일 경우 하나의 Server가 모든 사람들의 응답을 하기에는 처리 속도가 따라갈 수 없어 동작을 멈추게 된다.<br/>

**그럼 어떻게 문제를 해결해야 할까?**
1. Scale-up : Server가 더 빠르게 동작하기 위해 하드웨어 성능을 올리는 방법
2. Scale-out : 하나의 server 보다는 여러대의 Server가 나눠서 일을 하는 방법<br/>

**Scale-out의 장점**
* 하드웨어를 향상하는 비용보다 서버 한대 추가 비용이 더 적다.
* 여러 대의 Server 덕분에 무중단 서비스를 제공할 수 있다.

### 2. 부하 분산 처리
`Load(부하) Balancing(분산)` 이란 컴퓨터 네트워크 기술의 일종으로 둘 혹은 셋 이상의 중앙처리 장치 혹은 저장장치와 같은 컴퓨터 자원들에게 작업을 나누는 것을 의미한다.
말 그대로 부하는 분산해 트래픽이 과도하게 몰려 서비스가 중단되는 현상을 막귀 위한 기술이다. 그래야 지연 없이 작업을 처리하고 속도를 낼 수 있다.
![image](https://github.com/chae401/chae_study/assets/83829352/2111380a-6c41-4420-a015-0b660f996b28)

### 3. 주요 기능
- NAT(Network Address Translation)
	* 사설 IP 주소를 공인 IP 주소로 바꾸는데 사용하는 통신망의 주소 변조기 
		-> `공인 IP`는 전 세계에서 유일하지만, `사설 IP`는 하나의 네트워크 안에서 유일하다. 공인 IP는 외부, 내부 상관없이 해당 IP에 접속할 수 있으나, 사설 IP는 내부에서만 접근이 가능하다.
- Tunneling
	* 인터넷 상에서 눈에 보이지 않는 통로를 만들어 통신할 수 있게 하는 개념
	* 데이터를 캡슐화해서 연결된 상호 간에만 캡슐화된 패킷을 구별해 캡슐화를 해제할 수 있다.
- DSR(Dynamic Source Routing protocol)
	* 로드밸런서 사용 시 서버에서 클라이언트로 되돌아가는 경우 목적지 주소를 스위치의 IP 주소가 아닌 클라이언트의 IP 주소로 전달해서 네트워크 스위치를 거치지 않고 바로 클라이언트로 찾아가는 개념이다.

![image](https://github.com/chae401/chae_study/assets/83829352/f0f228f5-93c3-4864-8df3-499f2eed60b8)

### 4. 종류
- L2
	* Mac 주소를 바탕으로 Load Balancing한다.
- L3
	* IP 주소를 바탕으로 Load Balancing 한다.
- L4
	* Transport Layer(IP와 Port) Level에서 Load Balancing 한다.
	* TCP, UDP
	![image](https://github.com/chae401/chae_study/assets/83829352/d91394f4-97ae-4999-894a-cbff2b87f118)

- L7
	* Application Layer(사용자의 Request) Level에서 Load Balancing을 한다.
	* HTTP, HTTPS, FTP
	![image](https://github.com/chae401/chae_study/assets/83829352/48192b3b-d1af-4f5c-af98-9fe46b7d747c)

- HTTP
	* X-Forwarded-For : HTTP 또는 HTTPS 로드 밸런서를 사용할 때 클라이언트의 IP 주소를 식별하는데 도움을 준다.
	* X-Forwarded-Proto : 클라이언트가 로드 밸런서 연결에 사용한 프로토콜(HTTP 또는 HTTPS)을 식별하는 데 도움을 준다.
	* X-Forwarded-Port : 클라이언트가 로드 밸런서 연결에 사용한 포트를 식별하는 데 도움을 준다.
	![image](https://github.com/chae401/chae_study/assets/83829352/1b226bd3-97b6-4e46-89a1-f0d939bda22a)

### 5. Load Balancer는 어떤 기준으로 Server를 선택할까?
- Round Robin
	* 단순히 Round Robin으로 분산하는 방식
		-> RR(Round Robin) : 프로세스들 사이에 우선순위를 두지 않고, 순서대로 시간 단위로 CPU를 할당하는 방식
- Least Connections
	- 연결 개수가 가장 적은 서버를 선택하는 방식
	- 트래픽으로 인해 세션이 길어지는 경우 권장하는 방식
- Source
	- 사용자의 IP를 Hashing 하여 분배하는 방식
	- 사용자는 항상 같은 서버로 연결되는 것을 보장한다.

### 6. Load Balancer 장애 대비 방법
> Load Balancer를 이중화 하여 장애를 대비할 수 있다.

**장애 발생 시나리오**
1. 이중화된 Load Balancer들은 서로 Health Check를 한다.
2. Main Load Balancer가 동작하지 않으면 가상 IP(VIPm Virtual IP)는 여분의 Load Balacer로 변경된다.
3. 여분의 Load Balancer로 운영

![LoadBalancer](https://github.com/chae401/chae_study/assets/83829352/d60a4098-9754-4d6f-b428-9022dad724b4)


[참고자료](https://nesoy.github.io/articles/2018-06/Load-Balancer)
