---
title: 使用Swift开发App入门课程笔记
date: 2017-10-17 08:22:46
tags:
- Swift
- App
categories: 开发
---

## 第11课：做出决策

> 迅速进入主题。最好不要将你的 app 的初始视图设计成登录屏幕或者一个大大的​“开始”按钮。让人们看到 app 的第一个屏幕时就能够立即开始使用。大多数用户想要使用你的 app 做什么用？就将它做成初始视图。到 app 的主要部分需要轻点几下？答案应该是——非常少。

> 建议你先让他们对 app 有个大致的了解，再去关注那些细节问题。

## 第12课：实例、方法和属性

> 原型
> 现在，你可能有了中意的 app 创意，一个超越其他、深得你心的创意。如果所有创意都让你感觉兴味索然，那就返回到创意列表，从头开始。因为现在要真正开始构建 app 了。
> 在 app 日志中，至少为你的 app 界面写下或草拟三个外观视图。尤其是，想想一个新用户打开 app 之后的前 10 秒的情形。
> - 用户看到的第一个屏幕（视图）是什么？显示哪些按钮？接下来会怎样？
> - 想想你的 app 将显示哪些类型的图形和图标。
> - 用户需要轻点几下能够找到想要知道的内容？
> - 用户如何在视图之间进行导航？
> - 不需要使用文字就能表达 app 功能的简单方法有哪些？

## 第13课： QuestionBot

> 标准研发过程是进行更改、构建并运行、测试更改。有时候，你所处理的那部分 app 可能工程量巨大，或者有些工作相当耗时，但不管怎样，一定要进行测试。

> 这是一种理想的 app 构建方式——各工作部分相互之间尽可能没有交集，并且每个部分只完成一个核心任务。也就是说，每个部分各自独立构建完成并确保毫无差错后，再整合到一起。

> 你真正的目标用户是谁？
> 现在你有一个想要构建的 app 并且设计了初始的几个屏幕，是时候重新考虑你的目标用户了。想出几类将会使用你的 app 的人群。写下每种类型用户的特征描述。这个人是做什么的？多大年纪？为什么要使用这个 app？她如何找到自己需要知道的内容？她喜欢图片还是喜欢文字？她珍爱自己的设备还是凑合用用？

## 第14课：数组与循环

> 测试
> 你有自己的原型，并且清楚知道目标用户是谁。现在应该去寻求现实生活中的人们对于你所设计的视图的反馈。你完全可以进行一些用户测试。
> 在索引卡上重新绘制最新的原型视图。每张卡代表一个视图，测试用户可以快速翻阅并假装他们正在使用你的 app。每次他们“轻点”按钮时，你就切换到下一张卡。
> 找几个适合充当目标用户角色的人员。在他们浏览索引卡的时候，问他们知不知道要怎样在 app 中进行操作。他们知道要轻点哪些按钮吗？他们喜欢你的 app 吗？他们觉得这个 app 有用吗？
> 将你的调查结果记录在 app 日志中。

## 第15课：定义结构

> 那么就将这视为一次对于勇气的考验。你务必要确定你所做的是自己坚信的事情。

## 第16课： QuestionBot 2

> 再谈原型…
> 纸上原型是着手开发和测试 app 创意的有效途径。 后续的每个原型都会推动你走近那个直观又悦人的界面。不过，当你一步步接近最终设计时，务必要在实际设备（类似于你为之进行设计的设备）上进行原型制作。你可以观察用户手握设备的方式，看看他们的手指与界面进行互动时会出现什么情况，并检查你的按钮是否太大或太小。
> 纸上原型之后，你可以使用 Keynote 应用程序模拟 app 的不同视图。你主要是模拟 iOS 环境即可，不必完成幕后编程。你要做的就是从视图上的界面元素创建链接，将一张 Keynote 幻灯片链接到另一张幻灯片。当你创建了足以完美模拟导航的幻灯片和链接之后，就可以在目标设备上播放演示文稿，看看用户是如何与屏幕进行互动的。
> 在日志中仔细规划 Keynote 原型中要使用的视图。在 Keynote 中创建视图，然后不断完善。这次，除了考虑用户在屏幕之间可能的导航方式之外，还要对屏幕上的每个元素进行设计。你可以在 Keynote 中随意尝试各种按钮、图标和文本的颜色、大小和位置等。从 Iterative UI Design 的 WWDC 观看此视频，来了解有关使用 Keynote 设计 app 和创建原型的更多信息。

## 第17课：操作和出口

> 故事板与代码之间有两种类型的连接：
> 出口会将代码中的变量连接到故事板中的对象，这样就可以从代码中访问那些对象，并且在 app 运行时获取信息或进行更改。
> 操作会将开关和按钮等控件连接到代码中的方法，如此一来，举例来说，轻点某个按钮即会运行特定方法。

> 创建出口
> 白色背景上的白色视图难以分辨。选择“Editor”>“Canvas”>“Show Bounds Rectangles”，显示场景上每个内容的轮廓。
> 转到“View”>“Assistant Editor”>“Show Assistant Editor”打开助理编辑器。如果助理编辑器中没有显示 ViewController.swift，确保按以下方式设置助理编辑器顶部的跳转栏：
> 按住 Ctrl 键从视图拖移（按住 Ctrl 键，然后用鼠标或触控板点按并拖移）到代码中。
> ![出口](使用Swift开发App入门课程笔记\outlet.png)
> 上图中内容的详细说明从左到右依次为：
> - 圆圈：实心的圆圈表示该出口已连接。如果出口未连接，则为空心圆圈。
> - @IBOutlet weak：这是通知 Xcode 此行上的属性是出口。
> - var colorView：这是属性的声明，你对此已有所了解。
> - : UIView!：属性的类型是 UIView!。感叹号表示，如果出口未连接，而你尝试访问此属性，那么 app 将崩溃。UIView 是所有 iOS app 中使用的基本视图类型。屏幕上显示的所有内容几乎都是一种 UIView，负责绘制和处理触摸。

> 函数 viewDidLoad()，当视图控制器准备好显示在屏幕上时，就会调用此函数。

> 创建操作
> 连接出口和操作的方法有很多种。按住 Ctrl 键从故事板拖移到代码会创建新的出口和操作。创建完成之后，就可以通过“Connections”检查器或使用代码文件中的圆圈图标进行连接、断开连接和重新连接操作。
> 哪一种方法更好？如果想知道故事板中的特定对象连接到哪些出口和操作，可使用​“Connections”检查器。如果想知道特定出口或操作连接到哪些对象，可使用代码中的圆圈图标。

> 滑块
> 为什么要增加开关之间的间距呢？你现在所使用的模拟器是带光标的，可以精准地点击非常小的对象。但是使用通过手指进行操作的设备时，界面元素的周围必须有更多的空间。

> 润饰界面
> 设置开关的色调
> 要修正第一个问题，可以使用可用于许多控件的着色选项。开关有两种自定颜色：开启色调和滑块色调。所对应的开关区域如下所示：
> ![开关](使用Swift开发App入门课程笔记\uiswitch.png)

> 所有控件都有 isEnabled 属性，通过该属性可以激活或取消激活控件。控件的状态会伴随控件外观的改变，例如，变暗。

> 这一次，你可以先观察用户与原型的互动情况，然后再向他们提出问题。将你的 Keynote 原型交给他们，让他们像平时尝试新的 app 那样感受一下你的 app。你不可能永远做到随时指导用户，因此观察他们独立操作的情形非常重要，有助于你在设计时就预见到用户可能的行为。将你观察到的一切记录在日志中，例如，他们对哪里感到困惑，或者哪些内容真正吸引了他们。

## 第18课：自适应用户界面

> 通过​“自动布局”，可以设置用于定义视图布局方式的规则，称为约束。
> ![约束](使用Swift开发App入门课程笔记\constraints.png)

> 在很多 app 中，主用户界面均类似于视图堆栈或列表，并且该堆栈的运行方式都是从上到下或从左到右。你可以使用“自动布局”​中的约束来定义这种类型的界面，不过 iOS 提供了一种更为方便的方法，叫做堆栈视图。

> 请注意，在“Size”检查器中更改大小不会设置约束；它只会在 Interface Builder 中调整大小。
> ![设备视图尺寸](使用Swift开发App入门课程笔记\view-size.png)
> ![增加约束](使用Swift开发App入门课程笔记\add-new-constraints.png)

> 请注意，堆栈中的视图将显示为居中、左对齐或右对齐，具体取决于点按“Stack”​按钮之前视图的排列方式。

> 选择堆栈视图需要窍门。请选择以下其中一种技术：
> 1. 从堆栈视图外部拖拽滑过堆栈视图。
> 2. 从大纲视图中选择“Stack View”（请参阅左侧图像）。

> 堆栈视图设置是：
> 1. Alignment：设置视图在堆栈中的排列方式。
> 2. Spacing：设置堆栈中各视图之间的间距。

> 使用 Command-Control-Space，打开表情符号挑选器。

> 调整按钮大小以适合内容：
> 1. 确保选中按钮。
> 2. 从菜单中选择“Editor”>“Size to Fit Content”，或使用键盘快捷键 Command-=。

> 复制UI以创建新UI：
> 1. 选择UI。
> 2. 从菜单中选择”编辑”>“Duplicate”，或使用键盘快捷键 Command-D。

> 检查点
> 用户界面的布局已完成。应当及时确认它是否准确地适应其用途。选择不同的设备以更改画布的大小，并将方向从纵向更改为横向。

> 你可以使用所学过的知识在自己的 app 中构建自适应用户界面。以下是需要遵循的一些指导原则：
> - 为最小的设备而设计。这可确保你的设计适合于其他（较大）设备。
> - 使用约束定义图像视图的高度和宽度。这样，无需调整图像视图的大小也可以容纳非常大的图像。
> - 首先，添加并排列视图，然后选择这些视图并创建堆栈视图。
> - 使用堆栈视图设置（如间距和对齐）创建各种界面效果。
> - 嵌套堆栈视图来创建更加复杂的用户界面。务必尽量从最里面的堆栈视图开始。
> - 使用约束将最外面的堆栈视图设为水平和垂直居中，以确保用户界面在所有设备上均居中。
> - 在添加约束后解决“自动布局”问题。选择“Resolve Auto Layout Issues”菜单中的​“Update Frames”，以去掉那些烦人的橙色线。

## 第19课：枚举和Switch

> 如果支持 VoiceOver，用户就可以在看不到屏幕的情况下完全依靠声音在你的 app 中进行导航。其次，你的 app 必须与许多管理机构所采用的辅助功能指导原则保持同步。最后，满足所有用户的需求就是真理。

## 第20课：结业项目

> GameplayKit 框架中包含一个 API，可用来生成随机数字，并能够构建游戏更复杂的部分。你以前从未接触过这个框架，以下将提供逐步说明。
> 在 Sign.swift 文件的顶部添加 import GameplayKit。
> 添加该 import 语句后，你就可以使用该框架中的 API。
> 将以下行添加到该文件（这是高层次设置，任何结构或枚举定义中都未包含）：
> let randomChoice = GKRandomDistribution(lowestValue: 0, highestValue: 2)
> 如果在 randomChoice 上调用 nextInt() 方法，GKRandomDistribution 实例将提供一个介于构造器中指定的两个值之间的随机 Int。

> 设置按钮的“isHidden”属性的值来隐藏

## 第21课：接下来...

> The Swift Programming Language Guide
> 这是全面的 Swift 官方编程指南，其中不仅包含 Swift 编程中的新增主题，而且还对本课程中的一些内容进行了更为深入的讲解。本指南提供在线版本。
> iOS Human Interface Guidelines
> 这些指南阐述了 iOS app 用户界面设计原则，其中不仅提供了 iOS app 设计的高级信息，而且描述了特定的 UI 元素及其在 app 中的应用方式。这些指南以书籍或在线形式提供。
> WWDC 视频
> WWDC 会议视频涵盖了 Apple 软件开发的方方面面。有关 Xcode 和 Interface Builder 的会议中包含大量演示和演练，对于开发新手尤为有用。你可以在 Apple Developer 网站上观看所有会议。
> Start Developing iOS Apps
> 通过此在线教程，你能够以另外一种方式练习本课程中所学到的一些基础知识，还可以了解许多新增主题。在 Apple Developer 网站上进行查看。

## 其它资源

> 进一步了解《[人人能编程](https://www.apple.com/cn/everyone-can-code/)》课程。
> 进一步了解 [Swift Playgrounds](https://www.apple.com/cn/swift/playgrounds/)。
> 查阅其他《人人能编程》书籍：
> Swift Playgrounds 教师指南
> 使用 Swift 开发 App 入门课程教师指南
> 进一步了解 [Swift](https://developer.apple.com/swift/)。
> 查找用于为 Mac、iPhone、iPad 和 Apple Watch 创建 ​app 和配件的工具与资源。
> 在 Apple Developer Forum 中与其他程序员建立联系。
> 进一步了解如何提交 app 到 App Store。
> 查看支持编程教学的其他资源。
