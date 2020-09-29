# incompatible types: LayoutAllToolbarBinding cannot be converted to View..

`데이터바인딩`만 사용하던 프로젝트에 `뷰바인딩` 을 사용할 수 있도록 Gradle을 수정했더니 무시무시한 에러가 떳다.

```
incompatible types: LayoutAllToolbarBinding cannot be converted to View..
incompatible types: View cannot be converted to ViewDataBinding
.
.
.
.
.
.
.
.
.

```

평소 DataBinding과 Dagger 에러를 정말 싫어하는 필자로서는 머리가 지끈거렸다.

2가지로 빌드를 정상적으로 할 수 있게 됐다.

하나,

```xml
<layout xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools">
  ..
  ..
</layout>
```

두울,

```
tools:viewBindingIgnore="true"
```

# 결론

DataBinding을 사용하던 프로젝트에, ViewBinding을 적용하려는 것이면, `하나` 를 추천한다. `두울` 은 빌드를 되지만 컴파일 에러가 항상 존재할 수 있기 떄문이다.