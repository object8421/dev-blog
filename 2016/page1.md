#UITableView问题总结点
#1. 有关UITableView的contentSize、contentInset和contentOffset

tabelview的contentsize是由它的下列方法共同实现的：
- (NSInteger)numberOfSections;
- (NSInteger)numberOfRowsInSection:(NSInteger)section;
- (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath;
- (CGFloat)tableView:(UITableView *)tableView heightForHeaderInSection:(NSInteger)section;
- (CGFloat)tableView:(UITableView *)tableView heightForFooterInSection:(NSInteger)section;
contentSize、contentInset和contentOffse图示如下：
![contentSize.png](http://img.blog.csdn.net/20130613195037125)
![contentInset.png](http://img.blog.csdn.net/20130613195127390)
![contentOffse.png](http://img.blog.csdn.net/20130613195740546)

