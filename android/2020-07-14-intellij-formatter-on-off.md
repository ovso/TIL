# 특정 영역 포멧팅 하지 않기

IntelliJ를 사용하면서 필자는 무의식적으로 리포멧(Option + Command + L)을 사용한다. 코드가 설정한 스타일대로 바뀌기 때문이다. 그러나 종종 포멧팅 하고 싶지 않은 코드가 부분적으로 존재한다. 그럴때 Formatter Control를 사용하면 된다.

## 환경설정

Preferences(Command + ,)  -> Editor -> Code Style -> Formatter Control(Tab) -> Enable formatter markers in comments (체크박스 on )

## 사용

```kotlin
// @formatter:off
/*
포멧팅 하고 싶지 않은 코드
...
*/
// @formatter:on
```