# SCCardView

## 설명
뷰 밑에 있는 카드를 선택하여 상단에 있는 전체뷰를 바꿔주는 controller 입니다. 카드영역은 콜렉션뷰를 사용하였고 위에 내용이 표시되는 부분은 커스텀 하여서 원하는 목록을 넣어서 사용 할수 있습니다.

## Github 주소
https://github.com/myoungsc/SCCardView

## 스크린샷
![](https://github.com/myoungsc/SCCardView/blob/master/SCCardView.gif?raw=true)

## 작업한 환경
```Swift
* Swift 3.0.1
* XCode 8.3.1
* iOS 9.0 (Min SDK)
```

## 설치방법
다른 CocoaPod 처럼 설치 하시면 됩니다.
```Swift
1. 터미널에서 해당 프로젝트 디렉토리로 이동한 후 'Pod init'
2. 디렉토리에 있는 PodFile에 (pod 'SCCardView')를 추가
3. 터미널에서 'pod install'
```

## 사용방법
```Swift
import SCCardView

// Int index, [String: String] key, Value
// Make dummy data (Necessary key Image Card UI)
let dummyData: [Int: [String: Any]] = [0: ["image": UIImage()!,
                                          "title": "Catholic Church",
                                          "url": "https://github.com/myoungsc/SCCardView/blob/master/Example/SCCardView/Images.xcassets/sc0.imageset/sc0.jpg?raw=true",
                                          "description": "Maybe famous Catholic Churchsadl"],
                                       1: ["image": UIImage(named: "sc1")!,
                                           "title": "Beautiful Sea",
                                           "description": "Beautiful sea anywhere on earth"],
                                       2: ["image": UIImage(named: "sc2")!,
                                          "title": "Famous temple",
                                           "description": "A landscape of famous temple"],
                                       3: ["image": UIImage(named: "sc3")!,
                                          "title": "Pretty Flower",
                                          "description": "Pretty Flower\nphoto  by myoung father"],
                                       4: ["image": UIImage(named: "sc4")!,
                                          "title":"Vast Sky",
                                          "description": "Vast korea sky\nphoto by myoung father"],
                                       5: ["image": UIImage(named: "sc5")!,
                                          "title": "Leaf",
                                          "description":"Leaf anywhere on Korea\nphoto by myoung father"]]

sccard.delegate = self
sccard.cardStyle = .onlyTop
//if cardstyle round cutom
/*
 sccard.cardStyle = .custom
 sccard.initCustomCardStyle([.topLeft, .bottomRight])
 */
sccard.initialViewData(dummyData)

// Set initial value
if let dicSubData: [String: Any] = dummyData[0] {
    if let img: UIImage = dicSubData["image"] as? UIImage,
        let title: String = dicSubData["title"] as? String,
        let des: String = dicSubData["description"] as? String {
        sccardSubImg.image = img
        sccardSubTitle.text = title
        sccardSubDes.text = des
    }
}
// Autolayout bottom card ratio
contBottomDes.constant = sccard.bottomInterval


// Delegate
// Selector Card Click. Required Delegate
func SCCardSelectorCard(_ index: Int, dic: [String: Any]) {
    if let img: UIImage = dic["image"] as? UIImage,
        let title: String = dic["title"] as? String,
        let des: String = dic["description"] as? String {
        sccardSubImg.image = img
        sccardSubTitle.text = title
        sccardSubDes.text = des
    }
}

// Refresh content view from down image. Required Delegate
func SCCardURLIndexRefresh(_ img: UIImage) {
    sccardSubImg.image = img
}

// Card Down Gesture. optional Delegate
internal func SCCardDownCardAction(_ indexPath: IndexPath) {
    print("down gesture \(indexPath)")
}

// Card Up Gesture. optional Delegate
internal func SCCardUpCardAction(_ indexPath: IndexPath) {
    print("up gesture \(indexPath)")
}
```

## 라이센스
라이센스는 MIT라이센스를 따릅니다. 앱에 적용하실때는 사용하였다고 명시만 해주시면 됩니다.