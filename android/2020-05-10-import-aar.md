# AAR을 추가 하는 두 가지 방법

## 하나, 메뉴를 사용하여 추가하기

File > New > New Module > Select a Module Type > Import .JAR / .AAR Package

## 두울, build.gradle을 사용하여 추가하기

```groovy
dependencies {
	implementation fileTree(dir: 'libs', include: ['*.aar'])
  ...
}
```

# 결론

물론 필자는 두 번째 방법을 권장한다. 왜냐하면 첫 번째 방법은 app 모듈과 같은 수준에 모듈이 표시되면서 프로젝트 구조가 복잡해 보이기 때문이다. aar이 추가 될수록 가독성도 현저하게 떨어진다. 그러므로 필자는 두 번째 방식 권장한다.