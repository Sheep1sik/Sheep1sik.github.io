---
title:  "[ 필기 ] 운영체제의 종류별 특징 " 

categories:
  - Data processing
tags:
  - [운영체제 ,Unix, Linux, 정보처리산업기사, 자격증]

toc: true
toc_sticky: true

date: 2022-02-22
last_modified_at: 2022-02-22
---
강의를 듣고 정리한 필기입니다. 😀 지식 공유보단 개인적인 복습을 목적으로 포스팅하였습니다.

---
# 운영체제의 종류별 특징
## 1. Windows 계열 운영체제
	Windows 계열 운영체제는 개인용, 기업용, 워크스테이션용으로 출시된다.
	사용자가 컨트롤하는 마우스의 아이콘을 이용하여 소프트웨어를 실행시키는 편리한 인터페이스를 지원하는 것이 특징이다
	문제점이 발견되었을 시 수정에 시간이 걸린다는 단점이 있다.
	UNIX 계열의 운영체제에 비하여 시간적 차이를 이용하고 있는 악성 해커들이
	있어 보안애 취약하다는 문제점이 지속적으로 제기되고 있다.

## 2. UNIX/Linux 계열 운영체제
	UNIX는 1960년대 AT&T Bell 연구소, MIT 그리고 General Electric이
	공동 연구로 개발에 착수하여 개발한 운영체제이다.
	C 언어로 재이식되어 대중화의 기반을 마련되었고, 1970년대 AT&T가 본격적으로 UNIX 시스템을 판매하게 되었다.
	많은 변화를 거쳐 SYSTEM V 계열과 BSD 계열로 발전해 왔으나, 현재는 이 둘의 장점을 통합한 버전의 UNIX가 배포되고 있다.
	Linux는 UNIX의 호환 커널이다. 
	Linux는 수천 명 이상의 개발자들이 코드를 보고 갱신하고 있다
	Linux는 버그 발생 시 다수의 개발자가 수정에 참여하여 빠른 업데이트가 가능하지만, Windows와 같은 체계적인 지원이 상대적으로 부족하여 일반인들보다는 전문가들이 사용하고 있다.

### 2-1 UNIX와 Linux의 차이점

<img width="716" alt="Pasted Graphic 11" src="https://user-images.githubusercontent.com/88019314/155075557-2e2ea40e-5d35-47e2-9719-f043a6e85c57.png">
<br>
<a href = "https://license.youngjin.com/" > [출처]  이기적 무료 동영상 :  정보처리 산업기사 필기 2022 1-1-1 운영체제의 종류별 특징 </a>

## 3. Unix의 특징
    상당 부분 C 언어를 사용하여 작성되었으며, 이식성이 우수하다.
	( 어셈블리어 10%, C언어 90% )
	사용자는 하나 이상의 작업을 백그라운드에서 수행할 수 있어 여러개의 작업을 병행 처리할 수 있다.
	두 사람 이상의 사용자가 동시에 시스템을 사용할 수 있어 정보와 유틸리티들을 공유하는 편리한 작업 환경을 제공한다
	소스를 누구나 볼 수 있도록 설계된 개방형 시스템(Open System) 이다.
	(MS_DOS, MS-Windows는 Close System)
	표준이 정해져 있고 제품의 공급 업자가 많다.
	라이센스 비용이 저렴하다.
	커널(Kernel)의 크기가 비교적 작아서 이식성이 뛰어나다.
	Multi-Tesking : 여러 개의 프로그램을 동시에 수행할 수 있다.
	Multi-User : 여러 사용자가 동시에 사용할 수 있다.
	풍부한 네트워킹 기능이 존재한다.
	계층적(트리 구조)의 파일 시스템이다.
	사용자 위주의 시스템 명령어가 제공된다.
	쉘(Shell) 명령어 프로그램이 제공된다.

## 4. Unix의 기본 구성

### 4-1 커널 (Kernel)

	핵심 루틴으로, 하드웨어 보호기능, 사용자 서비스 제공, 프로세스 관리,
	메모리 관리, 네트워크(통신) 관리, 입출력 관리, 파일관리기능 등을 제공한다.

### 4-2 쉘 (Shell)

	사용자 명령의 입력을 받아 시스템 기능을 수행하는 명령 해석기로서 사용자와
	시스템 간의 인터페이스를 담당한다. 즉, 사용자와 커널 사이에서 중계자 역할을 한다.
	또한 여러가지의 내장 명령어를 가지고 있다.

### 4-3 유틸리티(Utility)

	문서 편집기, 데이터베이스 관리, 컴파일러, 네트워크(통신) 등을 제공한다.


## 5. Unix 파일 시스템
<img width="460" alt="Pasted Graphic 12" src="https://user-images.githubusercontent.com/88019314/155075943-c84f5ef2-8073-4658-86d4-5453bce30e82.png">
<br>
<a href = "https://license.youngjin.com/" > [출처]  이기적 무료 동영상 :  정보처리 산업기사 필기 2022 1-1-1 운영체제의 종류별 특징 </a>

### 5-1 Boot 블록
	부팅의 관련된 내용이 들어가 있는 블록

### 5-2 슈퍼 블록
	파일 시스템의 크기, I-node 테이블의 크기, Free Block 리스트 등을 기록된다

### 5-3 실린더 그룹 정보 블록
	사용 블록의 정보, 통계적 정보가 기록된다.

### 5-4 I-node 테이블
	파일의 정보를 기록한 파일 정보 테이블이 기록된다.

## 6. 파일과 디렉토리의 권한

<img width="681" alt="76 32420 19-9-22 19•8-25 19-9-24" src="https://user-images.githubusercontent.com/88019314/155076109-6918416a-b8d4-4e58-a0ca-1b72f2ec89b7.png">
<br>
<a href = "https://license.youngjin.com/" > [출처]  이기적 무료 동영상 :  정보처리 산업기사 필기 2022 1-1-1 운영체제의 종류별 특징 </a>

    1. UID : 사용자 ID ( 파일 소유자의 식별번호 )
	2. GID : 그룹 ID ( 파일 소유 그룹의 식별번호 ) 
	3. Protection : 파일 보호 모드
	4. 파일 링크 수 
	5. 블록 주소 : 파일의 실제 데이터가 있는 위치를 가리키고 있다.
	6. 파일의 크기
	7. 처음 생성 시기 ( 파일이 만들어진 시간 )
	8. 마지막 사용 시기 ( 파일을 최후로 접근(Access)한 시간 )
	9. 최종 수정 시기 ( 파일의 최종 수정 시간 )
	10. 파일 속성(타입) :  알번 퍼알(-), 디렉토리(d), 소켓(s), 링크 파일(l), 장치(l, c, b)

![image](https://user-images.githubusercontent.com/88019314/155076498-b251e220-6af7-408d-9ee9-d120c5928029.png)
<br>
<a href = "https://dololak.tistory.com/293" > [출처] https://dololak.tistory.com/293 </a>

## 7. 복사와 링크의 차이점
	cp는 복사하는 명령어이고, ln은 파일이나 디렉토리를 링크 거는 것이다.
	ln에는 hard link와 symbolic link가 있다.

### 7-1 예시
$ cp A.txt B.txt

	A.txt와 B.txt는 각각의 독립적인 파일로 존재한다.

$ In C.txt D.txt

	Hard Link가 설정되고, D.txt파일을 C.txt 파일에 의존적이 된다.
    C.txt 소유자나 그룹의 권한 등을 변경하게 되면 D.txt도 자동적으로 변경된다.
    C.txt를 삭제제할 경우 D.txt는 독립적으로 그대로 보존된다

$ ln -s E.txt F.txt

	Symbolic Link가 설정된다.
	E.txt의 소유자나 그룹의 권한 등을 변경하더라도 F.txt는 변경되지 않는다.
	E.txt를 삭제할 경우, F.txt는 사용할 수가 없으며 쓰레기 파일이 되어 버린다

### 7-2 하드 링크(Hard Link)

	똑같은 파일을 복사하는 것으로, 원본을 삭제해도 복사본이 그대로 남아있다.
	처음 생성된 파일의 링크 수는 1, 링크를 추가할 때마다 1씩 증가한다.
	실제 파일의 내용을 링크한다. 링크하면 파일의 링크수가 증가한다.
	해당 링크 파일을 삭제하면 링크수가 감소한다.
	해당 링크수가 0에 도달하면 원본 파일도 삭제한다
	디렉토리는 링크할 수 없으며 주로 일반 파일을 링크한다
	
### 7-3소프트 링크(Soft Link , 심볼릭 링크 , Symbolic Link)

	원본의 파일에 대한 위치 정보만을 가지고 있는 것으로 다른 파일에 대한 포인터형이다.
	원도우 바로가기와 유사한 개념으로 파일의 정보만을 Link 한다.
	링크명에 @가 붙는다.
	링크가 삭제되어도 원본 파일에 영향을 주지 않는다.
	주로 디렉토리도 링크할 때 사용한다.

## 8. Linux의 특징
	Unix가 중대형 컴퓨터에서 사용되는 것과는 달리, 리눅스는 위크스테이션이나 개인용 컴퓨터에서 사용된다
	파일 시스템이나 기능의 일부는 Unix를 기반으로 하면서, 핵심 커널 부분은 유닉스와 다르게 작성되어 있다.
	Unix와 거의 유사한 환경을 제공하면서 무료이기 때문에 개발자 및 학교 등을 중심으로 급속히 사용이 확장되고 있다.
	리눅스 운영체제의 소스 코드를 완전 무료로 공개하여 세계적으로 약 천백만명이 넘는 프로그램 개발자 그룹을 형성하고 있다.
	리눅스 커널 스케줄러는 임의의 프로세스를 선점할 수 있으며 우선순위 기반 알고리즘이다.
	라눅스는 모놀리틱 커널을 사용하기 때문에 커널 코드의 임의의 기능을 동적으로 적제(Load)하여 사용할 수 없다.
	리눅스 운영체제는 윈도우 파일 시스템인 NTFS와 저널링 파일 시스템인 JFFS를 지원한다
	리눅스는 다중 사용자와 다중 프로세서를 지원하는 다중 작업형 운영체제이다.

<img width="926" alt="Pasted Graphic 14" src="https://user-images.githubusercontent.com/88019314/155077238-53c0fad9-0f97-4f2d-8185-df20b614f45d.png">

### 8-1 마이크로 커널 (Micro Kernel)
	메모리 관리, 스케줄링, 기본적인 네트워킹 등 최소한의 기능들만을 제공한다.
	추가 기능은 사용자 레벨이어서 작동하고자 하는 모듈들을 끼워 넣어서 운영체제를 확장할 수 있도록 한다.
	커널 코드의 임의의 기능들을 동적으로 적제(load)하여 사용할 수 있다.
	추가 기능을 모듈 단위로 개발하면 되기 때문에 다양한 환경에 적용하기 쉬운 장점을 가진다.
	마이크로 커널은 메세지를 전달하는 방식으로 자원에 접근한다.
	메세지를 전달하는 방식이므로 문맥 교환에 많은 오버헤드를 초래한다.

### 8-2 모놀리틱 커널(Monolithic Kernel)
	네트워크 스택과 파일시스템 디바이스드라이버 등을 커널 기본 기능으로 포함하는 방식이다.
	마이크로 커널에 비해서 성능이 빠르다.
	리눅스와 윈도우즈등이 모놀리틱 커널 방식으로 개발되고 있다.
	모놀리틱 커널은 시스템 콜(Call)을 이용해서 커널 기능을 이용한다.
	모놀리틱 커널은 구현이 간단하다.
	시스템 자원을 효율적으로 사용할 수 있다는 장점을 가지고 있다.
	모놀리틱 커널은 커널 코드의 임의의 기능들을 동적으로 적재(load)하여 사용할 수 없다.
	많은 기능을 포함하기 때문에 다양한 환경의 시스템에 적응하기 어렵다는 단점이 있다.

***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}