## ADB를 환경변수에 제대로 등록(.bash_profile)했지만 동작하지 않을때

adb 경로를 .bash_profile에 제대로 등록했는데요. 터미널에서 adb가 동작하지 않을 때가 있다. 가령, source .bash_profile 이후에 adb가 동작은 하지만, 터미널을 종료/시작 했을때 터미널에서 adb가 동작하지 않는 경우다. 동작하지 않는 것은 adb명령어를 찾을 수 없다는 것과 같다. 그럴땐...

brew를 맘편하게 설치해 주자. 더 이상 스트레스 받지 말자..

```
brew cask install android-platform-tools
```

