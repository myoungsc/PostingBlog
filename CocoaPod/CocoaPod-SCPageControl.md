# SCPageController

## 설명
커스텀 한 PageController입니다. 페이징된 스크롤에 연결이 되어서 스크롤이 움직임에 따라 컨트롤 되는 라이브러리 입니다. 제가 처음으로 만들어본 CocoaPod 컨트롤러 입니다. 오토레이아웃은 쓰지 않았고 가운데 정렬되어서 프레임에 맞추는데, xib나 storyboard에서는 큰틀만 잡아 주면 됩니다.

## Github 주소
https://github.com/myoungsc/SCPageControl

## 스크린샷
![](https://github.com/myoungsc/SCPageControl/blob/master/ScreenShot/SCPageControl.gif?raw=true)

## 작업한 환경
```Swift
* Swift 3.0.1
* XCode 8.3.1
* iOS 9.0 (Min SDK)
* Not Use Autolayout
```

## 설치방법
다른 CocoaPod 처럼 설치 하시면 됩니다.
```Swift
1. 터미널에서 해당 프로젝트 디렉토리로 이동한 후 'Pod init'
2. 디렉토리에 있는 PodFile에 (pod "SCPageControl")를 추가
3. 터미널에서 'pod install'
```

## 사용방법
```Swift
public enum SCPageStyle: Int {
    case SCNormal = 100
    case SCJAMoveCircle // Design by Jardson Almeida
    case SCJAFillCircle // Design by Jardson Almeida
    case SCJAFlatBar // Design by Jardson Almeida
}

let sc = SCPageControlView()

override func viewDidLoad() {
    super.viewDidLoad()

	sc.frame = CGRect(x: 0, y: UIScreen.main.bounds.size.height-50, width: UIScreen.main.bounds.size.width, height: 50)
	sc.scp_style = .SCNormal
	sc.set_view(5, current: 0, tint_color: UIColor.red)
	view.addSubview(sc)
}

//MARK: ScrollView Delegate
func scrollViewDidScroll(_ scrollView: UIScrollView) {
	sc.scroll_did(scrollView)
}
```

## 라이센스
라이센스는 MIT라이센스를 따릅니다. 앱에 적용하실때는 사용하였다고 명시만 해주시면 됩니다.