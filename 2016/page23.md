#  iOS之iphone watch开发

如有兴趣，希望您能参与一起维护这个项目「iOS之iphone watch开发」

### 来自官方文档

- Human Interface Guidelines(https://developer.apple.com/watch/human-interface-guidelines/）
- App Essential(https://developer.apple.com/library/ios/documentation/General/Conceptual/WatchKitProgrammingGuide/CreatingtheUserInterface.html#//apple_ref/doc/uid/TP40014969-CH4-SW1）
- Glance Essentials(https://developer.apple.com/library/ios/documentation/General/Conceptual/WatchKitProgrammingGuide/ImplementingaGlance.html#//apple_ref/doc/uid/TP40014969-CH5-SW1）

* * *

### 交互和UI类

1. Watch只支持这么几种手势：系统的点击、force touch、digital crown旋转，不支持自定义手势。交互方式上会比较受限，在手机App上能实现的手势很多都在Watch上用不了。

2. Crown的所有操作都是Watch定义好的，不要试图对Crown的操作做任何定义。

3. 苹果希望Glance能在不同时间不同地点展示不同的内容。Glance是依靠模板展现的，并且一旦你选定一个模板就不能改了。所以选模板很重要，需要能适应所有的情况。


* * *

### 开发类

1. 很多接口不对外，比如不支持动画（只支持帧动画），只有原生地图支持动态渲染地图引擎，原生的地图可以放大缩小。

2. Notification分为短通知和长通知，短通知显示的是title，长通知显示的是body。但是以前手机app通常只有body没有title，所以要修改应用的推送接口，支持title，否则短通知就是空的。

3. 找到真机适配，字体、图片、布局都有可能异常。


* * *

### 几个tips

1. 模拟器iPhone锁屏的时候，手表会不可用，这是模拟器bug，真机没这个问题

2. 模拟器在iPhone app进程没启动的时候可以唤醒iPhone的host app，真机不行（但是官方app可以，因为目前第三方的app全都是extension形式运行，并不是watch上面的native app

3. 模拟器在iPhone横屏的时候，force touch手表会导致手表有一瞬间横屏，放心，这个也是模拟器bug

4. 真机的性能可能没有你想象的那么好，特别是对于数据传输方面，并不是一直能保持很稳定的速度，要尽量缩减iPhone和watch之间的数据传递，只在有数据变化的时候去做刷新

5. 使用Darwin Notification来做iPhone和watch的双向通知
这个特别重要，以至于需要解释一下。
当你的iPhone端数据变化的时候需要通知到watch，Foundation框架下的NSNotificationCenter是没有用的，需要使用CoreFoundation的Darwin Notification，可以参考下notify.h上面的接口。
事实上不仅仅是watch和iPhone可以这么做，keyboard extension和host app也可以。（他们都是extension）。

6. 使用presentTextInputControllerWithSuggestions来进行语音输入

7. 构建UI的一些技巧
    - A. 使用嵌套的group来处理一些布局关系
    - B. 选中多个组件可以合并调整他们的位置关系
    - C. 可以对38mm和42mm建立不同的size
    - D. 使用startAnimatingWithImagesInRange来实现动画，要准备好一堆的图
    - E. 利用hidden来做一些界面变化的效果


    