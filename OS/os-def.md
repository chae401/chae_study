## ⚽️운영체제의 정의
> 운영체제는 사용자가 응용 프로그램을 실행할 수 있는 기반 환경을 제공하여 컴퓨터를 편리하게 사용할 수 있ㄷ로고 도와주고, 하드웨어를 효율적으로 사용할 수 있도록 다양한 기능을 제공하는 소프트웨어이다.

### 운영체제의 역할
- 조정자
	- 시스템 운영요소를 적절하게 사용할 수 있도록 제어
- 자원 할당자 or 관리자
	- 각 프로그램에 필요한 자원(프로세스, 메모리, 파일, 장치 등)을 할당하거나 효율적으로 운영하기 위한 자원 할당 방법 결정
- 응용 프로그램과 입출력장치 제어자
	- 응용 프로그램과 입출력장치 제어

### 운영체제의 기능
- 자원 관리
	- 메모리 관리
	- 프로세스 관리
	- 주변장치(입출력장치) 관리
	- 파일(데이터) 관리
- 시스템 관리
	- 시스템 보호(사용자 권한 부여)
	- 네트워킹(통신)
	- 명령 해석기

### 운영체제의 유형
> 컴퓨터 시스템의 발전 과정과 용도 또는 응답 시간이나 데이터 입력 방법에 따라 결정됨

- 일괄 처리 시스템
- 다중 프로그래밍 시스템
- 다중 처리 시스템
- 시분할 시스템
- 실시간 처리 시스템
- 분산 처리 시스템

### 운영체제의 서비스
- 부팅 서비스
	- 컴퓨터 하드웨어를 관리하고 프로그램을 실행할 수 있도록 컴퓨터에 시동을 건다.
- 사용자 서비스
	- 사용자 인터페이스 제공, 프로그램 실행, 입출력 동작 수행, 파일 시스템 조작, 통신(네트워크( 등으로 프로그래머가 프로그래밍 작업을 쉽게 수행할 수 있도록 한다.
- 시스템 서비스
	- 자원 할당, 계정, 보호와 보안 등으로 시스템의 효율적인 동작을 보장한다.
- 시스템 호출
	- 프로세스 제어, 파일 조작, 장치 조작, 정보 관리 통신 등으로 프로그램이 운영체제의 기능을 서비스받을 수 있는 프로그램과 운영체제 간의 인터페이스를 제공한다.

### 운영체제의 구조

- 단일 구조 운영체제
	- 단일(monolithic) 구조 또는 모놀리식 커널 구조 운영체제는 초기에 생겨난 가장 보편적인 형태이다.
	- 운영체제의 모든 기능을 커널과 동일한 메모리 공간에 적재한 후 시스템 호출만으로 사용할수 있는 작고 간단하면서 시스템 기능이 제한된 구조이다.
	- 대표적인 예는 도스와 초기 유닉스이다.
- 계층 구조 운영체제
	- 비슷한 긴으을 수행하는 요소를 그룹으로 묶어 최하위 계층(계층0)인 하드웨어에서 최상위 계층(계층5)인 사용자 인터페이스까지 다수의 계층으로 구성된다.
	- 시스템을 계층으로 나누면 시스템 설계나 구현이 단순하고 시스템 검증과 오류 수정이 쉽다.
- 마이크로 커널 구조 운영체제
	- 커널에는 최소 기능만 포함시켜 크기를 대폭 줄이고 기타 기능은 사용자 공간으로 옮겨 사용자 영역에서 수행하는 서버 구현 방법이다.
