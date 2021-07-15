# Application 에서의 초기화

```kotlin
class MyApp: Application() {
  val manager:Manager = Manager(this)
  lateinit var manager2:Manager
  fun onCreate() {
    super.onCreate()
    manager2 = Manager(this)
  }
}

class Manager(context:Context) {
  ...
}
```

manager와 manager2의 초기화는 같을까 다를까? 결론부터 말하자면 다르다. manager의 context는 context.packageName 조차 가져오지 못한다. packageName을 가져오면 빈값("")이다. manager2는 일반적으로 context에서 가져올 수 있는 모든 값을 정상적으로 가져올 수 있다.

manager의 초기화 시점은 Android 플랫폼이 Application 인스턴스를 생성할 때다. 최초 인스턴스를 생성할때는 Application 생성자에서 super(mBase = null)을 하고 있다. mBase는 context를 가리키지만, null로 할당했기 때문에 mBase는 제대로된 정보를 가져올 수 없다. 때문에 context가 필요한 모듈이나 SDK들은 onCreate에서 하는 것이 맞다.
