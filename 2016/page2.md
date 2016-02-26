#iOS开发笔试题

##笔试一、

###1：对数组中的元素去重复
**例如：**
```
   NSArray *array = @[@"12-11", @"12-11", @"12-11", @"12-12", @"12-13", @"12-14"];
```
**参考答案：**
```
NSMutableArray *resultArray = [[NSMutableArray alloc] initWithCapacity:array.count];
// 外层一个循环
for (NSString *item in array) {
   // 调用-containsObject:本质也是要循环去判断，因此本质上是双层遍历
   // 时间复杂度为O ( n^2 )而不是O (n)
    if (![resultArray containsObject:item]) {
      [resultArray addObject:item];
    }
}
NSLog(@"resultArray: %@", resultArray);
```

###2：说说以下元素的特性和作用
**例如：**
```
   NSArray、NSSet、NSDictionary与NSMutableArray、NSMutableSet、NSMutableDictionary
```
**参考答案：**
```
特性：

    NSArray表示不可变数组，是有序元素集，只能存储对象类型，可通过索引直接访问元素，而且元素类型可以不一样，但是不能进行增、删、改操作；NSMutableArray是可变数组，能进行增、删、改操作。通过索引查询值很快，但是插入、删除等效率很低。

    NSSet表示不可变集合，具有确定性、互异性、无序性的特点，只能访问而不能修改集合；NSMutableSet表示可变集合，可以对集合进行增、删、改操作。集合通过值查询很快，插入、删除操作极快。

    NSDictionary表示不可变字典，具有无序性的特点，每个key对应的值是唯一的，可通过key直接获取值；NSMutableDictionary表示可变字典，能对字典进行增、删、改操作。通过key查询值、插入、删除值都很快。

作用：

    数组用于处理一组有序的数据集，比如常用的列表的dataSource要求有序，可通过索引直接访问，效率高。

    集合要求具有确定性、互异性、无序性，在iOS开发中是比较少使用到的，笔者也不清楚如何说明其作用

    字典是键值对数据集，操作字典效率极高，时间复杂度为常量，但是值是无序的。在ios中，常见的JSON转字典，字典转模型就是其中一种应用。
```

###3：简单描述一下XIB与Storyboards，说一下他们的优缺点。
**参考答案：**
```
优点：

    XIB：在编译前就提供了可视化界面，可以直接拖控件，也可以直接给控件添加约束，更直观一些，而且类文件中就少了创建控件的代码，确实简化不少，通常每个XIB对应一个类。

    Storyboard：在编译前提供了可视化界面，可拖控件，可加约束，在开发时比较直观，而且一个storyboard可以有很多的界面，每个界面对应一个类文件，通过storybard，可以直观地看出整个App的结构。

缺点：

    XIB：需求变动时，需要修改XIB很大，有时候甚至需要重新添加约束，导致开发周期变长。XIB载入相比纯代码自然要慢一些。对于比较复杂逻辑控制不同状态下显示不同内容时，使用XIB是比较困难的。当多人团队或者多团队开发时，如果XIB文件被发动，极易导致冲突，而且解决冲突相对要困难很多。

    Storyboard：需求变动时，需要修改storyboard上对应的界面的约束，与XIB一样可能要重新添加约束，或者添加约束会造成大量的冲突，尤其是多团队开发。对于复杂逻辑控制不同显示内容时，比较困难。当多人团队或者多团队开发时，大家会同时修改一个storyboard，导致大量冲突，解决起来相当困难。
```

###4、请把字符串2015-04-10格式化日期转为NSDate类型
**参考答案：**
```
NSString *timeStr = @"2015-04-10";
NSDateFormatter *formatter = [[NSDateFormatter alloc] init];
formatter.dateFormat = @"yyyy-MM-dd";
formatter.timeZone = [NSTimeZone defaultTimeZone];
NSDate *date = [formatter dateFromString:timeStr];
// 2015-04-09 16:00:00 +0000
NSLog(@"%@", date);
```

###5、请简单描述一下队列和多线程的使用原理。
**参考答案：**
- 串行队列：队列中的任务只会顺序执行
```
dispatch_queue_t q = dispatch_queue_create("...", DISPATCH_QUEUE_SERIAL);
```
- 并行队列： 队列中的任务通常会并发执行
```
dispatch_queue_t q = dispatch_queue_create("......", DISPATCH_QUEUE_CONCURRENT);
```

- 全局队列：是系统的，直接拿过来（GET）用就可以；与并行队列类似
```
dispatch_queue_t q = dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0);
```

- 主队列：每一个应用程序对应唯一一个主队列，直接GET即可；在多线程开发中，使用主队列更新UI
```
dispatch_queue_t q = dispatch_get_main_queue();
```




