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

### 코어 컴포넌트

## Text

- 텍스트를 표현하기 위한 컴포넌트
- onPress 속성이 있어서 버튼과 같이 기능을 수행할 수 있지만, 시각 효과는 없다.

## SafeAreaView

- iOS 기기의 노치(notch) 영역이나 Android 기기의 상태 표시줄, 내비게이션 바 등의 영역을 피해서 콘텐츠를 렌더링할 수 있도록 도와주는 컴포넌트
- Android는 직접적으로 padding 등을 제어 할 수 있으나, Ios는 불가능하기에
  작업을 할때 추가적인 view를 넣고 작업하는 것이 좋다.

## ScrollView

- 콘텐츠가 화면 크기보다 클 때 스크롤을 통해 모든 콘텐츠를 볼 수 있게 해주는 컴포넌트
- 해당 컨텐츠를 wrapper 형식으로 감싸면 된다.

## Button

- 리액트와 다르게 onPress 속성을 사용한다.
- title 속성은 버튼의 텍스트를 나타낸다. 단, 필수 값이다.

## TouchableOpacity

- 터치가 일어나면, 컴포넌트 바탕색의 투명도를 변경한다.

## TouchableHighlight

- 터치가 일어나면, 컴포넌트의 배경색을 변경한다.

## TextInput

- 입력된 텍스트는 value 속성값으로 얻을 수 있다.
- 텍스트가 입력될 때, onChangeText 이벤트를 실행한다.
- editable false로 disable 처리 할 수 있다.
- 텍스트입력이 모두 끝나면 onEndEditing 이벤트를 호출한다.
- 자식요소를 가지지 못한다.

### 내장 APIs

## Alert API

- 알림 컴포넌트
- title 속성 필수값

## StyleSheet API

- 스타일을 적용하기 위한 API
- 캐시된 스타일 객체를 생성할 수 있다.

## Platform API

- 현재 앱이 어느 OS에서 동작하고 있는지 구분하는 API
- `Platform.OS` 속성을 통해 확인할 수 있다.
- `Platform.select` 속성을 통해 OS별로 다른 스타일을 적용할 수 있다.

  ```css
  padding: Platform.select({ios: 10, android: 20, });
  ```

## Dimensions API

- 디바이스의 크기와 화면의 크기를 구분하는 API
- `Dimensions.get('window')` 속성을 통해 확인할 수 있다.

### 스타일링

- 코어 컴포넌트 중 `View` 가 들어간 컴포넌트는 `backgroundColor` 속성을, `Text` 컴포넌트는 `color` 속성을 사용한다.
- 정적 스타일의 경우 StyleSheet.create 방식으로 구현하는 것이 효과적이다.
- 동적 스타일의 경우 인라인 스타일 방식으로 구현하는 것이 일반적이다.
- 스타일 속성에 배열로 담아서 정적,동적 스타일링을 결합하는 형식으로 사용하면 된다.
