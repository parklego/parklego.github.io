---
title: React-Native
author: parklego
date: 2024-03-01
category: til
layout: post
---

### 개발환경 셋팅

> 설치

1. 홈브루 설치

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

   변경사항을 적용 시켜준다. 그리고 터미널을 재시작하자.

   ```
   source ~/.zshrc
   ```

2. 비주얼 스튜디오 코드 설치

3. Node 설치

4. 자바 SDK 설치

   @ 안드로이드 빌드 도구를 위해 설치

   - 자바 17버전 설치

     `brew install openjdk@17`

   - 자바 환경 변수 설정

     `open ~/.zshrc`

     ```
     export JAVA_HOME=/opt/homebrew/Cellar/openjdk@17/17.0.3/libexec/openjdk.jdk/Contents/Home
     export PATH=${PATH}:$JAVA_HOME/bin
     ```

   - shell 변경 사항 적용

     `source ~/.zshrc`

   - 자바 버전확인

     `java -version`

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

<br/>

최종 빌드 및 배포를 위해서는 안드로이드 스튜디오와 Xcode를 사용해야 한다.

플러터의 경우에는 네이티브언어가 없으면 자체 엔진으로 네이티브 도구를 이용하지 않고 빌드가 가능하다.

<br/>

> 실행

기본적인 개발 환경 셋팅이 됐으면, 프로젝트를 만들자.

```
npx react-native init 프로젝트_이름 --template react-native-template-typescript

npx react-native doctor // 점검
```

<br/>

> 에러 해결

✖ Adb - No devices and/or emulators connected. Please create emulator with Android Studio or connect Android device.

- 안드로이드 스튜디오에서 에뮬레이터 실행 후, `npx react-native run-android` 하여 연결

✖ Android SDK - Required for building and installing your app on Android

- Android Studio > Tools > SDK Manager > SDK tools > Android SDK Command-line Tools 설치

✖ xcode에 대한 에러

- ios폴더에서 `pod install`
