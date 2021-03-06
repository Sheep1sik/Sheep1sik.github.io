---
title:  "[ 필기 ] 프로세스(Process) Part.1 " 

categories:
  - Data processing
tags:
  - [프로세스, 정보처리산업기사, 자격증]

toc: true
toc_sticky: true

date: 2022-02-22
last_modified_at: 2022-02-22
---
강의를 듣고 정리한 필기입니다. 😀 지식 공유보단 개인적인 복습을 목적으로 포스팅하였습니다.

---
## 1. 프로세스 정의
	CPU에 의해서 현재 실행되고 있는 프로그램
	PCB의 존재로서 명시되는 것
	프로세서(CPU)가 할당되는 개체로서 디스패치가 가능한 단위
	지정된 결과를 얻기 위한 일련의 계통적 동작
	목적 또는 결과에 따라 발생되는 사건들의 과정
	비동기적 행위를 일으키는 주체
	프로시저가 활동 중인 것
	실행 중인 프로시저의 제어 궤적
	CPU가 할당되는 실체

## 2. 프로세스 상태 전이도
![(Ready)](https://user-images.githubusercontent.com/88019314/155084282-e7f538d8-c824-472a-bce7-ff6153c1e456.png)

## 3. 주요 프로세스 상태

### 3-1 제출(Submit)
    작업을 처리하기 위해 사용자가 작업을 시스템에 제출한 상태
### 3-2 접수(Hold)
    제출된 작업이 스풀 공간인 디스크 할당 위치에 저장된 상태
### 3-3 준비(Ready) 
    프로세스가 프로세서를 할당받기 위해 기다리고 있는 상태	
    프로세스는 준비상태 큐 에서 실행 준비
    접수 상태에서 준비 상태로의 전이는 Job 스케줄러에 의해 수행
### 3-4 실행(Run)
    준비상태 큐에 있는 프로세스가 프로세서를 할당받아 실행되는 상태
    프로세스 수행이 완료되기전에 프로세스에게 주어진 프로세서 할당 시간이 종료되면 프로세스는 준비 상태로 전이된다	
    준비상태에서 실행 상태로의 전이는 CPU 스케줄러에 의해 수행
### 3-5 대기(Wait), 보류, 블록(Block)
    프로세스에 입출력처리가 필요하면 현재 실행중인 프로세스가 중단되고, 입출력 처리가 완료될때까지 대기하고 있는 상태이다.
### 3-6 종료(Terminated Exit) 
    프로세스의 실행이 끝나고 프로세스 할당이 해제된 상태이다.

## 4. 상태 전이

### 4-1 디스패치(Dispatch)
	준비 상태에서 대기하고 있는 프로세스 중 하나가 CPU를 할당 받아 실행 상태로 변하는 시점이다.
### 4-2 Time run out ( 선점, 시간 초과 )
	자신에 할당된 시간 만큼 CPU를 사용하고 준비상태로 변하는 시점이다
### 4-3 I/O 요구 ( 입 / 출력 발생 )
	프로세스가 CPU를 사용 중에 I/O 행위가 필요하여 보류 상태로 이동하는 시점이다.
### 4-4 Wake up
	I/O 작업이 완료되어 준비 상태로 이동하는 시점이다
### 4-5 Suspend
	대기 상태에서 운영체제에 의해 일시적으로 벗어나는 상태이다
### 4-6 Resume
	Suspended에서 프로세스 활성화 상태로 다시 복귀

## 5. 장치 및 기술
	
### 5-1 스풀(Spool)
	입출력(I/O) 장치와 속도 차를 극복하기 위한 장치로 대부분 하드디스크가 중재한다.
	스풀은 영역, 스풀링(Spooling)은 행위 자체, 스풀러(Spooler)는 프로그램이다
### 5-2 버퍼링(Buffering)
	CPU와 입출력 장치와의 속도 차이를 줄이기 위해 메모리가 중재한다
### 5-3 채널(Channel)
	입출력만을 담당하는 소형 컴퓨터로 간단한 명령 구조와 레지스터를 가지고 있으며 입출력 장치와 통신하기 위한 간단한 장치로 구성되어 있다.

## 6. 프로세스의 자원 이동 순서

### 6-1 요청    
	프로세스는 특정 자원을 사용하기 전에 운영체제에게 자원을 요청한다.
### 6-2 사용
	프로세스가 요청한 자원을 운영체제 할당 하면 자원을 사용한다
### 6-3 해제
	프로세스는 사용한 자원을 다른 프로세스를 위해서 자원 사용을 해제한다.
***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}