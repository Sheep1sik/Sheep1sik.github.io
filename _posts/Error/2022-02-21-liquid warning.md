---
title:  "[ Jekyll ] liquid warning ์ฒ๋ฆฌ " 

categories:
  - Error
tags:
  - [Jekyll ,Error]

toc: true
toc_sticky: true

date: 2022-02-21
last_modified_at: 2022-02-21
---

๐Jekyll์์ liquid warning ์ฒ๋ฆฌํ๋ ๋ฐฉ๋ฒ

---

### liquid warning Error

<img width="567" alt="image" src="https://user-images.githubusercontent.com/88019314/154887227-66744162-a7c4-4e5d-a616-3dd57f6a9ab7.png">

### Error ํด๊ฒฐ๋ฐฉ๋ฒ
{% raw %}
ํ์ผ์ "{{, }} ๊ฐ ๋ค์ด ์๋ ๊ฒฝ์ฐ jekyll ์์ง์ด ๊ฒฝ๊ณ  ๋ฉ์์ง๋ฅผ ์ถ๋ ฅํ๊ณ ,
์ฌ์ด์ ์๋ {{ site.categories.['create-web'] }} ๋ ๋ฌด์๊ฐ ๋๋ค.
{% endraw %}

liquid parsing(๊ตฌ๋ถ๋ถ์)์ ํ์ง ์๊ธฐ ์ํด์๋ ๋ฌธ์ฅ ์๋ค๋ก ๋ค์๊ณผ ๊ฐ์ tag๋ฅผ ์ถ๊ฐํด ์ฃผ๋ฉด warning๊ณผ ์ถ๋ ฅ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ  ์ ์๋ค.

### ๋ณ๊ฒฝ ์ 

<img width="508" alt="image" src="https://user-images.githubusercontent.com/88019314/154890743-93ac35fa-b03a-49f1-b207-d6c0eeb5990a.png">

### ๋ณ๊ฒฝ ํ

<img width="491" alt="image" src="https://user-images.githubusercontent.com/88019314/154890667-9ca9309b-fc1f-42db-8b51-245fa9b04b1c.png">
    





***
<br>

    ๊ฐ์ธ ๊ณต๋ถ ๊ธฐ๋ก์ฉ ๋ธ๋ก๊ทธ์๋๋ค. ์ค๋ฅ๋ ํ๋ฆฐ ๋ถ๋ถ์ด ์์ ๊ฒฝ์ฐ 
    ๋๊ธ ํน์ ๋ฉ์ผ๋ก ์ง์ ํด์ฃผ์๋ฉด ๊ฐ์ฌํ๊ฒ ์ต๋๋ค! ๐

[๋งจ ์๋ก ์ด๋ํ๊ธฐ](#){: .btn .btn--primary }{: .align-right}