---
title: iOS11短信过滤
date: 2017-11-02 20:44:59
tags:
- iOS
- SMS
- ILMessageFilterExtension
categories: 开发
---

## Message Filter Extension

1. 创建 Message Filter Extension。在已有的项目中，选择菜单 File -> New -> Target...，创建 FilterExtension。

    ![创建 Message Filter Extension](iOS11短信过滤\NewMessageFilterExtension.png)

2. 实现过滤。编写过滤关键词的代码，打开文件 MessageFilterExtension.swift
```swift
    private func offlineAction(for queryRequest: ILMessageFilterQueryRequest) -> ILMessageFilterAction {
        guard let messageBody = queryRequest.messageBody else {
            return .none
        }
        
        return isFilter(messageBody) ? .filter : .none
    }
    
    private func isFilter(_ messageBody: String) -> Bool {
        let filterKeywords = ["优教育",
                              "今日新股发行",
                              "平安陆金所",
                              "集金学堂",
                              "苏宁金融",
                              "爱城市网",
                              "飞贷金融科技",
                              "家长帮",
                              "test",
                              "测试"]

        for keyword in filterKeywords {
            if messageBody.contains(keyword) {
                return true
            }
        }

        return false
    }
```

3. 设置短信过滤插件。打开手机的 设置 -> 信息 -> 未知与过滤信息 -> 短信过滤 中设置你的短信过滤插件打开。

    ![设置短信过滤插件](iOS11短信过滤\设置短信过滤插件.png)

4. 查看短信过滤效果。

    ![短信过滤效果](iOS11短信过滤\短信过滤效果.png)

5. 关于短信过滤与隐私

    ![关于短信过滤与隐私](iOS11短信过滤\关于短信过滤与隐私.png)

## 参考

1. [iOS 11 短信拦截功能初探](https://yq.aliyun.com/articles/98864)
2. [IdentityLookup](https://developer.apple.com/documentation/identitylookup)
3. [Filtering Unwanted Messages with Identity Lookup](https://developer.apple.com/videos/play/wwdc2017/249/)
4. [Swift的Guard语句](http://www.jianshu.com/p/3a8e45af7fdd)
5. [iOS 11 短信过滤扩展简介](https://zhuanlan.zhihu.com/p/27560301)
