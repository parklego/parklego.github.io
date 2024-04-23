---
title: CSS
author: parklego
date: 2024-03-01
category: til
layout: post
---

## 텍스트에 자연스럽게 gradient 넣기

1. 백그라운드 영역에 먼저 그라디언트를 넣어준다.

   ```
    background: linear-gradient(to bottom, #194c33, #bbb); // 예시
   ```

2. 아래와 같이 속성을 넣어준다.

   ```
   -webkit-background-clip: text; // 텍스트 내부에만 배경 이미지를 적용하도록 지정
   -webkit-text-fill-color: transparent; // 글씨 투명하게 지정
   ```
