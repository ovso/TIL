# Android Studio 초기 설정

이따금 Android Studio를 새롭게 설치해야 할 때가 있다. 그땐 본인 스타일에 맞는 초기 설정을 해야 한다.  언어에 대한 코드 스타일을 비롯해, 자신에게 맞는 플러그인들이 그것들이다. 이런 설정들을 기록해 두지 않으면 기억을 더듬어 봐야 한다. 모두 기억하면 괜찮지만 우리들은 그렇지 못하다. 필요할 때마다 설치할 수도 있지만 일에 흐름이 깨질수도 있다. 때문에 필자의 설정을 기록해 두고자한다.

## Theme

Preferences(⌘+,) -> Color Scheme -> Scheme -> Dracula

## Code Style

### 코드 리포멧( ⌥⌘ + L )을 위한 설정

- Preferences(⌘+,) -> Editor -> Code Style -> Java -> Set from... -> Android
- Preferences(⌘+,) -> Editor -> Code Style -> Kotlin -> Set from... -> Kotlin style guide
- Preferences(⌘+,) -> Editor -> Code Style -> Kotlin -> Load/Save -> Use defaults from -> Kotlin Coding Conventions
- Preferences(⌘+,) -> Editor -> Code Style -> Formatter Control -> Enable formatter markers in comments(Check in)
- .editorconfig 파일 설정(들여쓰기)

### 코드 스타일 정적 분석 도구(선택 사항)

- [detekt](https://github.com/arturbosch/detekt)
- [ktlint](https://github.com/pinterest/ktlint)
- [spotless](https://github.com/diffplug/spotless)
- [lint](https://developer.android.com/studio/write/lint)

## Plugins

Preferences(⌘+,) -> Plugins -> Marketplace

- [Rainbow Brackets](https://plugins.jetbrains.com/plugin/10080-rainbow-brackets/)
- [Json to Kotlin class](https://plugins.jetbrains.com/plugin/9960-json-to-kotlin-class-jsontokotlinclass-/)

## Live templates

Preferences(⌘+,) -> Editor -> Live Templates

안드로이드는 XML에 작업이 많기 때문에 XML 위주로 템플릿을 만들어 놓으면 편한다. 대표적으로 ConstraintLayout이 있다.

- AndroidXML

# 결론

안드로이드 스튜디오 설치 후 귀찮은 설정을 빠르게 진행하여 마음의 평온을 빨리 찾고 해피코딩하자.