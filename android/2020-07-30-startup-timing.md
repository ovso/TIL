# 앱 시작 시간

앱이 콜드 스타트 하여 화면에 보여지기 까지 얼마나 걸릴까? 로그를 보면 쉽게 알 수 있다.

`콜드 스타트` :

```
2020-07-30 09:28:25:477 1387-1516/? I/ActivityTaskManager: Displayed io.github.ovso.xxx/.ui.main.MainActivity: +1s863ms
```

`웜 스타트`

```
2020-07-30 09:28:25:477 1387-1516/? I/ActivityTaskManager: Displayed io.github.ovso.xxx/.ui.main.MainActivity: +117ms
```

위의 로그가 액티비티가 보여지는 시간을 말한다. 

[https://developer.android.com/topic/performance/vitals/launch-time?hl=ko](https://developer.android.com/topic/performance/vitals/launch-time?hl=ko)

