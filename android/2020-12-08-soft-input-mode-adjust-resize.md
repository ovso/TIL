## Manifest의 windowSoftInputMode, 코드로 설정하기

Android Navigation을 사용하게 되면 대부분 싱글액티비티를 유지하기 마련이다. 키보드가 올라오는 화면이 있고 그렇지 않은 화면이 있다. 키보드가 올라오는 화면은 아래와 같이 Manifest에 windowSoftInputMode의 설정이 필요할 때다 잦다. 설정에 따라 레이아웃을 안드로이드 플랫폼에 맡겨서 제어 하게 된다.

```xml
<Manifest
	...>
  <application
    ...>
    <activity
			android:name=".ui.main.MainActivity"
			android:windowSoftInputMode="adjustResize"
			... />
    </application>
</Manifest>
```

그러나, 필요하지 않을때는 어떻게 해야 할까? Activity로 화면을 구성할때는 고민할 필요가 없었지만 싱글액티비티로 화면을 구현하게 되면 분명히 키보드 + 레이아웃 문제와 마주치게 된다. 그럴 땐 동적으로 `windowSoftInputMode`를 제어해야 한다.

필요하지 않은 화면의 onResume에 아래와 같이 선언해준다.

```kotlin
requireActivity().window.setSoftInputMode(WindowManager.LayoutParams.SOFT_INPUT_ADJUST_NOTHING)
```

반대로, onPause에 

```kotlin
requireActivity().window.setSoftInputMode(WindowManager.LayoutParams.SOFT_INPUT_ADJUST_RESIZE)
```

이렇게 하면 프래그먼트 화면에서 키보드+레이아웃 문제(?)를 해결할 수 있다.

현재 API 30에서 SOFT_INPUT_ADJUST_RESIZE은 Deprecated된 상태다.