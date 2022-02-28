---
title:  "[ 필기 ] 디스크 관리 part.3 " 

categories:
  - Data processing
tags:
  - [프로세스, 정보처리산업기사, 자격증]

toc: true
toc_sticky: true

date: 2022-02-24
last_modified_at: 2022-02-24
---
강의를 듣고 정리한 필기입니다. 😀 지식 공유보단 개인적인 복습을 목적으로 포스팅하였습니다.

---
## 1. 하드디스크
	플로피 디스크에 비해 대량의 자료를 기억할 수 있고, 고속으로 읽고, 쓸 수 있다.
	자성체로 코딩된 딱딱한 알루미늄 원판을 저장 매체로 사용하여 자기 방식으로 데이터를 저장한다.
	컴퓨터 내부에 고정되어 있는 자기 디스크 장치를 회전하는 디스크 판 위로 읽기/쓰기 헤드가 움직이면서 디스크 표면에 데이터를 저장하거나, 디스크에 저장되어 있는 데이터를 읽어 온다.

<img width="479" alt="(Cylinder)" src="https://user-images.githubusercontent.com/88019314/155455446-6701d426-cf79-4c7a-b907-d2aac2498e72.png">
<br>

## 2. 하드디스크 구성 요소
	헤드(Head), 액세스 암(Access Arm), 디스크(Disk), 트랙(Track),섹터(Sector)

### 실린더(Cylinder)
	여러 개의 디스크에서 같은 지름을 갖는 트랙의 집합으로, 
	동시에 헤드가 접근하는 부분으로 실린더의 개수는 트랙의 개수와 일치한다.
	트랙이 100개이면 실린더도 100개가 된다.
### 클러스터(Cluster)
	여러 개의 섹터를 하나의 블록으로 묶어서 블록 단위로 접근하게 되는데, 이 블록을 클러스터라고 한다.

## 3. 하드디스크의 용량 계산
	실린더 개수와 면의 개수를 알려 줄 경우
	하드디스크의 총 용량 = 실린더의 개수 x 면의 수 x 트랙당 섹터 개수 x 섹터 크기

<img width="729" alt="스크린샷 2022-02-23 오후 9 09 40" src="https://user-images.githubusercontent.com/88019314/155455448-c9309c1d-da07-465d-ab9e-19fea0fdf902.png">
<br>

    = 2^2 x 2^15 x 2^4 x 2^9 => 2^34 => 2^4 x 2^30 => 16 x GB => 16GB
	
	헤드 개수와 실린더의 개수를 알려 줄 경우
		하드디스크의 총 용량 = 헤드 개수 x 실린더의 개수 x 면의 수 x 트랙당 섹터 개수 x 섹터 크기   

<img width="654" alt="Pasted Graphic 28" src="https://user-images.githubusercontent.com/88019314/155455456-051e7f1e-c2fd-4cd3-94d7-e4391fa15f39.png">
<br>

	= 4 x 1024 x 256 x 1024 => 2^2 x 2^10 x 2^8 x 2^10 => 2^30 => 1GB

	디스크 개수와 트랙 개수를 알려 줄 경우(면의 수 = 2n , n = 디스크 개수)
		하드디스크의 총 용량 = 2 x 디스크 개수 x 트랙 개수 x 트랙당 섹터 개수 x 섹터 크기

<img width="693" alt="Pasted Graphic 29" src="https://user-images.githubusercontent.com/88019314/155455460-64e3ba43-aa8d-4606-8f93-59c4bf672abd.png">
<br>

	= 2 x 8 x 512 x 256 x 512 =>  2^1 x 2^3 x 2^9 x 2^8 x 2^9 => 2^30 => 1GB

	디스크 개수와 트랙 개수를 알려 줄 경우 (면의 수 = 2n -2)
		하드디스크의 총 용량 = ((2 x 디스크 개수)-2) x 트랙 개수 x 트랙당 섹터 개수 x 섹터 크기

<img width="689" alt="Pasted Graphic 30" src="https://user-images.githubusercontent.com/88019314/155455464-ffdbcee3-749f-486d-85b6-45ebc5e44953.png">
<br>

	= (2 x 8 -2) x 512 x 1024 x 1024 => 7 x 2 x 512 x 1024 x 1024 => 2^1 x 2^9 x 2^10 x 2^10 => 7 x 2^30 = 7GB

	실린더의 개수와 트랙 개수를 알려 줄 경우
		자기 드럼 총 용량 = 실린더 개수 x 실린더당 트랙 개수 x 트랙당 섹터 개수 x 섹터 크기


<img width="723" alt="Pasted Graphic 31" src="https://user-images.githubusercontent.com/88019314/155455469-ca1ac3cf-d9c8-4c9b-a164-42b81cc50590.png">
<br>

	= 4 x 100 x 10 x 180 => 720,000 => 720KB

## 4. RAID (Redundant Array of Independent Disks)
	여러 대의 하드디스크가 있을 때 동일한 데이터를 다른 위치에 중복해서 저장하는 방법으로 여러 개의 하드디스크를 마치 하나의 디스크처럼
	사용하는 것으로 입출력 속도 및 안정성을 개선시킨 기술 장치이다.

### 4-1 RAID 종류

#### RAID -0
	데이터를 여러 세그먼트로 분할해서 저장하는 방식(스트라이핑)이다.
	중복 저장과 에러 검출 및 교정이 없는 방식이다.

#### RAID -1
	두 개의 물리적인 디스크에 각각 중복 저장하는 방식이다.
	디스크 미러링(Disk Mirroring) 방식이며 높은 신뢰도를 갖는 방식이다.

#### RAID -2
	해밍 코드 방식을 사용하여 디스ㅡ의 데이터 에러 검증에 사용하는 방식이다.
	해밍코드 - ECC(Error Correction Code : 오류 정정 코드)

#### RAID -3
	스트라이핑 방식으로 디스크에 저장하는 방식
	패리티 정보는 별도의 디스크에 저장한다.
	패리티 디스크의 패리티 단위는 바이트 단위

#### RAID -4
	블록 단위로 나누어 저장하며, 패리티 정보를 별도의 디스크에 저장한다.
	패리티 디스크의 패리티 단위는 블록 단위

#### RAID -5
	스트라이핑 방식 저장, 패리티 정보는 모든 하드디스크에 나누어 저장한다.
	패리티 블록들을 여러가지에 분산 저장하는 방식이며 단일 에러 검출 및 교정이 가능한 방식이다.

#### RAID -6
	RAID -5의 패리티를 이중 구조로 구축하여 데이터 보호성을 높인 방식이다.

#### RAID -SAFE33
<img width="631" alt="Pasted Graphic 33" src="https://user-images.githubusercontent.com/88019314/155455479-34c330d1-9501-4a82-b63c-c062c8b8ca36.png">
<br>

#### RAID -SAFE50
<img width="601" alt="Pasted Graphic 32" src="https://user-images.githubusercontent.com/88019314/155455483-a047ecb0-a686-48a0-8b5d-fe8a966a1fad.png">
<br>

#### RAID -1 + 0
<img width="475" alt="Pasted Graphic 34" src="https://user-images.githubusercontent.com/88019314/155455493-b367f0af-ba43-46cd-8fb3-9b58f5ea4349.png">
<br>

#### RAID -0 + 1 
<img width="522" alt="Pasted Graphic 35" src="https://user-images.githubusercontent.com/88019314/155455503-aba1aeff-dc53-4fbc-b212-8a1cf257a481.png">
<br>

## 5. 광디스크 시스템
	빛의 반사나 굴절을 이용하여 자료를 읽어 내거나 기록할 수 있는 광 저장 매체,  드라이브 등 관련 장치 전부를 의미한다.

### 5-1 광디스크 시스템 특징
	광디스크는 정보를 읽어 들이는데 레지어 빔을 사용한다.
	기록 위치에 관계없이 랜덤 액세스가 가능하여 정보를 빨리 읽을 수 있다.
	블루레이 디스크, CD-ROM, DVD, HD-DVD, 레이저 디스크 등과 같은 저장 매체에 기록한다.
	대량의 정보 저장이 가능하다.
	전기 신호를 이용하여 무작위 접근한다.
	파일 갱신이 용의하며, 영구 보존이 가능하다.
	자료의 검색, 보존에 사용된다.

### 5-2 광디스크의 회전 속도 제어 기술
<img width="717" alt="Pasted Graphic 36" src="https://user-images.githubusercontent.com/88019314/155455512-083ec47e-229f-4a3e-b7b4-a4b4cbc2561d.png">
<br>

	광디스크는 원형이다. 회전하는 동안 디스크의 안쪽은 천천히 회전되며, 바깥쪽은 빠르게 회전된다

#### 등각 속도 (CAV)
	안쪽과 바깥쪽의 같은 용량으로 저장되도록 디스크의 안쪽과 바깥쪽의 밀도를 다르게 하여 트랙 면적이 다르더라도
	모든 트랙이 같은 용량을 사용한 기술이다.

#### 등선 속도 (CLV)
	안쪽과 바깥쪽의 다른 용량으로 저장되도록 디스크의 안쪽과 바깥쪽의 밀도를 같게 하여 트랙 면적에 따라 다른 용량을
	저장 할 수 있도록 한것이다.

### 5-3 등각 속도와 등선 속도의 비교
<img width="736" alt="Pasted Graphic 37" src="https://user-images.githubusercontent.com/88019314/155455523-118aa05e-3b3f-40a7-8894-314a031b64fc.png">
***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}