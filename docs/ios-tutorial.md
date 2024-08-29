# KiTPlayer SDK Documentation

## 시작하기

이 문서는 KiTPlayer SDK 사용 방법을 안내합니다.

## 설치

### SPM으로 설치

KiTPlayer SDK를 SPM(Swift Package Manager)을 통해 설치할 수 있습니다.

```text
https://github.com/muzlive-info/muzlive-kit-player-sdk-ios
```

[repository](https://github.com/muzlive-info/muzlive-kit-player-sdk-ios)

## 프로젝트 설정

### 1. 앱 프라이버시 설정

KiTPlayer SDK를 사용하기 위해서는 앱의 마이크 권한이 필요합니다. 이를 위해 `Privacy - Microphone Usage Description` 설정을 추가해야 합니다.

`Info.plist` 파일에 아래 항목을 추가하세요:

```xml
<key>NSMicrophoneUsageDescription</key>
<string>키트 인식을 위해 마이크 권한이 필요합니다.</string>
```

![앱 프라이버시 설정 예시](https://prod-files-secure.s3.us-west-2.amazonaws.com/5ae1257a-34e7-42fd-9eac-be81ca8c780b/8624271b-7ee6-4d8e-86fb-051c0b1ea4fa/Untitled.png)

## SDK 사용하기

### 1. 초기화

`AppDelegate`에 SDK 키와 함께 `KiTPlayer`를 초기화해야 합니다. 아래와 같이 설정하세요:

```swift
import KiTPlayer

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
    var window: UIWindow?

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        KiTPlayer.initialize(withAPIKey: "YOUR_API_KEY")
        return true
    }
}
```

![초기화 예시](https://prod-files-secure.s3.us-west-2.amazonaws.com/5ae1257a-34e7-42fd-9eac-be81ca8c780b/8c5af5f3-3b4b-448b-a1af-ec31453f5e93/Untitled.png)

### 2. 플레이어 실행

`ViewController`에서 버튼을 통해 `start()` 메서드를 호출하여 플레이어를 실행할 수 있습니다. 예시는 다음과 같습니다:

```swift
import KiTPlayer

class ViewController: UIViewController {
    @IBAction func playButtonTapped(_ sender: UIButton) {
        KiTPlayer.shared.start()
    }
}
```

![플레이어 실행 예시](https://prod-files-secure.s3.us-west-2.amazonaws.com/5ae1257a-34e7-42fd-9eac-be81ca8c780b/9b632706-95ad-4b8f-be5f-8bf2875d1c73/Untitled.png)

### 3. 에러 확인

SDK 사용 중 발생할 수 있는 에러를 처리하기 위해 delegate를 등록할 수 있습니다.

```swift
import KiTPlayer

class ViewController: UIViewController, KiTPlayerDelegate {
    override func viewDidLoad() {
        super.viewDidLoad()
        KiTPlayer.shared.delegate = self
    }

    func kitPlayer(_ kitPlayer: KiTPlayer, didEncounterError error: Error) {
        print("Error encountered: \(error.localizedDescription)")
    }
}
```

![에러 확인 예시](https://prod-files-secure.s3.us-west-2.amazonaws.com/5ae1257a-34e7-42fd-9eac-be81ca8c780b/e19d434d-47ab-4f10-8cd3-6fe5e17c1745/Untitled.png)
![에러 확인 예시](https://prod-files-secure.s3.us-west-2.amazonaws.com/5ae1257a-34e7-42fd-9eac-be81ca8c780b/8f4de828-8a47-4e8f-a07c-fe1fd3aa4c75/Untitled.png)
```

