# Kotest 사용

안드로이드에서 Kotest 를 사용하려면 3 가지 설정이 필요합니다.

- 안드로이드 스튜디오 플러그인 설치
- 라이브러리 추가
- JUnit Platform 그래들 플러그인 추가

## 안드로이드 스튜디오 플러그인

[Kotest 에서 만든 플러그인](https://plugins.jetbrains.com/plugin/14080-kotest) 입니다. 안드로이드 스튜디오에서 플러그인을 검색하여 손쉽게 설치 할 수 있습니다.

## 라이브러리 추가

```kotlin
dependencies {
  ...
	testImplementation("io.kotest:kotest-runner-junit5:$version")
  ...
}
```

## JUnit Platform 그래들 플러그인 추가

앱 수준의 build.gradle 에 플러그인을 추가합니다.

```kotlin
android.testOptions {
   unitTests.all {
      it.useJUnitPlatform()
   }
}
```

# 테스트 코드 작성

여러가지 스타일의 테스트 코드 작성법이 있습니다. 개인이나 팀에 맞는 스타일로 작성하시면 됩니다.  테스트 클래스가 어떤 부모클래스를 두느냐에 따라 작성 방법이 달라집니다.

![](https://kotest.io/assets/images/gutter_icons-0041d916c7c27f35d387a77b0bbb55c0.png)

## 참고

https://kotest.io/docs/intellij/intellij-plugin.html