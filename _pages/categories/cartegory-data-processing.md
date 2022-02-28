---
title: "정보처리 산업기사"
layout: archive
permalink: categories/data-processing
author_profile: true
sidebar_main: true
---

<!-- 공백이 포함되어 있는 카테고리 이름의 경우 site.categories['a b c'] 이런식으로! -->

***

강의를 듣고 정리한 필기입니다. 😀 지식 공유보단 개인적인 복습을 목적으로 포스팅하였습니다.

{% assign posts = site.categories['Data processing'] %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}