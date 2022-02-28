---
title:  "[ Jekyll ] liquid warning 처리 " 

categories:
  - Error
tags:
  - [Jekyll ,Error]

toc: true
toc_sticky: true

date: 2022-02-21
last_modified_at: 2022-02-21
---

📝Jekyll에서 liquid warning 처리하는 방법

---

### liquid warning Error

<img width="567" alt="image" src="https://user-images.githubusercontent.com/88019314/154887227-66744162-a7c4-4e5d-a616-3dd57f6a9ab7.png">

### Error 해결방법
{% raw %}
파일에 "{{, }} 가 들어 있는 경우 jekyll 엔진이 경고 메시지를 출력하고,
사이에 있는 {{ site.categories.['create-web'] }} 는 무시가 된다.
{% endraw %}

liquid parsing(구분분석)을 하지 않기 위해서는 문장 앞뒤로 다음과 같은 tag를 추가해 주면 warning과 출력 문제를 해결할 수 있다.

### 변경 전

<img width="508" alt="image" src="https://user-images.githubusercontent.com/88019314/154890743-93ac35fa-b03a-49f1-b207-d6c0eeb5990a.png">

### 변경 후

<img width="491" alt="image" src="https://user-images.githubusercontent.com/88019314/154890667-9ca9309b-fc1f-42db-8b51-245fa9b04b1c.png">
    





***
<br>

    개인 공부 기록용 블로그입니다. 오류나 틀린 부분이 있을 경우 
    댓글 혹은 메일로 지적해주시면 감사하겠습니다! 😄

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}