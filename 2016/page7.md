# 阿里巴巴内推面试

2016.3.22，比较心塞的一天，内推挂了

---

面试官早上电话没接到，下午又打过来了，总的来说问的问题并不是很难。可能是自己功底的确不够扎实，很多问题，自己答的非常浅显，最后还是挂了。相关问题，总结如下。

---

1.下oc是如何就行内存管理的？

> * 在oc中采用arc机制，让编译器来进行内存管理。在下一代Apple LLVM编译器中设置ARC为有效状态，就无需再次键入retail和release代码，这在降低程序崩溃、内存等风险的同时，很大程度上减少了程序的开发量。oc内存管理也就是引用计数器。
 * 自己生成的对象，自己持有。
 * 非自己生成的对象，自己也能持有。
 * 不再需要自己持有的对象时释放。
 * 非自己持有的对象无法释放。
> * 对象属性，所有权的修饰符。
 * __strong 修饰符。
 * __weak 修饰符。
> * 自动释放池

2.在不用SDWebImage情况下，自己如何考虑图片缓存？
>ios所有网络请求都是异步的，用NSOperation开异步线程下载图片，当下载完成时替换占位图片，做了内存缓存，然后再进行本地缓存本地缓存。[参考][1]

3.实现多线程有哪几种方式？有何异同？
>NSThread
Cocoa NSOperation
[GCD][2]（Grand Central Dispatch）

4.有无多继承？
>代理和协议实现

5.monary约束(分类)?
>问了点语法，和分类自己意会错了。

6.分类
7.项目相关
8.strong weak 强弱引用block中
9.圆角问题
10.为什么要这样做，偶遇什么好处
11.banner

# 腾讯面试
2016.3.24，卧槽被阿里虐之后腾讯电话面试来了
1.runloop
2.runtime
3.多线程没问
4.解析html。。。。。项目相关
6.如何优化uitableview性能
7.非说自己懂圆角优化
8.经历这几个项目有什么感悟
9.http://www.cocoachina.com/ios/20150602/11968.html


  [1]: http://blog.csdn.net/xn4545945/article/details/37535681
  [2]: https://github.com/zhaoxiaobao/fuck-yesterday-flirt-tomorrow/blob/master/2016/page2.md
