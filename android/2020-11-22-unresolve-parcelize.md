# Unresolove @Parcelize

Kotlin의 `@Parcelize` 가 import되지 않을 때가 있다. 물론, app 수준의 `build.gradle.kts` 에는 아래와 같이 선언되어 있다.

```kotlin
id("kotlin-android-extensions")
kotlin("android")
```

위와 같을 땐 순서를 바꾸어 주자.

```kotlin
kotlin("android")
id("kotlin-android-extensions")
```

그럼 잘된다.