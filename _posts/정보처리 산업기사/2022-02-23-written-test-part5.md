---
title:  "[ 필기 ] 프로세스(Process) Part.2 " 

categories:
  - Data processing
tags:
  - [프로세스, 정보처리산업기사, 자격증]

toc: true
toc_sticky: true

date: 2022-02-23
last_modified_at: 2022-02-23
---
강의를 듣고 정리한 필기입니다. 😀 지식 공유보단 개인적인 복습을 목적으로 포스팅하였습니다.

---
## 1. 인터럽트 정의

	프로세스가 수행 중에 다른 프로세스를 수행하기 위하여 현재 수행 중인 프로세스를 중단하거나 외부 입력장치에 의해
	프로세스가 중단되는 상태를 인터럽트라고 한다
	사용자에 의해서 새로운 프로그램이 실행 될 때, 현재 실해 중인 프로세스의 상태를 잠시 중단하고, 새로운 프로그램을 실행 시키는 과정이다.
	잠시 중단한 프로세스의 상태는 다시 실행을 시작하기 위해 중단되었던 시점의 정보를 잠시 저장한다.
	인터럽트는 입출력 연산, 하드웨어 실패, 시스템 오류 등에 의해서 발생한다.
	인터럽트가 발생한 경우, 진행 중인 프로그램의 재개(Resume)에 필요한 레지스터 문맥(Register context)을 저장한다.

앞에서 배웠던 프로세스 상태 전이도에서의 모든 멈춤현상들도 인터럽트라고 한다.
![(Ready)](https://user-images.githubusercontent.com/88019314/155251523-027dc575-58ba-489d-97db-bce8c14b50f2.png)

## 2. 인터럽트의 처리를 위한 작업 순서
<img width="586" alt="Pasted Graphic 16" src="https://user-images.githubusercontent.com/88019314/155251560-b00a7872-9393-4aa9-ac2e-179429d2c181.png">
<br>

    1. 인터럽트가 발생하면 운영체제가 제어권을 받는다
    2. 운영체제는 인터럽트 받은 현재의 프로세스 상태를 저장한다
    3. 운영체제는 인터럽트의 발생 원인을 찾아 지정되어 있는 루틴으로 제어권을 넘겨준다
    4. 인터럽트 처리 루틴이 인터럽트를 처리한다.
    5. 인터럽트가 걸렸던 이전 프로세스의 상태로 복구된다.
    6. 인터럽트가 걸렸던 시점 이후부터 프로세스가 실행된다.

## 3. 인터럽트의 종류

### 3-1 SVC(SuperVisor Call) 인터럽트
		프로세스 관리 호출, 기억장치 할당 루틴호출, 입출력 수행 루틴 호출 시에 발생하는 인터럽트로 사용자가 새로운 프로그램을 실행할 때 발생한다.
		새로운 프로그램을 실행하는 것은 사용자와 운영체제 정보 교환을 하므로 오퍼레이터(사용자)와의 대화 시에 발생하는 인터럽트라고 한다.

### 3-2 입출력(I/O) 인터럽트
		하드웨어적 인터럽트로 프린트나 디스크 저장 시에 입출력 채널 확인,준비,할당,완료 시에 발생한다.

### 3-3 외부(Extern) 인터럽트
		여러 개의 프로세스가 운영되는 다중 프로그래밍 기법에서 임의의 프로세스는 CPU를 사용하기 위한 일정한 시간 간격이 있는데 이를 시간 할당량이라고 한다.
		임의의 프로세스는 운영체제에 의해서 시간 할당량이 확인되며, 운영체제가 관리하는 인터럽트 시계에 의해서 해당 프로세스가 종료된다.
		이때 발생하는 인터럽트가 외부 인터럽트다.

### 3-4 재시작(Restart) 인터럽트
		사용자가 Ctrl + Alt + Del 키를 입력하거나 Reset 버튼을 이용하여 시스템을 재부팅하는 경우에 발생한다

### 3-5 프로그램 검사(Program Check) 인터럽트
		실행 중인 프로그램에서 오버플로어(Overflow)나 언더플로어(Underflow)일 경우나 분모가 0인 나눗셈을 처리하는 경우에 발생한다

### 3-6 기계 검사(Machine Check) 인터럽트
		컴퓨터 시스템의 고장으로 발생한다.

## 4. 인터럽트의 특징
	컴퓨터 시스템에 비상사태가 발생할 떄 그 처리를 위해서 인터럽트가 필요하다
	하드웨어의 기능에 의하여 프로그램의 착오는 정해진 인터럽트 처리 루틴에 의해 복구되어야 한다.
	컴퓨터가 정상적인 업무를 수행하는 도중에 발생하는 예기치 않은 일들에 대하여 컴퓨터의 작동이 중단 없이 계속적으로 업무를 수행할 수 있도록 하는 기능이다.
	인터럽트가 발생되면 CPU는 현재 실행중인 명령을 마친 후 CPU의 상태를 보관한다.
	연산오류가 발생할 경우에 인터럽트가 발생한다.
	메모리 보호 구역에 접근을 시도하는 경우에 인터럽트가 발생한다.
	입출력이 완료되었을 때 인터럽트가 발생한다.
	인터럽트 요구를 처리하는 서비스 프로그램의 시작 주소는 다음 수행할 명령어의 번지를 기억하고 있는 레지스터인 프로그램  계수기(PC : Program Counter), 명령어 계수기에 기억시킨다.

### 4-1 인터럽트 처리를 위한 스택
	사용자에 의해서 새로운 프로그램이 실행 될 때, 현재 실행 중인 프로세스의 상태를 잠시 중단하고, 새로운 프로그램을 실행 시키는 과정이다.
	잠시 중단한 프로세스의 상태는 다시 실행을 시작하기 위해 중단되었던 시점의 정보를 잠시 스택(Stack)에 저장된다. 스택은 메모리 사용 방식 중에 하나이다.
	먼저 입력된 데이터가 나중에 처리되는 LIFO 구조이다.
	인터럽트나 함수 호출 등은 스택을 사용한다.
	큐(Queue) 구조의 메모리 사용 방식은 먼저 입력된 데이터를 먼저 처리해주는 FIFO 구조로 스풀이나 버퍼링을 사용하기에 적합한 방식이다.

## 5. 인터럽트 동기 
(📌동기 : 시간 맞춤 행위 )
	
### 5-1 동기 인터럽트 (Synchronous Interrupt)
	명령어 실행 중 CPU에 의해 처리되는 인터럽트로 하나의 명령어가 종료 후 인터럽트 발생한다.
	프로세스가 실행 중에 0으로 나누기를 할 때 발생하는 인터럽트, 프로세스 내 명령어 실행 때문에 발생하는 인터럽트, 프로세스 내 명령어가 보호 메모리 영역을 참조할 때 발생하는 인터럽트 등을 말한다.

### 5-2 비동기 인터럽트 (Asynchronous Interrupt)
	다른 하드웨어 장치가 CPU 클럭 시그널과 상관없이 생성하는 인터럽트이다.
	키보드 혹은 마우스를 사용할 때 발생하는 것과 같은 인터럽트를 말한다.

## 6. 트랩(Trap)
	프로세스가 특정 시스템 기능을 사용하려고 할 때 그 기능을 운영체제에게 요청하는 방법을 트랩이라고 한다.
	인터럽트 중에 소프트웨어적 인터럽트를 트랩이라고 할 수 있다.
	인터럽트나 트랩이 발생하면 프로그램 카운터(PC)를 정해진 특정 번지로 변경하여 정해진 처리 루틴을 수행하게 된다.
	
    트랩은 실행중인 프로그램 내에 특별한 조건을 걸어 놓은 것을 말한다.
	“인터럽트를 트랩한다”고 하면 특정한 인터럽트가 발생할 떄까지 기다렸다가, 해당하는 루틴을 실행시키는 것을 말한다.
	에러 트랩은 복원 루틴을 제공하기 위한 것이고, 디버깅 트랩은 특정 명령의 실행을 기다렸다가 현재 프로그램을 중지시키고, 현재 상태를 분석하는 것이다.
	트랩이 발생하는 조건은 0에 의한 나눗셈, Overflow 또는 underflow시, 보호 영역 내에 있는 기억장치 주소를 접근하는 경우이다.

## 7. PCB

### 7-1 PCB 정의
	PCB는 운영체제 내에서 한 프로세스의 존재를 정의한다. 즉, 여러 개의 프로세스를 수행하는 다중 프로그래밍 환경 하에서 각 프로세스를 구분하기 위한 프로세스 제어 블록이다.
	PCB 테이블은 프로세스들의 현재 상태를 기록한 정보 테이블이며 각 프로세스들의 주기억장치에 적재된 기억장치 혹은 포인터(100, 200, 300, 400)와
	식별자(식별자 : 1, 식별자 : 2 …) 등 PCB항족으로 기록된다.

### 7-2 PCB 항목
<img width="584" alt="1 Ready 120 3 100 23" src="https://user-images.githubusercontent.com/88019314/155252095-095706e0-6ad9-4312-9bec-7112a6a980b6.png">
<br>

	1. 프로세스 식별자
	2. 프로세스 현재 상태
	3. 프로그램 카운터(계수기)
	4. 프로세스 우선순위
	5. 프로세스가 적재된 기억장치 부분을 가리키는 포인터
	6. 프로세스에 할당된 자원을 가리키는 포인터
	7. 중앙처리장치(CPU, 처리기) 레지스터 정보
	8. CPU의 각종 레지스터 상태를 가리키는 포인터
    9. 계정 정보(시간 할당량)
	10. 기억장치 관리 정보
	11. 입출력 정보
	12. 부모 프로세스를 가리키는 포인터
	13. 자식 프로세스를 가리키는 포인터

### 7-3 프로세스 생성 과정
	새로운 프로새스를 위한 프로세스 식별자롤 할당한다.
	새로운 프로세스를 한 주소 공간과 프로세스 제어블록(Process Control Block)을 할당한다.
	새로운 프로세스의 프로세스 제어블록을 초기화한다.
	(상태정보, 카운터, 우선순위 등을 초기화)
	새로운 프로세스를 스케줄링 큐의 준비 또는 준비/보류 리스트에 연결한다.

## 8. 문맥교환(Context Switching)

### 8-1 문맥 교환의 정의
	다중 프로그래밍 시스템에서 운영체제에 의하여 CPU가 할당되는 프로세스를 변경하기 위하여 현재 CPU를 사용하여 실행되고 있는 프로세스의 상태정보를
	저장하고, 앞으로 실행될 프로세스의 상태 정보를 설정한 다음에 CPU를 할당하여 실행되도록 하는 작업이다.
	인터럽트가 발생한 경우, 진행 중인 프로그램의 재개(resume)에 필요한 레지스터 문맥(register context)을 저장한다.

### 8-2  시간할당량에 따른 문맥 교환수, 인터럽트 수, 오버헤드
	여러 개의 프로세스가 CPU를 차지하는 시간 간격을 시간할당량이라고 한다.
	시간할당량이 작으면 작을수록 여러 개의 프로세스가 동시에 수행되는 느낌을 가질 수 있지만 그에 따른 문맥 교환수, 인터럽트 횟수 오버헤드는 증가한다.

<img width="576" alt="Pasted Graphic 18" src="https://user-images.githubusercontent.com/88019314/155252259-04551b08-9d11-46cf-a994-bd75bbcfde2f.png">
***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}