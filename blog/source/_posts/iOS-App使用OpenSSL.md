---
title: iOS App使用OpenSSL
date: 2017-10-25 19:53:40
tags:
- iOS
- Swift
- OpenSSL
categories: 开发
---

## 编译 [OpenSSL-for-iPhone](https://github.com/x2on/OpenSSL-for-iPhone)

``` bash
git clone https://github.com/x2on/OpenSSL-for-iPhone.git
cd OpenSSL-for-iPhone/
./build-libssl.sh --version=1.1.0f
```

## 使用 OpenSSL

### 创建 iOS 工程。

### 拷贝 OpenSSL 头文件和库文件。

* 从 OpenSSL-for-iPhone 目录下拷贝 include 和 lib 目录到新创建的工程目录下面。

### 新建文件 UseOpenSSL-Bridging-Header.h

``` c
#import <openssl/md5.h>
#import <openssl/sha.h>
#import <openssl/evp.h>
```

### 配置工程属性。

* <b>Build Settings</b>，通过在搜索框中输入 Search Paths 快速过滤
    <b>Header Search Paths</b>    include/**
    <b>Objective-C Bridging</b>    Header UseOpenSSL/UseOpenSSL-Bridging-Header.h

### 添加库文件。

* 在左侧工程导航栏中的工程上单击右键，选择 New Group without Folder 菜单项，创建 Frameworks 。

* 增加库文件 libssl.a libcrypto.a 到 Frameworks 下。

### Swift 调用 OpenSSL 生成 md5

``` swift
import UIKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()

        let string = "Hello World!"
        let outStringLength = Int(MD5_DIGEST_LENGTH)
        let outStringPtr = UnsafeMutablePointer<UInt8>.allocate(capacity: outStringLength);
        
        MD5(string, outStringLength, outStringPtr)
        
        let md5 = NSMutableString()
        for i in 0..<outStringLength {
            md5.appendFormat("%02x", outStringPtr[i])
        }
        print(md5)
        
        outStringPtr.deallocate(capacity: outStringLength)
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
    }

}
```

## 参考

1. [CommonHMAC in Swift](https://stackoverflow.com/questions/24099520/commonhmac-in-swift/)
2. [iOS Use OpenSSL sample](https://github.com/vwarship/Samples/tree/master/iOS/Practice/UseOpenSSL)
