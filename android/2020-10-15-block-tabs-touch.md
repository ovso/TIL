# 탭 아이템 터치 막기(Block tabs touch)

안드로이드 네트워킹 중에 임시로 탭을 막아야 할 일이 생겼다. 아래와 같이 막을 수 있다.

```kotlin
       viewModel.isLoading.observe(this, {
            binding.tabs.apply {
                for (i in 0 until tabCount) {
                    getTabAt(i)?.view?.isClickable = it.not() // here
                }
            }
        })
```

