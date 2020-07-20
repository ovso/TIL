# 라이브러리 검색하여 추가하기

Android Studio에 라이브러리를 검색하여 추가하는 기능이 생겼다. 어느 버전부터 생겼는지 알 수 없지만, 필자의 사용하고 있는 IDE 버전은 4.1 [BETA](https://developer.android.com/studio/preview/) 4 이다.

## 사용

- `⌘ + ;` 으로 `Project Structure` 창을 연다.
- 좌측의 `Dependencies` 탭을 연다.
- 우측 `Modules`에서 라이브러리를 추가할 모듈을 선택한다. 일반적인 앱이라면 `app`을 선택하면 된다.
- 우측 `Modules`에서 또 우측을 보면 `Declared Dependencies`창이 있다. 상단에 + 버튼을 눌러 `Library Dependency`(팝업메뉴 중 택1)를 선택한다. 
- `Add Library Dependency` 창이 뜨는데, 가장 상단에 검색박스가 나온다. 그곳에서 검색을 한다.
- picasso, glide 등등을 검색한 후에 OK를 누르면 모듈 수준의 `build.gradle`에 Libarary가 추가된 것을 확인할 수 있다.

라이브러리를 검색하기 위해, 프로젝트 빌드 파일 (JCenter, Google, Android 리포지토리, Google 리포지토리)에 지정된 리포지토리를 사용한다.

