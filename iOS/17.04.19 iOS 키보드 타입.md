

#iOS 키보드 타입

안녕하세요. 개발자 Myoung 입니다. 
오늘은 iOS 키보드 타입에 대한 포스팅입니다. Objective-C,Swift 둘다 해당되는 타입형태입니다. UITextFeild, UITextView등 키보드를 사용하는 뷰에서 사용됩니다.

###키보드 타입 종류

```
typedef enum {
        UIKeyboardTypeDefault,               	// 기본적인 키보드
        UIKeyboardTypeASCIICapable,           	// 영문만 표시되는 키보드
        UIKeyboardTypeNumbersAndPunctuation,  	// 숫자와 특수문자가 표시되는 키보드
        UIKeyboardTypeURL,                    	// URL을 입력할 수 있도록 .과 / 그리고 .com이 키보드 영역에 표시되는 키보드
        UIKeyboardTypeNumberPad,             	// 숫자를 입력하는 키패드 형식의 키보드
        UIKeyboardTypePhonePad,               	// 전화 번호를 입력할 수 있는 키패드 형식의 키보드
        UIKeyboardTypeNamePhonePad,          	// 대문자 입력이 불가한 키보드
        UIKeyboardTypeEmailAddress,           	// 이메일을 입력할 수 있도록 @와 .이 키보드 영역에 표시되는 키보드
        UIKeyboardTypeDecimalPad,             	// 소숫점을 입력할 수 있는 키패드 형식의 키보드
        UIKeyboardTypeTwitter,                	// 트위터 입력을 빠르게 할 수 있도록 @와 #이 추가된 키보드
        UIKeyboardTypeWebSearch,              	// URL 및 검색어 입력에 최적화 됨 (공백 및. 표시)
        UIKeyboardTypeAlphabet = UIKeyboardTypeASCIICapable, // 더 이상 사용 안함
    } UIKeyboardType;
```


###사용법

사용법은 매우 간단 합니다. 코드로는 setKeyboardType을 사용하시면 됩니다.

####ObjectiveC
```
[textField setKeyboardType:UIKeyboardTypeEmailAddress];
```
####Swift
```
textField.keyboardType = .default
```

스토리 보드 상에서는 UITextFeild, UITextView View에 추가 하신 후 오른쪽 항목에서 보시면
KeyBoard Type이 있습니다. 거기서 적절하게 선택 해주시면 됩니다.

















