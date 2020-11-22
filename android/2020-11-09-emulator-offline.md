## Emulator offline

```
> adb devices
emulator-5554 offline
```

adb와 scrcpy를 자주 사용하는 필자로서는 `emulator offline` 라인이 달갑지 않다.

구글링하면 여러가지 해결책이 나오지만, 대부분 해결하지 못하거나 Windows 환경에서나 동작한다고 나온다. 때문에 해결책을 남기고자 한다.

### 해결

- emulator-5554에 대당하는 에뮬레이터를 Android Studio에서 실행한다. AVD가 여러개 설정되어 있다면 어느 것인지 알수가 없다. 하나 하나 실행해 보는 수밖에 없다. 에뮬레이터가 잘 실행되면 그 에뮬레이터는 emulator-5554가 아니다. offline이 뜬 에뮬레이터는 에러를 뱉는다.

- ```
  Error while waiting for device: AVD Galaxy_S10_API_29 is already running. // 이미 실행중이야.
  If that is not the case, delete the files at // 그렇지 않으면 다음 위치에서 모든 lock 파일을 삭제해.
     /Users/xxx/.android/avd/Galaxy_S10_API_29.avd/*.lock
  and try again. // 다시 시도해봐.
  ```

  위와 같은 에러를 뱉었다면 offline된 에뮬레이터가 맞다.

  에러를 잘 보자. 해당 경로의 `lock파일들을 모조리 삭제`하란다. 그렇게 해보자.

- Android studio를 재시작하자. 그러면 office은 사라지고 현재 연결되어 있는 디바이스들만 볼 수 있을 것이다.