# Gradle에서 APK 이름 설정

이런 간다한 방법이 있다.

```groovy
android {
    ...
    defaultConfig {
        ...
        setProperty("archivesBaseName", "AppNameHere")
    }
    ...
}
```

```groovy
setProperty("archivesBaseName", "AppNameHere-$versionName")
```



[https://www.tanelikorri.com/tutorial/android/set-apk-filename-in-gradle/](https://www.tanelikorri.com/tutorial/android/set-apk-filename-in-gradle/)

