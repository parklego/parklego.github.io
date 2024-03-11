---
title: 웹 접근성
author: parklego
date: 2024-03-01
category: til
layout: post
---

웹 접근성(a11y)는 정보에 동등하게 접근하고 이해 할 수 있도록 보장하기 위해 중요하다.

- [wai-aria란?](https://story.pxd.co.kr/1588)
- [aria 사용방법](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques)
- 리액트 jsx에서 `wai-aria`를 지원한다.
- `aria-\*` 과 같은 어트리뷰트는 kebab-case로 작성해야한다.

### role

- 태그의 역할을 알려주는 속성
- 정해진 값만 사용하여야 한다.

### aria-label

- 스크린 리더기에 전달할 내용을 알려주는 속성
- 예를들어, 어코디언이 있으면 펼치기와 같이 `aria-label`를 통해 알려줄 수 있다.
- 주의할 점은 시멘틱 태그이거나, role 속성 값이 상호작용(interactive)을 하는 값일 때 aria-label을 붙일 수 있다는 것이다.
- [aria-label과 role을 쓰기 위한 규칙](https://velog.io/@a_in/WAI-ARIA-role-aria-label)

### tabindex

- `0` : 상호작용 가능한 요소 처럼 포커싱이 된다.
- `-1` : 포커싱에서 제외 된다.
- `양수` : 강제로 순서를 정한다. 그 이후에 브라우저의 포커싱 순서대로 잡힌다. 무조건 피해야함.

### img alt

- 이미지가 나오지 않을 때, 이미지에 대한 설명

### aria-required

- `true`인 경우, 스크린 리더기에 필수요소임을 알려주는 속성

<br/>
