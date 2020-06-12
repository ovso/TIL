# Android Interview Questions

## 알고리즘 코딩테스트

## 사전 과제 코드 리뷰

## 과제 진행 소요시간

## 과제 수행 후 아쉬운점

## Gradle 설명

Gradle은 거의 모든 유형의 소프트웨어를 빌드 할 수있을 정도로 유연하게 설계된 오픈 소스 빌드 자동화 도구다. 안드로이드에서도 DSL로 Gradle을 채택하여 사용하고 있다.

## Gradle Flavor 사용경험

Flavors를 Develop, Staging, Production 으로 나누어 사용한 경험이 있다. 만약, Flavors가 3개 라면 3개의 동일한 패키지를 구성할 수 있다. 이 패키지 내에 동일한 리소스명을 가지고 서로 다른 구현을 할 수 있다. 아이콘, 앱 트레킹 클래스, 서버 API 주소 등이 달라질 수 있다.

### 참고

[https://developer.android.com/studio/build#build-config](https://developer.android.com/studio/build#build-config)

## compileSDKVersion과 targetSDKVersion 차이

### compileSDKVersion

compileSDKVersion은 앱이 컴파일 되는 API 버전이다. 즉, 해당 버전의 API에 포함 된 Android API 기능 (및 모든 이전 버전)을 사용할 수 있다. API 16 기능을 사용하려고하지만 compileSdkVersion을 15로 설정하면 컴파일 오류가 발생한다. compileSdkVersion을 16으로 설정 한 경우 앱의 실행 경로가 API 16에 특정한 API를 호출하지 않는 한 API 15 디바이스에서 앱을 계속 실행할 수 있다.

### targetSDKVersion

targetSdkVersion은 앱을 컴파일하는 방법 또는 사용할 수있는 API와는 아무 관련이 없다. targetSdkVersion은 사용자가 지정한 버전에서 (아마도 포함하여) 앱을 테스트했음을 나타낸다. 이것은 인증과 비슷하거나 OS 기능 측면에서 앱을 처리하는 방법에 대한 힌트로 Android OS를 제공하고 있음을 나타낸다.

예를 들어, [문서](https://developer.android.com/guide/topics/manifest/uses-sdk-element.html)에 다음과 같이 나와 있다.

> 예를 들어이 값을 "11"이상으로 설정하면 Android 3.0 이상에서 실행할 때 시스템이 앱에 새로운 기본 테마 (Holo)를 적용 할 수 있다.

런타임시 Android OS는이 값을 기반으로 OS 컨텍스트에서 앱이 양식화되거나 달리 실행되는 방식을 변경할 수 있다. 이 값의 영향을받는 다른 몇 가지 알려진 예가 있으며 해당 목록은 시간이 지남에 따라 증가 할 수 있다.

실질적인 목적으로 대부분의 앱은 targetSdkVersion을 최신 릴리스 버전의 API로 설정하려고한다. 이렇게하면 최신 Android 기기에서 앱이 최대한 멋지게 보인다. targetSdkVersion을 지정하지 않으면 기본값은 minSdkVersion이다.

### 참고

[https://stackoverflow.com/questions/26694108/what-is-the-difference-between-compilesdkversion-and-targetsdkversion](https://stackoverflow.com/questions/26694108/what-is-the-difference-between-compilesdkversion-and-targetsdkversion)

[https://developer.android.com/guide/topics/manifest/uses-sdk-element.html](https://developer.android.com/guide/topics/manifest/uses-sdk-element.html)

## Manifest 설명

모든 앱 프로젝트에는 프로젝트 소스 세트의 루트에 AndroidManifest.xml 파일 (정확히 해당 이름)이 있어야한다. 매니페스트 파일은 Android 빌드 도구, Android 운영 체제 및 Google Play에 대한 앱의 필수 정보를 설명한다.

앱에서 생성 한 각 앱 구성 요소에 대해 매니페스트 파일에서 해당 XML 요소를 선언해야한다. 요소에는 Activity, Service, Receiver, Provider 등 여러가지가 있다.

사용자에게 필요한 앱 권한을 설정할 수 있다.

## 안드로이드 생명주기 설명

### Activity

![](https://developer.android.com/images/activity_lifecycle.png)

### Fragment

![](https://developer.android.com/images/fragment_lifecycle.png)

## 이미지 캐시 설명 (Memory, Disk)

이미지 캐시에는 메모리 캐시와 디스크 캐시가 있다. 메모리 캐시는 객체에 담는것을 말하고, 디스크 캐시는 저장소에 저장하는 것을 말한다. 일반적으로 아이템마다 이미지가 있는 리스트를 구현할 때 메모리 캐시를 사용한다. 리스트를 좌우, 위아래로 로드할때 매번 로딩하는 것은 효율적이지 않기 때문에 이미지 캐시를 통해 로드하여 효율을 높일 수 있다.

안드로이드에서는 매모리 캐시는 LruCache를 사용하고, 디스크 캐시는 DiskLruCache를 사용한다. 

일반적으로 메모리 캐시와 디스크 캐시의 차이는 메모리 캐시는 처리 속도가 빠르지만 저장 공간이 작고, 디스크 캐시는저장 공간은 상대적으로 크지만 파일 입출력으로 인한 처리 속도가 느리다. 

### 참고

[안드로이드 이미지캐시(메모리캐시, 디스크캐시)](https://meylady.tistory.com/49)

[Caching Bitmaps](https://developer.android.com/topic/performance/graphics/cache-bitmap.html)

[Caching Bitmaps 한글](https://developer.android.com/topic/performance/graphics/cache-bitmap?hl=ko)

[LruCache](https://developer.android.com/reference/android/util/LruCache)

## LRU 알고리즘

제한된 수의 값에 대한 강력한 참조를 보유하는 캐시다. 값에 액세스 할 때마다 큐의 헤드로 이동한다. 전체 캐시에 값이 추가되면 해당 큐 끝의 값이 제거되고 가비지 콜렉션에 적합 할 수 있다.

### 참고

[LruCache](https://developer.android.com/reference/android/util/LruCache)

[LruCache 사용시 maxSize 및 sizeOf()](https://ccdev.tistory.com/33)

## String, StringBuilder, StringBuffer 차이

### 참고

[String, StringBuilder, StringBuffer의 차이](https://12bme.tistory.com/42)

## HashTable과 HashMap의 차이, HashMap의 내부구조는?

### HashTable과 HashMap의 차이

HashTable은 자바 1.0 부터 구현된 객체이고, HashMap은 Collections API 에 제공되었다. HashMap은 계속 개선되어 가고 있지만, HashTable은 변경되지 않고 있다. HashTable은 하위 호환성을 위해 존재한다고 볼 수 있다. 가장 큰 차이점은 동기화이다. HashTable은 동기화 되지만, HashMap은 동기화 되지 않는다. HashMap의 동기화를 원한다면 ConcurrentHashMap을 이용하는 것이 좋다. 

### HashMap의 내부 구조

[Java HashMap은 어떻게 동작하는가?](https://d2.naver.com/helloworld/831311)

## Hash설명 (연장선)

**해시 함수**(hash function)는 임의의 길이의 데이터를 고정된 길이의 데이터로 매핑하는 [함수](https://ko.wikipedia.org/wiki/함수)이다. 해시 함수에 의해 얻어지는 값은 **해시 값**, **해시 코드**, 해시 체크섬 또는 간단하게 **해시**라고 한다.

[해시함수]([https://ko.wikipedia.org/wiki/%ED%95%B4%EC%8B%9C_%ED%95%A8%EC%88%98](https://ko.wikipedia.org/wiki/해시_함수))

## Synchronized 설명

동기화를 말한다. `synchronized` 키워드를 사용하면, `JVM` 은 `Java 동기화 코드` 가 한 번에 하나의 쓰레드에서만 실행되도록 보장한다. `Java 동기화 코드` 란 `synchronized` 를 사용한 메서드나 로직을 말한다.

## Activity->Activity/Activity->Fragment/Fragment->Fragment 데이터 전송 방법은?

## Serializable, Parcel 설명

[Serializable](https://docs.oracle.com/javase/7/docs/api/java/io/Serializable.html) 은 Android SDK 가 아닌 표준 Java 의 인터페이스다.

[Parcelable](https://developer.android.com/reference/android/os/Parcelable.html) 은 직렬화를 위한 또다른 인터페이스 입니다. Serializable 과는 달리 표준 Java 가 아닌 Android SDK 의 인터페이스다.

Parcelable 은 Reflection 을 사용하지 않도록 설계되었다. Serializable 과는 달리 직렬화 처리 방법을 사용자가 명시적으로 작성하기 때문에 자동으로 처리하기 위한 Reflection 이 필요없다. 때문에 Parcelable이 비용이 적게 든다. 즉 Parcelable이 빠르다.

그러나! 객체를 각각 어떻게 처리해주느냐에 따라 속도는 역전된다.

[Parcelable vs Serializable , 정말 Serializable은 느릴까?]([https://medium.com/@limgyumin/parcelable-vs-serializable-%EC%A0%95%EB%A7%90-serializable%EC%9D%80-%EB%8A%90%EB%A6%B4%EA%B9%8C-bc2b9a7ba810](https://medium.com/@limgyumin/parcelable-vs-serializable-정말-serializable은-느릴까-bc2b9a7ba810))

## Bundle 설명

문자열로 키를 설정하고 다양한 Parcelable 형태의 값을 넣는 꾸러미다.

## CustomView 구현 방법은?

안드로이드 프레임워크에서 제공하는 기본적인 위젯들을 상속하여 구현할 수 있다. xml 요소를 통해 View를 제어하기 위해 res/values/attrs.xml 파일에 <declare-styleable> 요소를 추가하여 사용한다.

## Animation 설명

안드로이드 애니메이션은, 속성 애니메이션과 뷰 애니메이션으로 구현한다. 

속성 애니메이션은 설정된 시간 경과에 따른 객체의 속성 값을 [Animator](https://developer.android.com/reference/android/animation/Animator?hl=ko)로 수정하여 애니메이션을 만든다. 

뷰 애니메이션 프레임워크는 XML에서 모두 선언할 수 있는 트윈 애니메이션과 프레임별 애니메이션을 둘 다 지원한다. 트윈 애니메이션은 XML로 정의되는 애니메이션으로, 그래픽에서 회전, 페이딩, 이동, 확장과 같은 변환을 진행한다. 프레임 애니메이션은 XML로 정의된 애니메이션으로, 영화처럼 일련의 이미지를 순서대로 표시한다.

[애니메이션 리소스](https://developer.android.com/guide/topics/resources/animation-resource?hl=ko)

### 

## onDraw에서 canvas 설명

`android.graphics` 프레임워크에서는 그리기를 다음 두 영역으로 나눈다.

- *무엇*을 그릴 것인가(`Canvas`에서 처리)
- *어떻게* 그릴 것인가(`Paint`에서 처리)

예를 들어 `Canvas`에서는 선을 그릴 수 있는 메서드를 제공하고 `Paint`에서는 이 선의 색을 정의할 수 있는 메서드를 제공한다. `Canvas`에는 직사각형을 그릴 수 있는 메서드가 있는 반면, `Paint`에서는 이 직사각형을 색상으로 채울지, 아니면 빈 상태로 둘지 정의한다. 간단히 말하자면 `Canvas`에서는 화면에서 그릴 수 있는 도형을 정의하는 반면, `Paint`에서는 개발자가 그리는 각 도형의 색상, 스타일, 글꼴 등을 정의한다.

따라서 무언가를 그리려면 하나 이상의 `Paint` 개체를 만들어야 한다.

[맞춤 그리기](https://developer.android.com/training/custom-views/custom-drawing?hl=ko)

## DI 사용해봤는지?

Dagger, Koin을 사용해봤다. 정확히 구분하자면, Dagger는 DI, Koin은 ServiceLocator다. DI는 생성자나 메서드를 통해 외부에서 주입하지만, ServiceLocator는 내부에서 주입 할 수도 있다. 내부에서 주입하는 것은 테스트를 어렵게 만들 수 있다. 그러나 ServiceLocator를 DI처럼 외부에서만 주입하여 사용하면 큰 차이는 없다. 비슷하다.

## 디자인 패턴 알고 있는 것들 설명

### Singleton, Builder(Method chaining), Constructor, Beans 패턴

Singleton : 생성자가 여러 차례 호출되더라도 실제로 생성되는 객체는 하나이고 최초 생성 이후에 호출된 생성자는 최초의 생성자가 생성한 객체를 리턴한다. 이와 같은 디자인 유형을 **싱글턴 패턴**이라고 한다. [싱글턴 패턴](https://ko.wikipedia.org/wiki/싱글턴_패턴)

Builder : 복합 객체의 생성 과정과 표현 방법을 분리하여 동일한 생성 절차에서 서로 다른 표현 결과를 만들 수 있게 하는 패턴이다. 안드로이드 프레임워크에서 대표적인 사례로, AlertDialog.Builder 클래스가 있다.

Constructor : 인자가 다른 생성자 여러개를 추상화 하여 원하는 생성자를 사용할 수 있게 하는 패턴으로, 안티패턴이다.

Beans : 자바에서 일반적으로 사용하는 방식으로, 객체 생성 후 객체 . 으로 값을 설정하는 방법이다. 안티패턴이다.

## MVP 패턴이란?

Model View Presenter로 구성되어 있는 패턴이다. V와 P는 1:1 관계다. V에서 발생한 이벤트를 P로 보내 처리하기 때문이다. M은 P에서 사용하는 각종 클래스를 말한다. 각종 클래스란? ResourceProvider나 Repository 등의 클래스를 말한다.

## RxJava, RxKotlin에 대해 설명

RxJava는 ReactiveX (Reactive Extensions)의 Java VM 구현입니다. 관찰 가능한 시퀀스를 사용하여 비동기 및 이벤트 기반 프로그램을 구성하기위한 라이브러리입니다.

RxKotlin은 RxJava에 편리한 확장 기능을 추가하는 경량 라이브러리입니다. Kotlin은 기본적으로 RxJava와 함께 사용할 수 있지만 Kotlin에는 RxJava의 사용을 더욱 능률화 할 수있는 언어 기능 (예 : 확장 기능)이 있습니다. RxKotlin은 이러한 편의성을 하나의 중앙 집중식 라이브러리에서 보수적으로 수집하고 Kotlin과 함께 RxJava를 사용하기위한 규칙을 표준화하는 것을 목표로합니다.

## Git submodule 사용해봤나?

사용해봤다. 별도의 버전관리를 하고 있는 외부의 모듈을 사용하기 위해 submodule를 사용했다.

## Git에서 cherry pick, squash, rebase를 사용하는 경우는?

체리픽은 히스토리에서 커밋하나를 가져와 병합할때 사용한다.

squash는 여러 커밋을 묶어 하나의 커밋으로 만들때 사용한다. 되도록 push 이전에 하는게 낫다.

rebase는?

## Android Studio lint 사용경험?

있다. 명령어에서 ./gradlew lint 하거나 ./gradlew ktlint or ktlintFormat을 사용한다.

## Java Heap, Stack, Method memory 설명

[Java Memory 간단히 살펴보기](https://mirinae312.github.io/develop/2018/06/04/jvm_memory.html)

## Multi Thread 사용 경험

(Thread를 통해) Api 호출 후 UI를 갱신하면 Multi Thread다.

RecyclerView에서 Item마다 새로운 Api 호출하여 아이템 내의 리스트 값을 바꾼 경험이 있다.

## Thread 프로세스, Multi Thread 프로세스 장단점

## 대칭키와 비대칭키 암호화

**대칭키**는 송신자와 수신자가 같은 키로 암호화, 복호화 하는 것을 말한다. 대표적인 알고리즘으로 AES, DES가 있다.

**공개 키 암호 방식**(公開 - 暗號 方式, public-key cryptography)은 [암호 방식](https://ko.wikipedia.org/wiki/암호학)의 한 종류로 사전에 비밀 키를 나눠가지지 않은 사용자들이 안전하게 통신할 수 있도록 한다. 공개 키 암호 방식에서는 공개 키와 비밀 키가 존재하며, 공개 키는 누구나 알 수 있지만 그에 대응하는 비밀 키는 키의 소유자만이 알 수 있어야 한다. 공개 키는 보안 타협 없이 공개적으로 배포가 가능하다.[[1\]](https://ko.wikipedia.org/wiki/공개_키_암호_방식#cite_note-1) 공개 키 암호를 구성하는 알고리즘은 [대칭 키 암호](https://ko.wikipedia.org/wiki/대칭_키_암호) 방식과 비교하여 **비대칭 암호**(非對稱暗號)라고 부르기도 한다. 대표적인 알고리즘으로 RSA가 있다.

[대칭 키 암호]([https://ko.wikipedia.org/wiki/%EB%8C%80%EC%B9%AD_%ED%82%A4_%EC%95%94%ED%98%B8](https://ko.wikipedia.org/wiki/대칭_키_암호))

[공개 키 암호 방식(비대칭 키 암호)]([https://ko.wikipedia.org/wiki/%EA%B3%B5%EA%B0%9C_%ED%82%A4_%EC%95%94%ED%98%B8_%EB%B0%A9%EC%8B%9D](https://ko.wikipedia.org/wiki/공개_키_암호_방식))

## Queue 설명( Java )

큐는 큐의 끝에 요소를 삽입하고 큐의 시작에서 제거하는 데 사용됩니다. FIFO 개념을 따릅니다. 

Java의 Queue는 삽입, 삭제 등 Collection 인터페이스의 모든 메소드를 지원합니다. 

LinkedList, ArrayBlockingQueue 및 PriorityQueue는 가장 자주 사용되는 구현입니다. 

BlockingQueues에서 널 작업이 수행되면 NullPointerException이 발생합니다.

[Queue Interface In Java](https://www.geeksforgeeks.org/queue-interface-java/)

## Volatile 설명

Java 휘발성 키워드는 변수 가시성 문제를 해결하기위한 것입니다. 카운터 변수를 휘발성으로 선언하면 카운터 변수에 대한 모든 쓰기가 즉시 주 메모리에 다시 기록됩니다. 또한 카운터 변수의 모든 읽기는 주 메모리에서 직접 읽습니다.

[Java Volatile Keyword](http://tutorials.jenkov.com/java-concurrency/volatile.html)

## 싱글톤 DCL 단점

Thread-Safe 하지 않다.

[Singleton - Lazy Initialize와 DCL(Double checked locking)](http://blog.daum.net/smufu/3)

[Double-checked locking and the Singleton pattern](https://www.ibm.com/developerworks/library/j-dcl/index.html)

## Rx 설명, 장단점

ReactiveX는 관찰 가능한 시퀀스를 사용하여 비동기 및 이벤트 기반 프로그램을 작성하기위한 라이브러리입니다.

### 장점

비동기 프로그래밍이 편하다.

2개 이상의 Api를 연속적으로 사용할 때 콜백에 큰 부담이 없다. (콜백 지옥으로 부터 벗어날 수 있다)

### 단점

대부분의 시간 동안 스트림을 기반으로하기 때문에 대부분의 데이터 스트림을 저장하는 데 더 많은 메모리가 필요합니다.

학습 비용이 높다.

## 함수형 프로그래밍 설명, 장단점

### 설명

**함수형 프로그래밍**(functional programming)은 자료 처리를 [수학적 함수](https://ko.wikipedia.org/wiki/함수)의 계산으로 취급하고 상태와 가변 데이터를 멀리하는 [프로그래밍 패러다임](https://ko.wikipedia.org/wiki/프로그래밍_패러다임)의 하나이다. [명령형 프로그래밍](https://ko.wikipedia.org/wiki/명령형_프로그래밍)에서는 상태를 바꾸는 것을 강조하는 것과는 달리, 함수형 프로그래밍은 함수의 응용을 강조한다. 프로그래밍이 [문](https://ko.wikipedia.org/wiki/문_(프로그래밍))이 아닌 식이나 선언으로 수행되는 [선언형 프로그래밍](https://ko.wikipedia.org/wiki/선언형_프로그래밍) 패러다임을 따르고 있다.[[1\]](https://ko.wikipedia.org/wiki/함수형_프로그래밍#cite_note-expression_style-1) 함수형 프로그래밍은 1930년대에 계산가능성, 결정문제, 함수정의, 함수응용과 재귀를 연구하기 위해 개발된 형식체계인 [람다 대수](https://ko.wikipedia.org/wiki/람다_대수)에 근간을 두고 있다. 다수의 함수형 [프로그래밍 언어](https://ko.wikipedia.org/wiki/프로그래밍_언어)들은 람다 연산을 발전시킨 것으로 볼 수 있다.

### 장점

불변성(Immutability) : 함수형 프로그래밍은 불변성을 지향하여 사이드 이팩트를 줄이거나 제거한다. 불변성이기 때문에 검증하기도 수월하다. Thread-Safe 한 것도 장점 중의 하나다.

First-class, higher-order functions : 함수형 프로그래밍에서 함수는 일등 시민(first-class citizen)입니다. 일등 시민으로서의 함수란 변수에 할당할 수 있고, 다른 함수의 인자로 전달할 수 있으며, 다른 함수의 결과 값으로 반환될 수 있는 함수를 의미합니다. 함수를 하나의 값처럼 다룰 수 있기 때문에 객체지향 패러다임에서 클래스를 재사용하는 것처럼 함수를 재사용할 수 있고, 핵심 코드를 boilerplate 없이 간단하게 표현할 수 있습니다.

Lazy evaluation : 함수형 프로그래밍 언어는 지연 연산(lazy evaluation)을 지원합니다. 지연 연산이란 어떤 값이 실제로 쓰이기 전까지 그 값의 계산을 최대한 미루는 것입니다. 값을 미리 계산하여 저장하지 않기 때문에 공간을 절약할 수 있고, 값이 꼭 필요할 때만 계산하기 때문에 프로그램의 성능에도 긍정적인 영향을 줍니다. 

### 단점

상태가 없다. 불변을 지향하기 때문에 상태가 없다. 하지만 사용자(User)와의 상호작용(Interaction)은 대부분 상태 변화로 모델링 된다.

코드가 간결해질 수록 보기 어렵다.

인력이 부족하다.

[Five Drawbacks/Downsides of Functional Programming](https://spin.atomicobject.com/2019/08/29/functional-prog-pros-cons/)

[Functional Programming(함수형 프로그래밍)](https://devhue.github.io/blog/functional-programming)

## 프로세스와 쓰레드 설명

**프로세스**는 프로그램에 지정된 적절한 조치를 수행 할 수있는 프로그램의 실행입니다. 프로그램이 실행되는 실행 단위로 정의 될 수 있습니다. OS는 CPU가 사용하는 프로세스를 생성, 예약 및 종료하는 데 도움이됩니다. 기본 프로세스에 의해 생성 된 다른 프로세스를 자식 프로세스라고합니다.

**스레드**는 프로세스의 일부인 실행 단위입니다. 프로세스는 동시에 실행되는 여러 스레드를 가질 수 있습니다. 동시 프로그래밍에서 실행 단위입니다. 스레드는 가벼우 며 스케줄러에서 독립적으로 관리 할 수 있습니다. 병렬 처리를 사용하여 응용 프로그램 성능을 향상시키는 데 도움이됩니다.

[Process vs Thread: What's the difference?](https://www.guru99.com/difference-between-process-and-thread.html)

## 오버헤드

오버헤드(overhead)는 어떤 처리를 하기 위해 들어가는 간접적인 처리 시간 · 메모리 등을 말한다. 

예를 들어 A라는 처리를 단순하게 실행한다면 10초 걸리는데, 안전성을 고려하고 부가적인 B라는 처리를 추가한 결과 처리시간이 15초 걸렸다면, 오버헤드는 5초가 된다. 또한 이 처리 B를 개선해 B'라는 처리를 한 결과, 처리시간이 12초가 되었다면, 이 경우 오버헤드가 3초 단축되었다고 말한다.

## AndroidManifest

### launchMode

[android:launchMode](https://developer.android.com/guide/topics/manifest/activity-element?hl=ko#lmode) 는 액티비티를 시작하는 방법에 대한 지침이다. 인텐트를 처리하기 위해 액티비티를 호출할 때 발생하는 것을 결정하기 위해 `Intent` 객체에서 액티비티 플래그(`FLAG_ACTIVITY_*` 상수)와 함께 작동하는 4개의 모드가 있다. 그 드는 다음과 같다.

`standard`
`singleTop`
`singleTask`
`singleInstance`

기본 모드는 `standard` 다.

### taskAffinity

[android:taskAffinity](https://developer.android.com/guide/topics/manifest/activity-element?hl=ko#aff)

## Kotlin Nothing

## RxJava Subject

# 참고

[Kotlin Android Interview Questions](https://blog.mindorks.com/kotlin-android-interview-questions)

