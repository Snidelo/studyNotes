# HTML

https://www.w3school.com.cn/tags/index.asp

## 简介

HTML(Hyper Text Makeup Language)即为超文本标记语言

是一种标记语言，侧重表现内容，展现和格式；差不多的还有一种XML语言，侧重于内容

文件后缀名一般是.htm .html



特点：

1. 由尖括号包围的关键词，比如 <html>
2. 通常是成对出现的，比如 <div>和 </div>
3. 标签对中的第一个标签是开始标签，第二个标签是结束标签；
4. 开始和结束标签也被称为开放标签和闭合标签。
5. 也有单独呈现的标签，如<img src="百度百科.jpg" />等。
6. ==一般成对出现的标签，其内容在两个标签中间；单独呈现的标签，则在标签属性中赋值。如<h1>标题</h1>和 <input type="text" value="按钮" />。==
7. 网页的内容需在<html>标签中，标题、字符格式、语言、兼容性、关键字、描述等信息显示在<head>标签中，而网页需展示的内容需嵌套在<body>标签中。



具体格式如下

```html
<!-- 
	HTML文件有固定的格式，最外层是HTML标记，其中分为两大部分，分别是HEAD和BODY	
-->
<html>
    <!-- head部分 -->
    <!-- 主要用于写一些脚本（引入一些外部写的脚本文件，比如CSS），或者规定一些内容，比如页面的标题-->
    <head>
        <title> this is the title</title>
    </head>
    
    <!-- body部分 -->
    <!-- 主要处理页面展现的部分 -->
    <body>
        <!-- body中可以直接加入文本 -->
        this is the body
        
        <!-- 加粗文本并增大字体，这里可以看到和XML的另一点区别就是有开始，可以没有结束标签 -->
        <h1>
            bold and bigger
        </h1>
        
        <h1>
            <font color="red">
	            bold and bigger            
            </font>
        </h1>
        
        <!-- 超链接可以用a来表示，后面加上超链接属性，和值 -->
        <a href="https://www.baidu.com">
        	this is a ref
        </a>
        
        <!-- 换行 -->
        <br>
        <br>
        
        <!-- 可以加上另外的一些属性，比如在新标签也中打开 -->
        <a href="https://www.bilibili.com"
		   target="_blank">
			open a hyper ref in new tag
		</a>
		
	
		<!-- 创建一个2行3列的表格 -->
		<!-- tr（tablerow）表示行，td表示列 -->
		<!-- 在表后增加属性和值，width表示占用外层容器的百分比；align表示对其，值可以为center
			 left，right等；border表示边框的宽度，值为整数 -->
		<table border="1" align="center" width="80%">
            <!-- 第一行 -->
			<tr>
                <!-- th（tablehead）也表示列，和td的区别在于它让表格中的值 居中 且 加粗-->
				<th>aa</th>
				<th>bb</th>
				<th>cc</th>
			</tr>
            <!-- 第二行 -->
			<tr>
                <!-- 用td也能够达到th的效果 -->
				<td align="center"><b>dd</b></td>
				<td>ee</td>
				<td>ff</td>
			</tr>
		</table>
	</body>
</html>
```



## 常见标签种类：

| <!--...-->   | 定义注释。                                         |
| ------------ | -------------------------------------------------- |
| <[!DOCTYPE]  | 定义文档类型。                                     |
| <a>          | 定义锚。                                           |
| <abbr>       | 定义缩写。                                         |
| <acronym>    | 定义只取首字母的缩写。                             |
| <address>    | 定义文档作者或拥有者的联系信息。                   |
| <applet>     | 不赞成使用。定义嵌入的 applet。                    |
| <area>       | 定义图像映射内部的区域。                           |
| <article>    | 定义文章。                                         |
| <aside>      | 定义页面内容之外的内容。                           |
| <audio>      | 定义声音内容。                                     |
| <b>          | 定义粗体字。                                       |
| <base>       | 定义页面中所有链接的默认地址或默认目标。           |
| <basefont>   | 不赞成使用。定义页面中文本的默认字体、颜色或尺寸。 |
| <bdi>        | 定义文本的文本方向，使其脱离其周围文本的方向设置。 |
| <bdo>        | 定义文字方向。                                     |
| <big>        | 定义大号文本。                                     |
| <blockquote> | 定义长的引用。                                     |
| <body>       | 定义文档的主体。                                   |
| <br>         | 定义简单的换行。                                   |
| <button>     | 定义按钮 (push button)。                           |
| <canvas>     | 定义图形。                                         |
| <caption>    | 定义表格标题。                                     |
| <center>     | 不赞成使用。定义居中文本。                         |
| <cite>       | 定义引用(citation)。                               |
| <code>       | 定义计算机代码文本。                               |
| <col>        | 定义表格中一个或多个列的属性值。                   |
| <colgroup>   | 定义表格中供格式化的列组。                         |
| <command>    | 定义命令按钮。                                     |
| <datalist>   | 定义下拉列表。                                     |
| <dd>         | 定义定义列表中项目的描述。                         |
| <del>        | 定义被删除文本。                                   |
| <details>    | 定义元素的细节。                                   |
| <dir>        | 不赞成使用。定义目录列表。                         |
| <div>        | 定义文档中的节。                                   |
| <dfn>        | 定义定义项目。                                     |
| <dialog>     | 定义对话框或窗口。                                 |
| <dl>         | 定义定义列表。                                     |
| <dt>         | 定义定义列表中的项目。                             |
| <em>         | 定义强调文本。                                     |
| <embed>      | 定义外部交互内容或插件。                           |
| <fieldset>   | 定义围绕表单中元素的边框。                         |
| <figcaption> | 定义 figure 元素的标题。                           |
| <figure>     | 定义媒介内容的分组，以及它们的标题。               |
| <font>       | 不赞成使用。定义文字的字体、尺寸和颜色。           |
| <footer>     | 定义 section 或 page 的页脚。                      |
| <form>       | 定义供用户输入的 HTML 表单。                       |
| <frame>      | 定义框架集的窗口或框架。                           |
| <frameset>   | 定义框架集。                                       |
| <h1> to <h6> | 定义 HTML 标题，可以改变标题的大小。               |
| <head>       | 定义关于文档的信息。                               |
| <header>     | 定义 section 或 page 的页眉。                      |
| <hr>         | 定义水平线。                                       |
| <html>       | 定义 HTML 文档。                                   |
| <i>          | 定义斜体字。                                       |
| <iframe>     | 定义内联框架。                                     |
| <img>        | 定义图像。                                         |
| <input>      | 定义输入控件。                                     |
| <ins>        | 定义被插入文本。                                   |
| <isindex>    | 不赞成使用。定义与文档相关的可搜索索引。           |
| <kbd>        | 定义键盘文本。                                     |
| <keygen>     | 定义生成密钥。                                     |
| <label>      | 定义 input 元素的标注。                            |
| <legend>     | 定义 fieldset 元素的标题。                         |
| <li>         | 定义列表的项目。                                   |
| <link>       | 定义文档与外部资源的关系。                         |
| <map>        | 定义图像映射。                                     |
| <mark>       | 定义有记号的文本。                                 |
| <menu>       | 定义菜单列表。                                     |
| <meta>       | 定义关于 HTML 文档的元信息。                       |
| <meter>      | 定义预定义范围内的度量。                           |
| <nav>        | 定义导航链接。                                     |
| <noframes>   | 定义针对不支持框架的用户的替代内容。               |
| <noscript>   | 定义针对不支持客户端脚本的用户的替代内容。         |
| <object>     | 定义内嵌对象。                                     |
| <ol>         | 定义有序列表。                                     |
| <optgroup>   | 定义选择列表中相关选项的组合。                     |
| <option>     | 定义选择列表中的选项。                             |
| <output>     | 定义输出的一些类型。                               |
| <p>          | 定义段落。                                         |
| <param>      | 定义对象的参数。                                   |
| <pre>        | 定义预格式文本。                                   |
| <progress>   | 定义任何类型的任务的进度。                         |
| <q>          | 定义短的引用。                                     |
| <rp>         | 定义若浏览器不支持 ruby 元素显示的内容。           |
| <rt>         | 定义 ruby 注释的解释。                             |
| <ruby>       | 定义 ruby 注释。                                   |
| <s>          | 定义加删除线的文本。                               |
| <samp>       | 定义计算机代码样本。                               |
| <script>     | 定义客户端脚本。                                   |
| <section>    | 定义 section。                                     |
| <select>     | 定义选择列表（下拉列表）。                         |
| <small>      | 定义小号文本。                                     |
| <source>     | 定义媒介源。                                       |
| <span>       | 定义文档中的节。                                   |
| <strike>     | 不赞成使用。定义加删除线文本。                     |
| <strong>     | 定义强调文本。                                     |
| <style>      | 定义文档的样式信息。                               |
| <sub>        | 定义下标文本。                                     |
| <summary>    | 为 <details> 元素定义可见的标题。                  |
| <sup>        | 定义上标文本。                                     |
| <table>      | 定义表格。                                         |
| <tbody>      | 定义表格中的主体内容。                             |
| <td>         | 定义表格中的单元。                                 |
| <textarea>   | 定义多行的文本输入控件。                           |
| <tfoot>      | 定义表格中的表注内容（脚注）。                     |
| <th>         | 定义表格中的表头单元格。                           |
| <thead>      | 定义表格中的表头内容。                             |
| <time>       | 定义日期/时间。                                    |
| <title>      | 定义文档的标题。                                   |
| <tr>         | 定义表格中的行。                                   |
| <track>      | 定义用在媒体播放器中的文本轨道。                   |
| <tt>         | 定义打字机文本。                                   |
| <u>          | 定义下划线文本。                                   |
| <ul>         | 定义无序列表。                                     |
| <var>        | 定义文本的变量部分。                               |
| <video>      | 定义视频。                                         |
| <wbr>        | 定义视频。                                         |
| <xmp>        | 定义预格式文本。                                   |

几个特殊的：`&nbsp;`表示空格 `<br>`表示换行`<hr>`表示一条横线



## 标签属性

这一部分主要还是参考首行的连接中的教程，其他的一些注意事项，每次遇到就补充.

```html
<tagName type="typeValue" name="nameValue" id="idValue">
```

### id VS. name

#### id

只能够被js所使用

```js
var index = document.getElementById("idValue");
var content = index.value;
```



#### name

可以被客户端（html中引入的.js）所使用，也可以被服务器端（Servlet）所使用

- ###### 服务器端

```java
//服务器端用 name 属性找到所有相同 name 标签的内容
String[] contents = request.getParameterValues("nameValue");

//服务器端用 name 属性找到对应的标签的内容
//相当于 request.getParameterValues("nameValue")[0]
String content = request.getParameter("nameValue");
```



- ###### 客户端（javascript）

```js
//客户端用 name 属性找到对应的标签
var content = document.getElementsByName("nameValue")[0];
//相当于 var index = document.getElementById("nameValue").value;
```





## 表单（form）

#### 介绍：

表单在[网页](https://baike.baidu.com/item/网页/99347)中主要负责[数据采集](https://baike.baidu.com/item/数据采集/219239)功能。一个表单有三个基本组成部分： 

​	表单标签：这里面包含了处理表单数据所用CGI程序的URL以及数据提交到服务器的方法。

​	[表单域](https://baike.baidu.com/item/表单域/3788809)：包含了[文本框](https://baike.baidu.com/item/文本框/7321309)、密码框、[隐藏域](https://baike.baidu.com/item/隐藏域/249616)、[多行文本框](https://baike.baidu.com/item/多行文本框/6388067)、[复选框](https://baike.baidu.com/item/复选框/7431800)、[单选框](https://baike.baidu.com/item/单选框/7431782)、下拉选择框和文件上传框等。 

​	表单按钮：包括提交按钮、复位按钮和一般按钮；用于将[数据传送](https://baike.baidu.com/item/数据传送/500685)到服务器上的CGI脚本或者取消输入，还可以用表单按钮来控制其他定义了处理脚本的处理工作。

#### 作用：

网页中登录等操作，会通过表单的形式将信息随着请求传给服务器端。是客户端和服务器端交互的最基本常见的一种方式。



关于表单（form）的HTML标签（控件）的一些介绍

整个表单部分需要被表单标签包括

```html
<form>
    <!-- content -->
    ...
</form>
```

其中可以包括以下几个控件：

#### input   

输入，用type区分，值可以为：

##### Text

文本输入 input不添加type属性时，默认为text

```html
<!-- 文本输入 -->
username:<input type="text">
<br>
password:<input type="text">
<br>
```



##### Radio

单选框，需要放到一个组里

- 需要放在一个组里，用name属性区分

```html
<!-- 单选框 -->
<!-- 需要放在一个组里面，才能够实现单选功能。通过name属性实现 -->
sex:female<input type="radio" name="gender"> male<input type="radio" name="gender"> <br>
```



##### Checkbox

复选框

```html
<!-- 复选框 -->
habit:study<input type="checkbox"> play<input type="checkbox"><br>
```



##### File 

文件上传

```html
<!-- 文件上传 -->
file uplode:<input type="file">
```



##### Submit 

提交，将表单（整个或部分）提交至服务器

```html
<!-- 表单内容提交 -->
<input type="submit" value="tijiaoanniu">
```

注意，提交默认提交当前页面，提交后页面会刷新，也可以指定提交的部分

##### Reset

重置，将页面恢复到最初的状态（而非清空）

```html
<!-- 重置当前页面 -->
<input type="reset" value="chongzhi">

<!-- 以下文本充值后会变成helloworld -->
username:<input type="text"，value="hello world“>
<br>
```

##### Button

普通按钮，通常会连接到javascript上处理

```html
<!-- 普通按钮 -->
<input type="button" value="normalbutton" onclick="javascript:alert('helloworld');">
```



#### Textarea

大的文本区域，用于接收大的文本输入

```html
<!-- 文本框 -->
comment:<textarea></textarea><br>
```



#### Select 

下拉菜单

- 需要配合option标签使用，一个option就是下拉菜单中的一个选

```html
<!-- 下拉表单 -->
education:<select>
    <option>primary-school</option>
    <option>university</option>
</select><br>
```

#### Hidden