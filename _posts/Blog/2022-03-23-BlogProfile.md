---
title:  "프로필 사진 및 모양(곡률) 바꾸기" 

categories:
  - Blog
tags:
  - [Blog, Github,Jekyll]

toc: true
toc_sticky: true

date: 2022-03-23
last_modified_at: 2022-03-23
---

---
## 프로필 사진 변경

먼저 프로필 사진을 바꿔보도록 하자.
프로필 사진에 들어갈 원하는 사진을 골라 /assets/에 업로드를 한다.

만약 사진의 픽셀을 조정하고 싶다면 , 맥북 기준으로 미리보기를 연다음 픽셀을 조정하면 된다.
<br>
나 같은 경우 높이 732 , 너비 549로 설정해주었다.
사진을 /assets/에 업로드를 하였다면 이제 /_config.yml 파일을 검색하여 수정해주자.
<br>#Site Author을 검색하면 쉽게 찾을 수 있다.

~~~yml
author:
  name             : "공부하는 공돌이📖"  
  avatar           : "/assets/images/Profile.png"
  bio              : " Development Diary 🧸"
  #location         : "Seoul, South Korea"
~~~

avatar에, 내가 사진 파일을 올린 경로를 복사해두자.

~~~yml
 avatar           : "/assets/images/Profile.png"
~~~

## 프로필 모양(곡률) 변경
_sass/minimal-mistakes/_sidebar.scss을 검색해서 수정해주자.

~~~scss
/*
   Author profile and links
   ========================================================================== */

.author__avatar {
  display: table-cell;
  vertical-align: top;
  width: 36px;
  height: 36px;

  @include breakpoint($large) {
    display: block;
    width: auto;
    height: auto;
  }

  img {
    max-width: 200px; // 프로필 크기 바꾸기
    border-radius: 50%; // 프로필 곡률 , 작아질수록 사각형에 가까워짐

    @include breakpoint($large) {
      padding: 5px;
    }
  }
}
~~~
여기도 Author profile and links를 검색하면 쉽게 찾을 수 있다.

📌max-width를 바꾸면 내 프로필 사진의 최대 크기를 바꿀 수 있다.
단, 내 sidebar보다 더 커지지는 않는다.

📌border-radius가 낮아질수록 사각형에 가까워진다.
50%면 완전한 원형이 된다.

📌breakpoint의 padding, border를 바꿔주면 프로필 사진 주변의 테두리를 바꿀 수 있다.

~~~scss
max-width: 200px; // 프로필 크기 바꾸기
border-radius: 50%; // 프로필 곡률 , 작아질수록 사각형에 가까워짐
~~~
나는 이 부분을 위와 같이 각각 바꿨다.
***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}
