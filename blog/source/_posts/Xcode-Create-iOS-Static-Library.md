---
title: Xcode Create iOS Static Library
date: 2017-11-27 14:09:58
tags:
- iOS
- 静态库
- C
categories: 开发
---

> 创建一个iOS静态库，使用C语言开发。

## 创建静态库

![](Xcode-Create-iOS-Static-Library\Create-iOS-Cocoa-Touch-Static-Library.png)

## 编译配置

- 当你开发的时候使用的iOS SDK 11时，想要让发布的版本可以在iOS SDK 8以上都可以运行，就需要设置：Build Setting -> Architecture -> Build Active Architecture Only = No; Build Setting -> Deployment -> iOS-Deployment-Target = iOS 8.0

    ![](Xcode-Create-iOS-Static-Library\Build-Active-Architecture-Only.png)

    ![](Xcode-Create-iOS-Static-Library\iOS-Deployment-Target.png)

## 发布Release

![](Xcode-Create-iOS-Static-Library\Edit-Scheme-Menu.png)

![](Xcode-Create-iOS-Static-Library\Edit-Scheme-Dialog.png)

## 参考

1. [Guomi](https://github.com/vwarship/Guomi)
2. [Xcode7打包Framework](http://www.jianshu.com/p/a8366426fe51)
3. [Xcode4 Linking Problem. File was built for archive which is not the architecture being linked (arm6)](https://stackoverflow.com/questions/5303933/xcode4-linking-problem-file-was-built-for-archive-which-is-not-the-architecture)
4. [Error: “File was built for archive which is not the architecture being linked (armv7s)”](https://stackoverflow.com/questions/14828693/error-file-was-built-for-archive-which-is-not-the-architecture-being-linked-a)
5. [xcode编译时，有第三方库时，编译设置build active architecture only问题](http://blog.csdn.net/ysysbaobei/article/details/16371263)
6. [ld: warning: ignoring file](https://stackoverflow.com/questions/22910866/ld-warning-ignoring-file)
7. [iOS生成静态库方法-iOS集成静态库-iOS合并静态库](http://blog.sina.com.cn/s/blog_7b9d64af0101jlym.html)
8. [iOS黄色警告之was built for newer iOS version (7.0) than being linked (6.0)解决办法](http://blog.csdn.net/l2i2j2/article/details/51184515)
9. [Creating a Static Library in iOS Tutorial](https://www.raywenderlich.com/41377/creating-a-static-library-in-ios-tutorial)
10. [iOS App使用OpenSSL](https://vwarship.github.io/2017/10/25/iOS-App使用OpenSSL/)
11. [在ios中调用C语言的国密算法SM2以替换RSA](http://blog.csdn.net/qq_15509071/article/details/51862664)
