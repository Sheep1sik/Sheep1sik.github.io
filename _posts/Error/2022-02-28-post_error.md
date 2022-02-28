---
published: true
title:  " [ Error ] 깃허브 포스트 개시 안됨 해결 " 

categories:
  - Error
tags:
  - [Github ,Error]

toc: true
toc_sticky: true

date: 2022-02-28
last_modified_at: 2022-02-28
---

📝 깃허브 포스트 개시 안됨 해결

---


## 해결 방법

여기 아래 내용들은 기본적으로 지켜야 할 것들이다. 확인해보자.

* YEAR-MONTH-DAY-title.md 파일 제목 형식을 확인한다.
* 포스팅 날짜 맞게 입력했는지 확인한다.
* _post 폴더에 맞게 위치해 있는지 확인한다.
* 카테고리 맞게 입력 했는지, 해당 카테고리 존재하는지 확인해본다.

만약 위 내용에서의 문제가 없다면 아래 내용을 시도해보자.
나 같은 경우 1번과 2번을 추가해 성공했다.

* _config.yml에 futrue: true 추가
* 페이지 옵션(타이틀, 카테고리 적는곳)에 published: true 추가
* index.html에 공백이라도 추가해 변경사항 만들고 push
* jekyll build --verbose 로 Skipping 된 것 있나 확인

## 해결

<img width="330" alt="image" src="https://user-images.githubusercontent.com/88019314/155959709-0339f660-af67-497d-973f-9ab3f6f71554.png">
<br>
<img width="426" alt="image" src="https://user-images.githubusercontent.com/88019314/155959817-44b4924b-aa32-46d6-8ece-b8992b76f6ae.png">

***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}