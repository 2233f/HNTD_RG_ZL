问题一：导入模块后报出

`AttributeError: module 'bankApp.views' has no attribute 'log_in'`

![image-20230423102818285](C:\Users\dahun\AppData\Roaming\Typora\typora-user-images\image-20230423102818285.png)

解决办法：

这个问题翻译过来就是没有找到该视图函数。首先我们分析产生原因，视图函数、视图函数，讲的就是一个函数，现在我们导入了`app`中放有视图函数的目录，但是我们通过这个目录对编写函数的文件进行导入时出现问题，那就有可能是**在这个总的文件中对函数进行索引的路径出现了问题**，或者**我们可以更改我们的导入方式**。

法一：更改我们导入方式

![image-20230423104557128](C:\Users\dahun\AppData\Roaming\Typora\typora-user-images\image-20230423104557128.png)

成功启动

法二：针对路径索引的问题

![image-20230423105525538](C:\Users\dahun\AppData\Roaming\Typora\typora-user-images\image-20230423105525538.png)

采用`from django.urls impotr include`导入`app`自己目录下的`urls`文件，在其中编写视图函数和路由的对应关系。



问题二：

`The view bankApp.views.log_in.main didn't return an HttpResponse object. It returned None instead.`

![image-20230423110141310](C:\Users\dahun\AppData\Roaming\Typora\typora-user-images\image-20230423110141310.png)

分析：

翻译:返回的是一个None（可就是空，没有返回值）

主要原因：没有添加return

解决办法：

![image-20230423110326644](C:\Users\dahun\AppData\Roaming\Typora\typora-user-images\image-20230423110326644.png)