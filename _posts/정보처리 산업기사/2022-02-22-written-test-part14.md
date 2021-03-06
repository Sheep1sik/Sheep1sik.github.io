---
title:  "[ 필기 ] 디스크 관리 part.1 " 

categories:
  - Data processing
tags:
  - [디스크관리, 정보처리산업기사, 자격증]

toc: true
toc_sticky: true

date: 2022-02-24
last_modified_at: 2022-02-24
---
강의를 듣고 정리한 필기입니다. 😀 지식 공유보단 개인적인 복습을 목적으로 포스팅하였습니다.

---
<img width="654" alt="(Access Arm)" src="https://user-images.githubusercontent.com/88019314/155454812-20216680-0c97-4f60-9d68-20ac356e2153.png">
<br>
## 1. 디스크 구조

### 트랙(Track)
    디스크의 회전축을 중심으로 동심원 모양으로 디스크의 종류마다 개수가 모두 다르다.
	일반적으로 200트랙(0 ~ 199 트랙)이다.

### 섹터(Sector)
	하나의 트랙을 몇 개로 분할한 블록으로 한 개의 섹터는 일반적으로 512byte ~ 1024byte 용량을 갖는다.

### IPL(Initial Program Loader)
	디스크를 접근할 때 디스크의 물리적인 정보를 제공한다.
	일반적으로 부트(Boot) 섹터라고 한다.
	물리적인 정보는 트랙수, 섹터수, 섹터당 byte 수 등이다.
	
### FAT(File Allocation Table)
	효율적인 저장을 위해서 여러개의 복사본을 가지고 있다.
	
### 디렉토리(Directory)
	디스크에 저장된 파일의 기본적인 정보를 수록하는 공간으로 파일명, 파일 속성, 작성 날짜, 작성 시간, 파일 위치, 파일의 크기 등의 정보를 갖는다.

### 실린더(Cylinder)
	회전축을 중심으로 같은 거리에 있는 트랙들의 집합이다.
	하드디스크처럼 여러개의 디스크 판을 사용할 때 사용하는 단어로 플로피 디스크처럼 한 장을 사용할 경우에는 트랙과 같은 말이다.
	
## 2. 드라이브
	디스크를 감싸고 있는 부분이다.

### 액세스 암 (Access Arm)
	읽기/쓰기 헤드를 움직여주는 막대

### 고정 축 (Boom)
	액세스 암들을 동시에 이동시키는 막대로 탐색시간(Seek time)은 고정축의 이동시간이 된다.

### 헤드 (Head)
	데이터를 읽어 내거나 기록하는 장치

## 3. 디스크 접근시간
	
### 탐색시간(Seek Time)
	디스크 상의 원하는 데이터를 액세스하기 위해 트랙 또는 실린더에 헤드를 위치시키는데 걸리는 시간

### 회전 지연 시간(Latency Time)	
	지정된 트랙에 위치한 헤드가 원하는 섹터에 위치시키는데 걸리는 시간으로 Rotational Delay Time 또는 RPM 지연 시간이라고도 한다.

### 전송 시간(Transmission Time)
	디스크로부터 주기억장치로 데이터가 이동하는 시간이다.

	검색 시간 (Search time) = 탐색시간 + 회전 지연 시간
	접근 시간(Access time) = 전송 시간 + 대기 시간(Waiting time)

## 4. 디스크 스케줄링 전략의 목적
	처리량을 최대화한다.
	응답시간을 최소화한다.
	응답시간의 편차를 최소화한다.

***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}