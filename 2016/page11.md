### iOS之3D Touch开发
3D Touch的三大模块
3D Touch功能主要分为以下三个模块：

 Home Screen Quick Actions
> 通过主屏幕的应用Icon，我们可以用3D Touch呼出一个菜单，进行快速定位应用功能模块相关功能的开发。如上面的日历。

peek and pop
> 这个功能是一套全新的用户交互机制，在使用3D Touch时，ViewController中会有如下三个交互阶段： 
> （1）提示用户这里有3D Touch的交互，会使交互控件周围模糊
> (img)
> 
> （2）继续深按，会出现预览视图
> (img)
> （3）通过视图上的交互控件进行进一步交互
>  (img)

Force Properties
> iOS9为我们提供了一个新的交互参数:力度。我们可以检测某一交互的力度值，来做相应的交互处理。例如，我们可以通过力度来控制快进的快慢，音量增加的快慢等。

 实例来看是如何实现3D Touch功能
 


 




### iOS之3D Touch开发
3D Touch的三大模块
3D Touch功能主要分为以下三个模块：

 Home Screen Quick Actions
> 通过主屏幕的应用Icon，我们可以用3D Touch呼出一个菜单，进行快速定位应用功能模块相关功能的开发。如上面的日历。

peek and pop
> 这个功能是一套全新的用户交互机制，在使用3D Touch时，ViewController中会有如下三个交互阶段： 
> （1）提示用户这里有3D Touch的交互，会使交互控件周围模糊
> 
> （2）继续深按，会出现预览视图
> (img)
> （3）通过视图上的交互控件进行进一步交互

Force Properties
> iOS9为我们提供了一个新的交互参数:力度。我们可以检测某一交互的力度值，来做相应的交互处理。例如，我们可以通过力度来控制快进的快慢，音量增加的快慢等。

 实例来看是如何实现3D Touch功能
 


 



