# SCTableIndex

## 설명
섹션을 사용하지 않고 테이블에 들어갈 String의 초성을 가지고 인덱스를 만드는 라이브러리입니다. 섹션 인덱스가 필요 할경우 활용해서 사용하실수 있습니다.

## Github 주소
https://github.com/myoungsc/SCTableIndex

## 스크린샷
![](https://github.com/myoungsc/SCTableIndex/blob/master/SCTableIndex.gif?raw=true)

## 작업한 환경
```Swift
* Swift 4
* XCode 9.1
* iOS 9.0 (Min SDK)
```

## 설치방법
다른 CocoaPod 처럼 설치 하시면 됩니다.
```Swift
1. 터미널에서 해당 프로젝트 디렉토리로 이동한 후 'Pod init'
2. 디렉토리에 있는 PodFile에 (pod 'SCTableIndex')를 추가
3. 터미널에서 'pod install'
```

## 사용방법
```Swift
import SCTableIndex

arrItem.sort()
sctbindex.delegate = self
//Use Selector Font, HelveticaNeue-Medium is Normal Font
//sctbindex.initialFont = UIFont(name: "HelveticaNeue-Medium", size: 13)!
//Use Selector initial Text Color, black is Normal Color
//sctbindex.initialTextColor = UIColor(red: 50.0/255.0, green: 50.0/255.0, blue: 50.0/255.0, alpha: 1.0)
//String Array item
sctbindex.setView(arrItem)


//MARK: SCTableIndex Delegate
extension ViewController: SCTableIndexDelegate {
    // Move starting point item that select initial text
    func scTableIndexReturnInitialText(_ strInitial: String, index: Int) {
        tbMain.scrollToRow(at: IndexPath(row: index, section: 0), at: .top, animated: true)
    }
}
```

## 라이센스
라이센스는 MIT라이센스를 따릅니다. 앱에 적용하실때는 사용하였다고 명시만 해주시면 됩니다.