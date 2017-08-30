##SCWebPreview

###설명
페이스북, 카카오톡에서 URL을 공유하게 되면 미리보기 형식으로 이미지, 제목, 내용을 보여주는 창들이 있습니다. 그런 창들을 쉽게 구현 할 수 있게 도와주는 라이브러리 입니다. 원리는 html tag중에 meta data중 og:(og:url, og:image, og:title, og:description) 속성을 가지고 있는 내용을 가져와서 사용 할 수 있게 구성 되어 있습니다.

###Github 주소
https://github.com/myoungsc/SCWebPreview

###스크린샷
![](https://github.com/myoungsc/SCWebPreview/blob/00447772b63ca0ab15556b7ae260776b098a12b9/SCWebPreview_ScreenShot.gif?raw=true)

###작업환경
```Swift
* Swift 3.0.1
* XCode 8.3.3
* iOS 9.0 (Min SDK)
```

###설치방법
일반적인 CocoaPod 설치 방법과 동일합니다.
```Swift
1. 터미널에서 해당 프로젝트 디렉토리로 이동한 후 'Pod init'
2. 디렉토리에 있는 PodFile에 (pod "SCWebPreview")를 추가
3. 터미널에서 'pod install'
```

###사용방법
- SCWebPreview를 import 합니다.
```Swift
import SCWebPreview
```

- HTML에서 metaData를 가져옵니다.([String]배열을 통해 url을 넣어 주시면 됩니다.)
```Swift
let webPages: [String] = ["https://github.com/myoungsc", "http://devsc.tistory.com/"]
let scWebPreview = SCWebPreview()
scWebPreview.initWebPages(webPages)
scWebPreview.startCrawling(){
    for i in 0 ..< webPages.count {
        let dic = self.scWebPreview.getPreviewDataFromIndex(i)
        guard dic.count != 0 else {
            print("error: dic is optionl Value")
            return
        }
        //doSomething
    }
}
```

- 데이터를 가져오는 방법입니다.
```Swift
let dicWebData: [String: String] = scWebPreview.getPreviewDataFromIndex(0)
print("og:url - \(dicWebData["og:url"]!)")
print("og:url - \(dicWebData["og:title"]!)")
print("og:url - \(dicWebData["og:description"]!)")
print("og:url - \(dicWebData["og:image"]!)")
```

- 해당 인덱스의 url를 사파리로 오픈 하는 방법입니다.
```Swift
scWebPreview.openSafariFromUrl(0)
```

###라이센스
라이센스는 MIT라이센스를 따릅니다. 앱에 적용하실때는 사용하였다고 명시해주셔야됩니다.