# javabean



>- 在java1996年发布,当年12月即发布了java bean1.00-A,有什么用呢?通过统一的规范可以设置对象的值(get,set方法),这是最初的java bean;
>
>- 在实际企业开发中,需要实现事务,安全,分布式,javabean就不好用了.sun公司就开始往上面堆功能,这里java bean就复杂为EJB;
>- EJB功能强大,但是太重了.此时出现DI(依赖注入),AOP(面向切面)技术,通过简单的java bean也能完成EJB的事情,这里的java bean简化为POJO;
>- Spring诞生了.



## 目标

- 了解javabean的概念
- 了解javabean的规范
- 掌握jsp访问javabean的语法
- 理解javabean的四种范围



## 概念

- JavaBean 是一种JAVA语言写成的可重用组件（以类的形式存在），包含属性（Properties），方法（Methods），事件（Event）等特性（组成元素）




## 作用（优点）

- 是的HTML与JAVA程序分离，这样便于维护代码
- JSP侧重生成动态网页，事务处理有JavaBean来完成，可以充分利用JavaBean组件的可重用性特点



## 特征

一个标准的JavaBean有以下几个特性

- 必须是具体的和公共的，并且具有无参数的构造器
- 通过提供符合一致性设计模式的公共方法将内部域暴露成员属性，set和get方法获取
  - JavaBean同时也是一种规范，需要创建setter，getter是因为，jsp在转换成Servlet时，会将获取、设置JavaBean中属性的动作转化成调用setter、getter方法
- 其他Java 类可以通过反射机制发现和操作这些JavaBean 的属性。



## 分类

JavaBean通常分成两类。一种是有用户界面的JavaBean，即可视化领域的JavaBean，如AWT下的使用；

另一种是没有用户界面的，主要负责处理事务（如数据运算，操作数据库）的JavaBean。JSP通常访问的是后一种JavaBean



## 组成

一个JavaBean由三部分组成

### 属性（Properties）

### 方法（Methods）

### 事件（Events）



## JSP访问JavaBean

### 1、导入JavaBean

```jsp
<%@page import="pacage.JavaBeanName" %>
```



### 2、创建JavaBean对象

创建对象使用<span style="color:red">`<jsp:useBean>`</span>  标签，需要完成的几个步骤，由标签的属性体现



```jsp
<!-- 这里的scope指的是生命周期，存活时间范围 -->
<jsp:useBean id="instanceName" class="pacage.JavaBeanName" scope="session"/>
```



#### id：对象引用

- 在所定义的范围（scope）中确认JavaBean的变量。使之能够在之后的程序中使用此变量名来分辨不同的Bean

#### class：JavaBean的包名和类名

#### scope：作用时间范围，同时也是对象引用的命名空间

- 该属性决定了JavaBean对象存在的范围，可选值：page（默认），request，session，application

jsp.class：

![image-20200407091806055](asd.assets/image-20200407091806055.png)



### 3、访问JavaBean属性

访问分为两种操作，一种情况是获取值，另一种情况是设置值\

分别使用<span style="color:red">`<jsp:getProperty>`</span>,<span style="color:red">`<jsp:setProperty>`</span>标签

#### 获取：

```jsp
<jsp:getProperty name="instanceName" property="propertyName"/>
```

#### 设置：

```jsp
<!-- via value -->
<jsp:setProperty name="instanceName" property="propertyName" value="valueToSet"/>
```



```jsp
<!-- via parameter -->
<jsp:setProperty name="instanceName" property="propertyName" param="requestParaName"/>
```



#### name：对象引用

- 这个name就是之前\<jsp:useBean>标签中设置的对象引用

#### property： 需要设置的对象名

- 用一个参数值来制定Bean中的一个属性值，一般情况下是从request对象中获得的，其中property指定Bean的属性名，param指定request中的参数名



#### value：需要设置的值

- 在设置的时候会转换成对应的Object，如果转换失败，那肯定就设置失败了。比如这里的count是int类型的，输入“10”肯定能够转换成int

#### parameter:从request的该参数中获取设置的值

- parameter可以获取请求中对应的参数（参数名为requestParaName），并将其赋值给property

<span style="color:red"> 注意，不能在同一个\<jsp:setProperty>标签中同时使用param和value参数</span>   



<img src="D:\DOCUMENT\自学笔记\圣思园javaweb\11-javabean.assets/image-20200407092134723.png" alt="image-20200407092134723" style="zoom: 200%;" />



### JSP创建Bean时，scope参数的相关区别

#### JavaBean在scope="page"范围内的使用

- 客户每次请求访问JSP页面时，都会创建一个JavaBean对昂，JavaBean对侠女的有效范围是客户请求访问的当前JSP网页。JavaBean对象在一下两种情况下都会结束其生命周期
  - 客户请求访问的当前JSP网页通过`\<jsp:forward>`或者RequesDispachter.forward()，将请求转发到另一个文件
  - 客户请求访问的当前JSP页面执行完毕变相客户端发回响应

#### JavaBean在scope="request"范围内的使用

- 客户每次请求访问JSP页面时都会创建新的JavaBean对象，其有效范围为：
  - 客户请求访问当前JSP网页
  - 和当前JSP网页共享一个客户请求的网页，即当前JSP网页中<%@ include %>以及\<jsp:forward>
  - 当所有共享同一客户端请求的JSp页面执行完毕并向客户端发回响应时，JavaBean对象结束生命周期
- JavaBean对象作为属性保存在HttpRequest对象中，属性名为JavaBean的`id`（对象引用），属性值为JavaBean对象，因此也可以通过`HttpRequest.getAttribute()`方法取得对象

#### JavaBean在scope="session"范围内的使用

- JavaBean对象被创建后，存在于整个SESSION的生命周期内，同一个Session中的JSP文件共享该JavaBean对象
- JavaBean对象作为属性保存在HttpSession对象中，属性名为JavaBean的`id`（对象引用），属性值为JavaBean对象。除了可以通过JavaBean的id直接引用JavaBean对象外，也可以通过`HttpSession.getAttribut()`方法取得该对象

#### JavaBean在scope="application"范围内的使用

- JavaBean对象被创建后，存在于整个Web应用是生命周期内，Web应用中的所有JSP文件都能够共享一个JavaBean对象
- JavaBean对象作为属性保存在HttpRequest对象中，属性名为JavaBean的`id`（对象引用），属性值为JavaBean对象，因此也可以通过`HttpRequest.getAttribute()`方法取得对象











