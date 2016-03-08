#Core Text 入门 

## 1.概述

Core Text是用来进行文字精细排版的，所以了解文字相关的知识也不可避免。

1.字符（Character）和字形（Glyphs）

排版系统中文本显示的一个重要的过程就是字符到字形的转换，字符是信息本身的元素，而字形是字符的图形表征，字符还会有其它表征比如发音。 字符在计算机中其实就是一个编码，某个字符集中的编码，比如Unicode字符集，就囊括了大都数存在的字符。 而字形则是图形，一般都存储在字体文件中，字形也有它的编码，也就是它在字体中的索引。 一个字符可以对应多个字形（不同的字体，或者同种字体的不同样式:粗体斜体等）；多个字符也可能对应一个字形，比如字符的连写（ Ligatures）


bounding box（边界框 bbox），这是一个假想的框子，它尽可能紧密的装入字形。
baseline（基线），一条假想的线,一行上的字形都以此线作为上下位置的参考，在这条线的左侧存在一个点叫做基线的原点，
ascent（上行高度）从原点到字体中最高（这里的高深都是以基线为参照线的）的字形的顶部的距离，ascent是一个正值
descent（下行高度）从原点到字体中最深的字形底部的距离，descent是一个负值（比如一个字体原点到最深的字形的底部的距离为2，那么descent就为-2）
linegap（行距），linegap也可以称作leading（其实准确点讲应该叫做External leading）,行高lineHeight则可以通过 ascent + |descent| + linegap 来计算。


 2.坐标系

 传统的Mac中的坐标系的原点在左下角，比如NSView默认的坐标系，原点就在左下角。但Mac中有些View为了其实现的便捷将原点变换到左上角，像NSTableView的坐标系坐标原点就在左上角。iOS UIKit的UIView的坐标系原点在左上角。 
往底层看，Core Graphics的context使用的坐标系的原点是在左下角。而在iOS中的底层界面绘制就是通过Core Graphics进行的，那么坐标系列是如何变换的呢？ 在UIView的drawRect方法中我们可以通过UIGraphicsGetCurrentContext()来获得当前的Graphics Context。drawRect方法在被调用前，这个Graphics Context被创建和配置好，你只管使用便是。如果你细心，通过CGContextGetCTM(CGContextRef c)可以看到其返回的值并不是CGAffineTransformIdentity，通过打印出来看到值为

```
Printing description of contextCTM:  
(CGAffineTransform) contextCTM = {  
a = 1  
b = 0  
c = 0  
d = -1  
tx = 0  
ty = 460  
}        

```

Core Text一开始便是定位于桌面的排版系统，使用了传统的原点在左下角的坐标系，所以它在绘制文本的时候都是参照左下角的原点进行绘制的。 但是iOS的UIView的drawRect方法的context被做了次flip，如果你啥也不做处理，直接在这个context上进行Core Text绘制，你会发现文字是镜像且上下颠倒。 

 这里再提及一个函数CGContextSetTextMatrix，它可以用来为每一个显示的字形单独设置变形矩阵。

3.NSMutableAttributedString 和 CFMutableAttributedStringRef

Core Foundation和Foundation中的有些数据类型只需要简单的强制类型转换就可以互换使用，这类类型我们叫他们为Toll-Free Bridged Types。 
CFMutableAttributedStringRef和NSMutableAttributedString就是其中的一对，Core Foundation的接口基本是C的接口，功能强大，但是使用起来没有Foundation中提供的Objc的接口简单好使，所以很多时候我们可以使用高层接口组织数据，然后将其传给低层函数接口使用。

## 




