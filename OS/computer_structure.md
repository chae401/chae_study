## 컴퓨터 시스템의 구성

### 1. 컴퓨터 시스템의 구성
- 컴퓨터 시스템은 프로세서, 메모리(기억장치), 주변장치의 하드웨어와 명령어로 작성한 프로그램인 소프트웨어로 구성된다.
- 위의 구성 요소는 컴퓨터의 주 기능인 프로그램을 실행하기 위해 버스로 상호 연결되어 있다.

<br/>

### 2. 프로세서
- `CPU(Central Processing Unit-중앙처리장치)` 는 컴퓨터 하드웨어 구성 요소 중 운영체제와 가장 밀접한 부분이다.
- 컴퓨터의 모든 장치의 동작을 제어하고 연산을 수행한다.
- 프로세서는 연산장치와 제어장치, 레지스터로 구성되며, 내부버스로 연결되어 있다.
- 보통 제어와 데이터 처리를 담당한다.

<br/>

### 3. 레지스터
- 프로세서에 위치한 고속 메모리로 극히 소량의 데이터나 처리 중인 중간 결과와도 같은 프로세서가 바로 사용할 수 있는 데이터를 담고 있는 영역이다.
- 용도에 따라 전용과 범용 레지스터로 구분된다.
- 저장하는 정보의 종류에 따라 데이터 레지스터, 주소 레지스터, 상태 레지스터로 세분화한다.
- 저장된 정보의 변경 여부에 따라 사용자 가시 레지스터와 사용자 불가시 레지스터로 구분한다.

<br/>

### 4. 메모리
**메모리 종류**
- 보조기억장치
	- HDD, SSD를 일컬으며 비휘발성이다.
	- 속도는 느리나 용량이 큰 자기디스크, 광디스크, 자기 테이프 등
	- HDD vs SSD
		- `하드디스크`는 기계적인 장치이다. 하드디스크 컨트롤러에게 어떤 특정 주소의 데이터를 읽어오라고 시키면 하드디스크는 '헤드를 해당 주소를 포함하는 트랙으로 이동시킨다' → '헤드가 해당 트랙의 위에 도착한다' → '해당 트랙의 LBA번호를 읽으면서 맞는 섹터가 도착할 때까지 기다린다'의 과정인데 여기서 헤드의 이동 거리는 10cm 정도.  
		=> 데이터가 있는 지점까지 직접 가서 읽는 방식
  
		- `SSD`는 이 모든 걸 전기 신호로 해결한다. 또 하드디스크의 데이터 액세스 포인트는 단 하나 뿐이지만 SSD는 이론상 무한하게, 실제적으로는 수천 개 이상의 액세스 포인트를 가질 수 있다.
		=> 데이터가 있는 위치에 전화를 걸어 확인하는 방식
		
- 메인메모리
	- RAM을 가리키며 휘발성이다.
	- 프로세서 외부에 있으면서 프로세서에서 수행할 프로그램과 데이터를 저장하거나 프로세서에서 처리한 결과를 저장
- 고속 버퍼의 캐시
	- 프로세서 내부나 외부에 있으면서 처리 속도가 빠른 프로세서와 상대적으로 속도가 느린 메인 메모리의 속도 차이를 보완
- 레지스터
	- 속도는 가장 빠르나 용량이 작음

**메모리 계층 구조**

<br/>

![image](https://github.com/chae401/chae_study/assets/83829352/2aae5b71-54e5-4d54-9086-db4710c84cf5)

여러 계층의 메모리를 연결하여 비용, 속도, 용량, 접근시간 등을 상호 보완한 계층적 메모리 구조를 메모리 계층 구조라고 한다.

<br/>

### 5. 시스템 버스
![image](https://github.com/chae401/chae_study/assets/83829352/4e4b2a33-7b13-41d7-9020-cb944ed22c3f)
- `시스템 버스(System Bus)`는 하드웨어를 물리적으로 연결하여 서로 데이터를 주고받을 수 있게 하는 통로이다.
- 컴퓨터 내부의 다양한 신호(데이터 입출력 신호, 프로세서 상태 신호, 인터럽트 요구와 허가 신호, clock 신호 등)를 시스템 버스로 전달한다.
- 위치에 따라 내부 버스(CPU 내부), 외부 버스(CPU 외부)로 구분된다.
- 기능에 따라 데이터 버스, 주소 버스, 제어 버스로 구분된다.
	<내부버스>
	- `Data Bus` : CPU와 기타 장치 사이에서 데이터를 전달하는 통로
	- `Address Bu`s : CPU가 주기억장치나 I/O 장치로 주소를 전달하는 통로
	- `Control Bus` : Data Bus와 Address Bus를 제어하기 위한 제어 신호들을 전송하는 통로

<br/>

### 6. 주변장치
- 프로세서와 메인 메모리를 제외한 나버지 하드웨어 구성 요소이다.
- 단순히 입출력 장치라고도 하는데, 크게 입력 장치, 출력 장치, 저장 장치로 구분한다.

<br/>

### 7. 명령어
> 명령어는 사용자가 원하는 연산과 오퍼랜드, 처리 순서를 프로세서에 지시하는 것이다.

**명령어 구성**
- 연산 부호(OPcode)
- 명령어가 처리할 데이터
- 데이터가 저장된 레지스터나 메모리 주소인 피연산자(operand)

<br/>

**명령어 실행**
- 컴퓨터 시스템의 메모리에 보관한다.
- 한 번에 한 개씩 프로세서로 전송하면서 해석&실행한다.
- 명령어는 명령어 인출과 명령어 실행 주기의 반복 처리로 실행한다.
- 명령어 실행 사이클은 인출 사이클, 간접 사이클, 실행 사이클, 인터럽트 사이클로 구성된다.

**인터럽트**
- 인터럽트는 현재 실행 중인 프로그램의 수행을 연기하고 다른 프로그램의 수행을 요구하는 명령이다.
- 시스템의 처리 효율을 향상시키며, 프로그램이 실행 순서를 바꿔 가면서 처리하여 다중 프로그래밍에 사용한다.




