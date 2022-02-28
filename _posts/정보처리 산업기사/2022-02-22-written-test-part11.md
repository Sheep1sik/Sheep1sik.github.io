---
title:  "[ 필기 ] 주기억장치 사용 방식 " 

categories:
  - Data processing
tags:
  - [주기억장치, 정보처리산업기사, 자격증]

toc: true
toc_sticky: true

date: 2022-02-24
last_modified_at: 2022-02-24
---
강의를 듣고 정리한 필기입니다. 😀 지식 공유보단 개인적인 복습을 목적으로 포스팅하였습니다.

---
<img width="583" alt="Pasted Graphic 6" src="https://user-images.githubusercontent.com/88019314/155453043-1515df6e-10fc-4f52-a537-3e09ee05dbc1.png">
<br>
## 1. 고정 분할( 정적 분할 ) 할당 기법
	주기억장치의 크기를 다르게 분할하되 항상 고정된 크기를 갖는 형태로 분할하는 방식이다.
	분할된 영역이 고정되어 있으므로 프로그램이 적재되고 남는 공간이 생긴다.
	프로그램이 주어진 분할 안에 다 들어갈 수 없는 경우가 생길 수 있다.
	프로그램이 실행되기 위해서는 그 전체가 주기억장치에 위치하고 있어야 한다.
	내부, 외부 단편화가 모두 존재한다.
	단편화가 많아 효율적이지 못하다.
	분할된 최대 영역보다 큰 프로그램은 적재할 수 없다.

### 1-1 단편화(Fragmentation)
	주기억장치 상에서 번번하게 기억장소가 할당되고 반납됨에 따라 기억장소들이 조각들로 나누어져서 사용하지 못하는 공간이다.
		
### 1-2 내부 단편화(Internal Fragmentation)
	이미 정해진 크기에 프로그램을 할당하고 남은 기억 공간으로 사용되지 못하는 공간이다.

### 1-3 외부 단편화(External Fragmentation) 
	사용 가능한 분할 영역은 있지만 프로그램의 크기가 커서 사용하지 못하는 기억 공간이다.

<img width="668" alt="Pasted Graphic 7" src="https://user-images.githubusercontent.com/88019314/155453048-b2982de8-0eb6-4192-8cb0-0c4be4ca66e0.png">
<br>

## 2. 가변 분할 ( 동적 분할 ) 할당 기법
	프로그램의 크기에 따라 주기억장치 분할 크기를 동적으로 분할하는 방식이다.
	미리 크기를 결정하지 않고 실행할 프로세스의 크기에 맞게 기억 장소를 분할한다.
	외부 단편화만 존재한다.
	기억장소 활용 율이 높아진다.
	고정 분할 방식에 비해 실행될 프로세스 크기에 대한 제약이 완화된다.
	주기억장치의 크기를 넘지 않는 범위에서 큰 프로그램을 적재할 수 있다.

 <img width="647" alt="Pasted Graphic 9" src="https://user-images.githubusercontent.com/88019314/155453054-3b8f5850-1d47-4f16-9ee5-1c5644029e49.png">
 <br>
### 2-1 주기억장치 관리 레지스터
	주기억장치는 물리적으로 연속적인 공간이다.	
	주기억장치의 분할 영역, 프로그램이 적재되는 위치, 프로그램이 시작되는 위치 등을 CPU내에 레지스터가 기억하고 있다.
### 2-2 경계 레시즈터 (Boundary Register)
	사용자 영역에 존재하는 프로그램이 운영체제 영역을 침범하지 못하도록 한다.
### 2-3 차폐 레지스터 (Fence Register)
	분할된 영역을 다른 프로그램이 사용하지 못하도록 분할 영역의 위치(주소)를 기억한다.

### Coalescing 예시
<img width="646" alt="Pasted Graphic 12" src="https://user-images.githubusercontent.com/88019314/155453060-272cbf91-eb64-4762-acf6-f32f054df729.png">
<br>
### Comapction 예시
<img width="679" alt="Pasted Graphic 13" src="https://user-images.githubusercontent.com/88019314/155453068-67d2fce9-03fb-450d-93ff-bd0c9ea0f96f.png">
<br>
### 2-4 베이스 레지스터 (Base Register)
	주기억장치에 적재된 프로그램의 시작 위치를 기억하고 있다.
	
### 2-5 재배치 레지스터 Relocation Register)
	프로그램이 한 영역에서 다른 영역으로 옮겨지더라도 명령의 주소 부분을 바꾸지 않고 정상적으로 실행되 수 있도록 한다.

<img width="612" alt="Pasted Graphic 10" src="https://user-images.githubusercontent.com/88019314/155453083-b5d5e63e-f9e3-4806-90dc-4d47632dd904.png">
***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}