---
title: React-Native
author: parklego
date: 2024-03-01
category: til
layout: post
---

### 개발환경 셋팅

1. 홈브루 설치

2. 비주얼 스튜디오 코드 설치

3. Node 설치

4. 자바 SDK 설치

   @ 안드로이드 빌드 도구를 위해 설치

5. Xcode 설치

   @ IOS 앱 개발을 위해 설치

6. 루비 설치

   @ iOS 앱 개발을 위해서는 CocoaPods라는 의존성 관리 도구 필요

   @ CocoaPods는 Ruby로 작성되어 있음

   @ rbenv를 설치해서 관리

7. 코코아팟 설치

   @ 오브젝트-c로 구현된 네이티브 모듈 빌드를 위해 설치

   @ 원격저장소에 호스팅된 각종 패키지를 받기 위해 설치

8. 워치맨 설치

   @ 변경사항 자동 탐지 반영하기 위해 설치 (핫리로딩)

최종 빌드 및 배포를 위해서는 안드로이드 스튜디오와 Xcode를 사용해야 한다.

플러터의 경우에는 네이티브언어가 없으면 자체 엔진으로 네이티브 도구를 이용하지 않고 빌드가 가능하다.

<br/>

> 설정

silicon mac은 기본 경로를 opt/homebrew로 가져가야 한다.

```
arch -arm64e /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

이제 모든 brew 명령어 앞에 arch -arm64e를 붙여야 한다. alias를 등록하자.

```
open ~/.zshrc
```

```
alias brew="arch -arm64e brew"
```

silicon mac에서 homebrew 기본 경로를 /usr/local에서 /opt/homebrew로 변경해야한다.

```
export PATH=/opt/homebrew/bin:$PATH
```

변경사항을 적용 시켜준다. 그리고 터미널을 재시작하자.

```
source ~/.zshrc
```
