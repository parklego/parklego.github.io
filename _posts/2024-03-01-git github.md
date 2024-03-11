---
title: Git/Github
author: parklego
date: 2024-03-01
category: til
layout: post
---

## Jekyll을 사용하여 GitHub Pages 배포 및 테마적용

> 사전 준비

- Ruby 설치
- Jekyll 설치
- 테마 선택
  - [jamstackthemes.dev](http://jamstackthemes.dev)
  - [http://jekyllthemes.org/](http://jekyllthemes.org/)
- 코드블럭 선택
  - [https://spsarolkar.github.io/rouge-theme-preview/](https://spsarolkar.github.io/rouge-theme-preview/)
    <br/>

> 배포 및 테마 적용하기

1. github repository 생성

   - repository명은 github 아이디.github.io로 생성할 것
   - repository는 public 으로 할 것
   - ex) parklego.github.io

2. bundle 명령어 실행

   ```javascript
   bundle install
   bundle exec jekyll serve
   ```

3. 블로그 설정
   - \_conif.yml 파일에서 제목이나 이름 등을 변경
   - Gemfile 플러그인 설치하는 곳
