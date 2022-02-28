---
title:  "[ 필기 ] 프로세스 스케줄링(Process Scheduling) Part.2 " 

categories:
  - Data processing
tags:
  - [프로세스 스케줄링, 정보처리산업기사, 자격증]

toc: true
toc_sticky: true

date: 2022-02-23
last_modified_at: 2022-02-23
---
강의를 듣고 정리한 필기입니다. 😀 지식 공유보단 개인적인 복습을 목적으로 포스팅하였습니다.

---
## 1. HRN(Highest Response-ratio Next) - 비선점형

### 1-1 HRN의 특징

	FIFO과 SJF의 단점을 보완하여 개발된 방법이다.
	HRN은 실행 시간 추정과 선점 기능 때문에 스케줄러가 복잡해지고 남은 시간 계산들을 저장해 놓아야 하는 단점을 보완하였다.
	HRN은 작업의 서비스 받을 시간과 그 작업이 서비스를 기다린 시간으로 결정되는 우선순위에 따라 CPU를 할당한다.
	HRN의 우선순위 공식은 다음과 같으며 계산 결과가 큰 작업에 우선순위를 부여한다

<img width="519" alt="Pasted Graphic 22" src="https://user-images.githubusercontent.com/88019314/155253515-991b8c79-44f8-4f67-85df-95b4dfce1ca3.png">
<br>

### 1-2 HRN 우선 순위 계산

<img width="440" alt="Pasted Graphic 23" src="https://user-images.githubusercontent.com/88019314/155253558-608488eb-432f-46da-9ab0-a454da1cebdc.png">
<br>

	우선순위 계산 식
	대기시간 + 실행시간 / 실행시간

	A = 10 + 18 / 18 = 1.555…
	B = 16 + 24 / 24 = 1.666…
	C = 8 + 19 / 19 = 1.421…

	우선 순위 : B -> A -> C

## 2. RR(Round-Robin) - 선점형

### 2-1 RR의 특징
	대표적인 선점형 방식이다.
	동일한 시간할당량(Time Slice)을 사용하는 시분할 처리 시스템에 효과적으로 적용된다.
	시간할당량 안에 작업을 마치지 않으면 준비 대기 리스트의 가장 뒤로 배치되는 방식이다.
	시간할당량이 크면 비 선점의 FIFO와 동일하다.
	시간할당량이 작으면 문맥 교환수와 오버헤드가 증가한다.
	적절한 응답시간을 보장해주는 대화식 사용자에게 효과적이다.

### 2-2 RR 평균 반환시간 계산 -1

<img width="437" alt="Pasted Graphic 24" src="https://user-images.githubusercontent.com/88019314/155253660-ac42bd79-2b4a-48e9-a0b9-68e0dddc0daa.png">
<br>

    임의로 시간 할당량은 10초로 가정하고 풀어보자

		대기 리스트
		A(10초) -> B(10초) -> C(5초) -> D(10초) -> E(1초) -> B(8초) -> D(2초)

		평균 실행시간  = 실행시간 총 합 / 작업 수
		10 + 18 + 5 + 12 + 1 / 5 => 46 / 5 

		평균 대기시간 =  (대기시간 - 도착시간) 의 총 합 / 작업 수
		0 + 20 + 6 + 19 + 16 / 5 => 61 / 5

		A의 대기시간 = 0
		B의 대기시간 = 10 + (5 + 10 +1) - 6 (도착시간)  => 20
		C의 대기시간 = (10 + 10) - 14 (도착시간) => 6
		D의 대기시간 = (10 + 10 + 5) + (1 + 8) - 15 (도착시간) => 19
		E의 대기시간 = (10 + 10 + 5 + 10) - 19 (도착시간) => 16

		평균 반환시간 = 평균 실행시간 + 평균 대기시간
		평균 반환시간 = 9.2 + 12.2 =. 1.4 이다

### 2-3 RR 평균 반환시간 계산 -2

<img width="441" alt="Pasted Graphic 25" src="https://user-images.githubusercontent.com/88019314/155253755-5ba59d8c-125f-469f-8bc7-8f6244b7e1ae.png">
<br>

	임의로 시간 할당량은 2초로 가정하고 풀어보자

		대기리스트
		P1(2초) -> P2(2초) ->  P1(1초) -> P3(2초) -> P2(2초)

		평균 실행시간  = 실행시간 총 합 / 작업 수
		3 + 4 + 2 / 3 => 9 / 3

		평균 대기시간 =  (대기시간 - 도착시간) 의 총 합 / 작업 수
		2 + 4 + 2 / 3 = 8 / 3

		P1의 대기시간 = 2  - 0 (도착시간)=> 2
		P2의 대기시간 = 2 + (1 + 2) - 1 (도착시간) => 4
		P3의 대기시간 = (2 + 2 + 1)  - 3 (도착시간) => 2

		평균 반환시간 = 평균 실행시간 + 평균 대기시간
		평균 반환시간 = 3 + 2.666… = 5.7 이다

## 3. SRT(Short Remaining Time) - 선점형

### 3-1 SRT의 특징
	작업이 끝나기까지 “ 남아 있는” 실행시간의 추정치가 가장 작은 프로세스를 먼저 실행하는 방식이다.
	서비스 받는 시간을 기록해야 하기 때문에 오버헤드 증가한다.
	평균 대기시간과 대기시간의 분산(편차의 제곱)도 크다.
	임계치(Threshold value)를 사용한다.

### 3-2 SRT 평균 반환시간 계산  

<img width="436" alt="Pasted Graphic 26" src="https://user-images.githubusercontent.com/88019314/155253823-ce76b42a-0ba4-4bd9-9a47-b562d91a61e7.png">
<br>

	대기기리스트
	A(1초) -> B(1초) -> C(3초) -> B(5초) -> A(23초)

	평균 실행시간  = 실행시간 총 합 / 작업 수
	24 + 6 + 3 / 3 => 33 / 3

	평균 대기시간 =  (대기시간 - 도착시간) 의 총 합 / 작업 수
	9 + 3 + 0 / 3 => 12 / 3

	A의 대기시간 = 1 + 3 + 5 -0 (도착시간) => 9
	B의 대기시간 = 1 + 3 - 1 (도착시간) => 3
	C의 대기시간 = 1 + 1 - 2 (도착시간) => 0

	평균 반환시간 = 평균 실행시간 + 평균 대기시간
	평균 반환시간 = 4 + 11 = 15

## 4. MFQ(Multi level Feedback Queue) - 선점형

### 4-1 MFQ의 특징
	짧은 작업이나 입출력 위주의 작업에 우선순위를 부여하기 위해 개발된 방식이다.
	큐( 대기 리스트 )가 여러 개이며 우선순위가 있다.
	각 큐마다 시간할당량이 존재하며 낮은 큐일수록 시간할당량은 커진다.
	각각의 큐들은 종속적으로 연결되어 있다.
	CPU를 시간할당량만큼 사용한 프로세스는 낮은 큐로 이동된다.
	맨 마지막 단계의 큐는 RR(라운드 로빈 스케줄러)를 사용한다.

### 4-2 MFQ의 운영
<img width="560" alt="Pasted Graphic 27" src="https://user-images.githubusercontent.com/88019314/155253931-7b22f012-fb6b-419e-815f-0d149fa788f5.png">
<br>

    맨 위에서 5 Queue 먼저 처리 그 이후 10 Queue로 이동

<img width="566" alt="Pasted Graphic 29" src="https://user-images.githubusercontent.com/88019314/155253939-44278cef-38b5-4954-b732-8fab4d82ec29.png">
<br>

    10 Queue에서 처리 그 이후 15 Queue로 이동

<img width="554" alt="Pasted Graphic 30" src="https://user-images.githubusercontent.com/88019314/155253946-4464eebc-62a8-4693-be4c-d81a0f670443.png">
<br>

    15 Queue에서 처리 후 마지막 20 Queue로 이동

<img width="525" alt="Pasted Graphic 32" src="https://user-images.githubusercontent.com/88019314/155253949-333e3cc2-f520-41c0-a5fc-950008af1332.png">
<br>
	
    70에서 RR을 돌려서 70 -> 50 -> 30 -> 10 -> 0 으로 작업이 끝난다

## 5. MLQ(Multi Level Queue) - 혼합형

### 5-1 MLQ(MQ)의 특징
	선점형, 비선점형 방식이다.
	우선순위가 가장 높은 큐에서는 비선점형으로 사용된다.
	우선순위가 낮은 큐에서는 선점형으로 사용된다.
	상위 큐가 우선순위가 가장 높은 큐로 신속한 처리를 필요로 하는 시스템 프로세스가 입력된다.
	중위는 대화형 프로세스, 하위는 일괄처리 프로세스가 입력된다.
	대기 리스트 간에 프로세스가 이동이 안 된다.
	
### 5-2 MLQ(MQ)의 운영

<img width="510" alt="Pasted Graphic 33" src="https://user-images.githubusercontent.com/88019314/155254284-f8250923-4dd7-4571-a758-e5a5fdddb8a2.png">
<br>

    상위 작업을 먼저 처리

<img width="505" alt="Pasted Graphic 34" src="https://user-images.githubusercontent.com/88019314/155254288-49404e62-4cf8-449e-a71a-1c1044709908.png">
<br>

    상위 작업을 다 처리한 후 중위 작업으로 넘어온다.

<img width="507" alt="Pasted Graphic 35" src="https://user-images.githubusercontent.com/88019314/155254293-9687b808-78c0-4f3c-bc13-c9947eb8ea4f.png">
<br>

    처리도중 상위 작업이 들어오면 중위 작업을 중단하고 상위 작업으로 넘어간다.
***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}