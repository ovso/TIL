# kotlin not configured

`코틀린이 구성되지 않았다.` 

모듈을 새로 만들어 추가했는데 `kotlin not configuared` 라는 메시지가 클래스 상단에 알림 형식으로 떳다. 빌드하는 것은 문제가 없었다. 하지만 여러 클래스에 컴파일 에러가 나고 있는 상황이었다.

모듈의 build.gradle의 dependencies에 `kotlin-stdlib` 이 자동으로 추가되어 있었다. 이를 `kotlin-stdlib-jre7 or jre8`  로 바꾸고 _Sync Now_ 하니 해결되었다.