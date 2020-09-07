## WEB-INF文件夹

在第一个WebApp时，做了很多配置等准备工作，见过了许多之前没有见过的文件目录，首先就是WebApp下的"WEB-INF"目录。这是规定的名字，不能改变，里面保存的是网站的前端代码和前端资源。文件夹中有一个web.xml（deployment description）即部署描述符，主要作用是将servlet描述符映射到具体的文件



## target文件夹

target文件夹中有classes文件夹和generated-sources，前者就是存放编译出来的字节码文件，也是Tomcat运行WebApp的目标文件夹



## server.xml文件

在之前的创建过程中，在Tomcat安装目录下的\conf下的server.xml进行了设置，添加了如下一条内容

```xml
<Context docBase="D:\DOCUMENT\IdeaProject\servlettest\out\artifacts\servlettest_war_exploded" path="/servlettest_war_exploded"/>
```

其实，客户端对资源的访问主要是访问的服务器，通过服务器找到相应的资源，所以服务器需要在客户端访问前，就知道（做好准备）资源在哪。

- path：上下文（是URI的一部分，前面写错了）
- docBase：文件在硬盘的位置

实际上，path是一个逻辑路径，docBase是物理路径

就像JAVA_HOME = D:/SOFTWARE/jdk一样，前者是逻辑路径，后者是物理路径