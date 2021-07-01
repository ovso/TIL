# AAB(Android App Bundle) 설치하기

aab를 설치하는 방법은 두 가지다.. bundletool(jar)을 사용하거나, Playstore 테스트 트랙(내부 트랙 등)에 aab 파일을 업로드 하여 다운로드 하는 방법이다. 여기서는 bundletool을 이용하는 방법을 살펴보고자 한다.

- bundletool 다운로드
- App Bundle에서 APK 집합 생성
  - 집합(apks)을 생성할때 서명 정보도 포함해야 한다. 서명 정보를 포함하지 않으면 bundletool이 디버그 키로 APK에 서명을 한다. 

```
java -jar bundletool.jar build-apks --bundle=xxx_105-1.0.6.rc1-production-release.aab --output=app.apks
```

- 연결된 기기에 APK 배포

```
bundletool install-apks --apks=app.apks
```



aab를 미리 해보는 것은 대체로 앱 용량을 보기 위함이 경우가 만을 것으로 생각한다. 그럴 땐 bundletool을 이용하자.
