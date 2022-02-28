---
title:  "[ Error ] failed to push some refs to" 

categories:
  - Error
tags:
  - [Github ,Error]

toc: true
toc_sticky: true

date: 2022-02-22
last_modified_at: 2022-02-22
---

📝 error:failed to push some refs to 해결 방법

---
### Error:failed to push some refs to

<img width="567" alt="image" src="https://user-images.githubusercontent.com/88019314/155054017-863e5998-b268-4154-9cec-a37bc6faa99b.png">

이와 같이 push를 했을 때 에러가 발생하는 경우가 있다

이는 원격저장소(github)에 내 로컬(내컴퓨터)에는 없는 파일이 있을 때 내 파일을 push 할 면 발생하는 오류이다.

이럴땐 원격저장소에서 내 로컬에 저장하지 않은 파일을 pull한 후 원격저장소에 다시 push를 해야한다.

### Error 해결방법
    git pull '원격 저장소 별칭(보통 origin)' master

그 이후 push 가능

    git add .
    git commit -m "커밋 메세지"
    git push '원격 저장소 별칭(보통 origin)' master


***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}