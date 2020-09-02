# 오직 상태표시줄만 투명하게 하기

구글링하면, 상태표시줄(Status Bar)를 투명하게 하는 스타일(styles.xml), 코드들을 얼마든지 찾아볼 수 있다. 그러나 오직 상태표시줄만을 투명하게 하기란 까다롭다. 수많은 구글링 결과들이 안되거나 틀렸거나 하단 네비게이션을 제어하면서 문제들이 생긴다. 포기하던 찰나에.. 검색 결과중 하나만 시도해보고자 한게... 

## 오직 상태표시줄만..

```kotlin
fun Activity.makeStatusBarTransparent() {
    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP) {
        window.apply {
            clearFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS)
            addFlags(WindowManager.LayoutParams.FLAG_DRAWS_SYSTEM_BAR_BACKGROUNDS)
            if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.M) {
                decorView.systemUiVisibility =
                    View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN 
                        or View.SYSTEM_UI_FLAG_LIGHT_STATUS_BAR
            } else {
                decorView.systemUiVisibility = View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN
            }
            statusBarColor = Color.TRANSPARENT
        }
    }
}
```

야호!!!!!!!!!!!

[https://proandroiddev.com/android-full-screen-ui-with-transparent-status-bar-ef52f3adde63](https://proandroiddev.com/android-full-screen-ui-with-transparent-status-bar-ef52f3adde63)