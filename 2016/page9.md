###建议一
+ 了解apple新技术，作为程序员应该知道这一点的重要性
+ 修炼自己的基本功
+ 了解FRP函数式编程，对应框架就是ReativeCocoa和RxSwift
+ 造属于自己轮子，当自己以设计者的方式来思考问题获取能收获更多
+ 贡献自己东西，把自己的思想和心得写成文章可能才能印象更深刻。尝试翻译英文的博客，利人利己才能有提高

###建议二
+ 会熟练使用Profile性能调优。比如其中有一个time Profile会告诉哪行代码执行花费较长的时间，哪里出现卡顿，这样我们就可以知道哪里出现问题可以进行优化
+ 写测试，写测试，不仅仅可以帮助自己找bug，更重要的是会让自己思考如何更好的架构自己的应用，很多的优秀的工程师，代码架构能力都是很不错的。同时也会用OSX server和xcode配置continue intergration
+ 能够轻松编写多线程代码，熟悉nsoperation，gcd等
+ 熟悉一些常用的系统类库原理和best practice，比如core data，这些玩意要玩好，但是要话费很长时间
+ iOS应用，UI占很重要的一部分，可能部分时候需要自己使用默认之间，有时候自己必须要实现组件和动画，core animation 和uidynamics都需要学习
+ 要解决一个问题或者要实现一个功能时候，尽量自己去实现，除非性能太差或者逻辑过于复杂时候，才会自己去找第三方的库
+ 手头的项目要是没有什么高的要求，没有性能问题要解决，对于很多细节问题无所谓的公司，作为有要求的工程师应当跳槽吧，或者自己去尝试帮助自己提高，总会学习新的api和技术

###建议三
+ 来测试一下自己，比如对objective-c有做够了解吗？OC是如何基于c来封装？解释一下下面两行代码是啥意思？
''
''typedef __attribute__((NSObject)) CGGradientRef GradientObject;
'' @property (nonatomic, strong) GradientObject storedGradient;
'' 
+ protocol、category这样的东西应该手到擒来，多线程的知识点掌握的是否扎实？runtime这种黑魔法研究过没有？代码是否足够优雅，后续维护容易吗？各种设计模式也该有所了解吧
+ 熟悉的掌握两年的view，那么能快速仿造主流一app的ui吗？
+ UI研究稍微深点，比如侧滑菜单这种要怎么实现？UIview，UIviewcontroller一堆方法，到底是干什么用的呀，是不是要好奇一下。
+ UIView再往深处看，下面还有CALayer，研究没？为什么修改CALayer的某些property属性会产生动画
+ 既然用了两年第三方类库，那么比如图片缓存这类，看过源码实现没？如果自己来实现的话，有哪些Caching Algorithms？该怎么取舍？各种常用的第三方类库你研究过原理没？
+ App在和服务器交流数据的过程中安全性
+ 视音频处理
