---
title: 编辑UITextField和UITextView时如何隐藏键盘
date: 2017-11-06 09:36:26
tags:
- UITextField
- UITextView
categories: 开发
---

> 当编辑完 UITextField 和 UITextView 控件后，键盘出来了就遮住了下面的控件，想操作下面的控件又被遮住了。
    
```swift
import UIKit

class ViewController: UIViewController, UITextFieldDelegate, UITextViewDelegate {
    @IBOutlet weak var textField: UITextField!
    @IBOutlet weak var textView: UITextView!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        textField.returnKeyType = .done // 换行变成完成
        textView.returnKeyType = .done
        
        textField.delegate = self
        textView.delegate = self
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
    }
    
    func textFieldShouldReturn(_ textField: UITextField) -> Bool {
        print(">>textFieldShouldReturn")
        
        textField.resignFirstResponder()
        return true
    }
    
    func textView(_ textView: UITextView, shouldChangeTextIn range: NSRange, replacementText text: String) -> Bool {
        if text == "\n" {
            print(">>textView")
            
            textView.resignFirstResponder()
            return true
        }

        return true
    }

}
```

## 参考
1. [UITextField UITextView Hide Keyboard](https://github.com/vwarship/Samples/tree/master/iOS/Practice/UI/UITextXXXHideKeyboard)
2. [iOS 键盘处理（改变键盘为完成键），UITextField键盘显示隐藏，弹出，回弹](http://www.jianshu.com/p/8ddf5beaf702)
3. [Swift - 文本输入框（UITextField）的用法](http://www.hangge.com/blog/cache/detail_530.html)
4. [swift中UITextView的使用](http://blog.csdn.net/st646889325/article/details/52804678)
