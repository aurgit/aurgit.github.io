---
title: HTML与CSS基础课程学习笔记
author: ezhq
top: false
cover: true
toc: true
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: cn
comments: true
date: 2017-10-18 22:02:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592660804/Img/BlogCover/blogTopImage_qh8ggl.png
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592660804/Img/BlogCover/blogTopImage_qh8ggl.png
password:
summary: 慕课网《HTML与CSS基础课程》学习笔记
categories:
- Dev
tags:
- Dev
- Frontend
- HTML
- CSS
keywords:
updated: 2017-10-18 22:02:00
---

# 备注
## 预备知识 
* 无 

## 学习预期结果 
* 学习HTML、CSS样式基础知识 
* 利用HTML、CSS样式技术制作出简单页面 


# HTML介绍 
## 代码初体验：制作我的第一个网页 

## HTML和CSS的关系 
* **HTML是网页内容的载体**。内容就是网页制作者放在页面上想要让用户浏览的信息，可以包含文字、图片、视频等。 
* **CSS样式就是表现**。就像网页的外衣。比如，标题字体、颜色变化，或为标题加入背景图片、边框等。所有这些用来改变内容外观的东西称之为表现。 
* **JavaScipt是用来实现网页上的特殊效果**。如：鼠标滑过弹出下拉菜单。或鼠标滑过表格的背景颜色改变。还有焦点新闻（新闻图片）的轮换。可以这么理解，有动画的，有交互的一般都是用JavaScript来实现的。 

## 认识HTML标签 
* **标题** `<h1>标题内容</h1>` 
* **段落** `<p>段落内容</p>` 
* **图片** `<img src="图片名字.图片格式">` 

## 标签语法 
* HTML标签不区分大小写，`<h1>`和`<H1>`作用一样 

## 认识HTML文件基本结构 
* `<html></html>`为根标签，所有的网页标签都在`<html></html>`中 
* `<head>`标签用于定义文档的头部，是所有头部元素的容器。 
* 头部元素有：`<tittle>`、`<script>`、`<style>`、`<link>`、`<meta>`等标签 
* `<body></body>`之间的内容是网页的主要内容，如`<h1>`` <p> ``<a>`` <img>`等网页内容标签，在这里的标签中的内容会在浏览器中显示出来 

## 认识head标签 
* `<head>`是文档的头部标签，描述了文档的各种属性和信息，大多数文档头部数据不会作为内容显示给读者 
* 可用在`<head>`部分的标签： 
    ```html
    <head>
        <title>...</title>
        <meta>
        <link>
        <style>...</style>
        <script>...</script>
    <head>
    ```
* `<title></title>`标签之间的文字内容是网页的标题信息，会出现在浏览器的标题栏中。 

## 了解HTML的代码注释 
* `<!--注释文字-->` 


# 认识标签_1 
## 语义化 
* 标签学习要点：标签用途，标签在浏览器中的默认样式 
* 语义化：明白每个标签的用途（即在什么情况下使用此标签合理） 
* 语义化的目的：1.更容易被搜索引擎收录 2.更容易让屏幕阅读器读出网页内容 

## body标签：网页内容 
* 网页上显示的内容要放在`<body></body>`标签中 

## p标签：段落 
* 一段文字一个`<p></p>`标签 
* `<p>`标签的默认样式为段前段后都会有空白行 

## hx标签：网页标题 
* `<hx></hx>`为标题标签，x取值为1-6，对应不同等级的标题，`<h1>`为最高等级标题 
* `<h1>`标签一般用在网站名称上 

## strong和em标签：强调语气 
* `<em></em>`表示一般程度强调，被强调内容斜体显示 
* `<strong></strong>`表示更加强烈的强调，被强调内容默认粗体显示 

## span标签：文字单独样式 
* `<span></span>`为内容单独设置特殊样式,具体样式在`<head>`标签内`<style>`标签内通过`span{}`单独设置 

## q标签：短文本引用 
* `<q></q>`用来引用别处非自己创作的语句，被引用语句无须手动添加双引号，默认被引用内容会被自动添加上双引号 

## blockquote标签：长文本引用 
* `<blockquote></blockquote>`标签用来对大段文字进行引用，对于被引用内容，显示时候会进行左右缩进处理 

## r标签：分行显示文本 
* `<br />`放在需要换行的文段末尾，相当于word文档的回车 
* xhtml1.0写法：`<br />` html4.01写法：`<br>` 
* `<br />`标签为空标签，即没有具体HTML内容，类似标签有`<br />`、`<hr />`和`<img />` 
* 在HTML代码中的回车、空格是被直接忽略的 

## &nbsp;网页中添加空格 
* `&nbsp;`代表文本中的一个空格 

## hr标签：添加水平横线 
* html4.01版本：`<hr>` 
* html1.0版本（一般使用）：`<hr />` 

## address标签：网页地址信息 
* `<address></address>`用来定义一个地址、签名或作者身份等需要在网页中展示出来用于联系的信息 
* 例子：`<address>作者：<a href="mailto:example@mail.com">example</a></address> 
* `<address>`标签内容显示样式默认为斜体 

## code标签：加入一行代码 
* `<code></code>`只用于插入一行较短的代码，多行代码用`<code></code>`标签 

## pre标签：加入大段代码 
* `<pre></pre>`标签作用：预格式化文本，在标签中的文本通常会保留空格和换行符，而不必再手动输入`<br>``&nbsp;`。此标签并不只是为显示计算机源码使用，需要在网页中预显示格式时都可以使用此标签 


# 认识标签_2 
## ul标签：无序列表 
* `<ul>...</ul>`标签用来排列无先后顺序的信息列表 
* 语法：
    ```html
    <ul>
        <li>信息</li>
        <li>信息</li>
        ......
    </ul>
    ```

## ol标签：有序列表 
* `<ol>...</ol>`标签一般用来进行有先后顺序需要的信息的显示,标签内文本自动标序号 
* 语法：
    ```html
    <ol>
        <li>信息1</li>
        <li>信息2</li>
        ......
    </ol>
    ```

## div标签：独立逻辑容器 
* `<div>...</div>`标签用于将相互独立的内容相互分隔开来，如网页中不同栏目 

## div id="..."标签命名 
* `<div id="">...</div>`标签用于给标签自定义名称，便于理解使用 
* 用法：
    ```html
    <div id="板块名称“>...</div> 
    ```

## table标签：表格 
* 表格标签关键元素：table、tbody、tr、th、td 
* `<table>...</table>`:整个标签的最外围 
* `<tbody>...</tbody>`:加上此标签后，此标签包含的内容在下载完后优先显示，而不用等到整个表格加载结束后再显示。若不加此标签，则整个表格加载完之后才会显示。用此标签分段，可以对表格分部分进行尽快显示 
* `<tr>...</tr>`:表格的行，有几对此标签，表格就有几行 
* `<td>...</td>`:表格的列，一行中包含几对此标签，该行就有几列 
* `<th>...</th>`:表格表头，表格头部的一个单元格 
* 表格中列的个数，取决于一行中数据单元格的个数。表头默认粗体居中显示 
* table表格在没有添加CSS样式之前，在浏览器中没有表格之间的分割线 
* 例子：
    ```html
    <table>
        <tr>
            <th>产品名称</th>
            <th>品牌</th>
            <th>库存量（个）</th>
            <th>入库时间</th>
        </tr>
        <tr>
            <td>耳机</td>
            <td>联想</td>
            <td>500</td>
            <td>2008-08-08</td>
        </tr>
        <tr>
            <td>U盘</td>
            <td>金士顿</td>
            <td>120</td>
            <td>2009-09-09</td>
        </tr>
    </table>
    ```

    ![3_5_table标签_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592661381/Img/BlogCover/3_5_table%E6%A0%87%E7%AD%BE_%E9%85%8D%E5%9B%BE_1_b4bfnn.png)

## 表格边框 
* 添加CSS代码，为上一小节表格添加边框 
* 添加的部分CSS代码(在head标签内)：
    ```html
        <head>
        ...
            <style type="text/css">
            table tr td,th{border:1px solid #000;}
            </style>
        ...
        </head>
    ```
     

* 代码与效果图 
    ```html
        <!DOCTYPE HTML>
        <html>
        <head>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title>为表格添加边框</title>
        <style type="text/css">
        table tr td,th{border:1px solid #000;}
        </style>
        </head>
        <body>
         <table>
                <tr>
                 <th>产品名称</th>
                 <th>品牌</th>
                 <th>库存量（个）</th>
                 <th>入库时间</th>
                </tr>
                <tr>
                    <td>耳机</td>
                    <td>联想</td>
                    <td>500</td>
                    <td>2008-08-08</td>
                </tr>
                <tr>
                    <td>U盘</td>
                    <td>金士顿</td>
                    <td>120</td>
                    <td>2009-09-09</td>
                </tr>
            </table>
        </body>
        </html>
    ```

    ![3_6_表格美化_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592661480/Img/BlogCover/3_6_%E8%A1%A8%E6%A0%BC%E7%BE%8E%E5%8C%96_%E9%85%8D%E5%9B%BE_1_kupbzm.png)

## caption标签：表格标题和摘要 
* 表格标题：用来描述表格内容，标题默认显示在表格上方 
* 表格标题用法：
    ```html
        <table>
            <caption>标题文本</caption>
            <tr>
                <td>...</td>
                <td>...</td>
                ...
            </tr>
        ...
        </table>
    ```

* 表格摘要：表格摘要的内容不会在浏览器视图中显示出来，它的作用是增加表格的可读性（语义化），使搜索引擎更好地理解表格内容，也可使屏幕阅读器更好地阅读表格内容 
* 表格摘要用法：
    ```html
    <table summary="表格摘要文本">
    ```


# 认识标签_3 

## a标签：链接 
* `<a>`标签用来实现超链接 
* 用法：
    ```html
    <a href="目标网址" title="鼠标划过显示的文本">链接显示文本</a>
    ```

* 带`<a>`标签的文字会自动默认为蓝色，可以用CSS自定义颜色 
* `<a>`标签的超链接默认在当前页面打开，若需要在新标签打开超链接，方法为：
    ```html
    <a href="目标地址" target="_blank" title="鼠标划过显示的文本">链接显示文本</a>
    ```

## mailto标签：邮件发送 
* `<a>`标签何以搭配`<mailto>`进行超链接发送邮件，也就是点击某个超链接后，自动打开发送邮件的应用，进行邮件填写与发送 
* 用法：
    ```html
    <a href="mailto:邮箱地址1;邮箱地址2?cc=抄送地址1;抄送地址2&bcc=密件抄送地址1;密件抄送地址2&subject=邮件主题&body=邮件内容">
    ```

* 参数解释 
    * *mailto*：邮箱地址。点击链接后，浏览器会自动调用浏览者系统默认的电子邮件客户端，并在收件人一栏自动填上该关键词设置的收件人的地址 
    * *cc*：抄送地址 
    * *bcc*：密件抄送地址 
    * *;*：分隔符。用于分隔多个邮箱地址，实现同时发送或抄送给多个人邮件 
    * *subject*：邮件主题 
    * *body*：邮件内容 

* 如果mailto后面同时有多个参数，则第一个参数必须以`?`开头，后续参数相互之间用`&`分隔开来 

## img标签：图片插入 
* `<img>`标签用于在网页插入图片 
* 用法：
    ```html
    <img src="图片地址" alt="图片显示失败时显示文本" title="提示文本">
    ```

* 参数说明 
    * *src*：图片的地址 
    * *alt*：图片的描述性文字，当图片显示失败，会在图片本应显示的地方显示此参数内的文字 
    * *title*：鼠标划过是显示的文字内容 
* 图片格式可以为GIF、PNG、JPEG 


# 与浏览者交互：表单标签 

## form标签：表单标签 
* `<form>`标签用来与访问者进行交互。该标签可以把访问者输入的数据传送到服务器端，使服务器端程序对传回的数据进行处理 
* 用法 
    ```html
    <form method="传送方式" action="服务器文件">
    ......
    </form>
    ```

* 参数解释 
    * *`<form>...</form>`*：表单标签。所有表单内容在此标签内实现 
    * *action*：表单数据被传输的目的地，可以是一个PHP页面（如save.php） 
    * *method*：表单数据传输方式（get/post），具体实现属于后端 
    * 所有表单控件，如文本框、文本域、按钮、单选框、复选框等，都必须放在`<form>`标签内，否则会使预期完整表单数据无法完整传输 

* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>表单标签</title>
    </head>
    <body>
    <form method="post" action="save.php">
         <label for="username">用户名:</label>
         <input type="text"  name="username" id="username" value="" />
         <label for="pass">密码:</label>
         <input type="password"  name="pass" id="pass" value="" />    
         <input type="submit" value="确定"  name="submit" />
         <input type="reset" value="重置" name="reset" />
    </form>  
    </body>
    </html>
    ```

    ![5_1_表单标签_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592661530/Img/BlogCover/5_1_%E8%A1%A8%E5%8D%95%E6%A0%87%E7%AD%BE_%E9%85%8D%E5%9B%BE_1_dzp6sp.png)

## input标签：文本输入框、密码输入框 
* *`<input>`*标签：用来进行文本输入或密码输入 
* 用法 
    ```html
    <form>
        <input type="输入类型选择" name="文本框名称" value="输入框默认值设定" />
    </form>
    ```

* 参数解释 
    * *type*：输入类型选择。选择值： 
        * *text*：文本输入，正常显示输入的字符 
        * *password*：密码输入，输入的字符会被黑色实心圆点代替 
    * *name*：文本框名称，用于后台识别用途 
    * *value*：文本框默认内容，用于提示 

* 例子 
    ```html
        <!DOCTYPE HTML>
        <html>
        <head>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
        <title>文本输入框、密码输入框</title>
        </head>
        <body>
        <form  method="post" action="save.php">
            账户: 
            <input type="text" name"myName" value="Name" />
            <br>
            密码: 
            <input type="password" name="pass" />
        </form> 
        </body>
        </html>
    ```

    ![5_2_表单标签_配图_2](https://res.cloudinary.com/imgcave/image/upload/v1592661549/Img/BlogCover/5_2_%E8%A1%A8%E5%8D%95%E6%A0%87%E7%AD%BE_%E9%85%8D%E5%9B%BE_2_j1zdcu.png)


## textarea标签：多行文本输入 
* *`<textarea>`*标签：用来进行大段的文字输入 
* 用法 
    ```html
    <textarea rows="行数" cols="列数">文本框文字</textarea>
    ```

* `rows`和`cols`这两个参数可以分别用CSS中的`width`和`height`代替 
* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>文本域</title>
    </head>
    <body>
    <form action="save.php" method="post" >
        <label>个人简介：</label>
        <textarea rows="10" cols="50">在此处输入具体内容...</textarea>
        <input type="submit" value="确定"  name="submit" />
        <input type="reset" value="重置"  name="reset" />
    </form> 
    </body>
    </html>
    ```

    ![5_3_textarea标签_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592661745/Img/BlogCover/5_3_textarea%E6%A0%87%E7%AD%BE_%E9%85%8D%E5%9B%BE_1_jqrlx9.png)


## radio/checkbox单选框与复选框 
* *radio*和*checkbox*用来进行单选和复选。单选框只能选一项，复选框可以多选或全选 
* 用法 
    ```html
    <input type="选择框类型" value="默认内容" name="名称" checked="checked" />
    ```

* *`checked`*参数为`checked`时，该选项默认处于被选中状态 
* 同一组的单选按钮，name取值要一致，以便起到同一组单选按钮进行单选的作用 
* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>单选框、复选框</title>
    </head>
    <body>
    <form action="save.php" method="post" >
        <label>性别:</label>
        <label>男</label>
        <input type="radio" value="1"  name="gender" />
        <label>女</label>
        <input type="radio" value="2"  name="gender" />
    </form>
    </body>
    </html>
    ```

    ![5_4_单选框与复选框_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592661777/Img/BlogCover/5_4_%E5%8D%95%E9%80%89%E6%A1%86%E4%B8%8E%E5%A4%8D%E9%80%89%E6%A1%86_%E9%85%8D%E5%9B%BE_1_lbiicj.png)

## select标签：下拉列表框 
* *`<select>`*标签用来作为下拉列表框，可以单选，也可以多选 
* 用法 
    ```
    <form name="列表框名称">
        <label>列表框标题</label>
        <select multiple="是否多选">
            <option value="选项1提交值">选项1显示值</option>
            <option value="选项2提交值">选项2显示值</option>
            <option value="选项3提交值">选项3显示值</option>
            <option value="选项4提交值" selected="默认是否被选择属性">选项4显示值</option>
        </select>
    </form>
    ```

* *`selected`*参数选择`selected`时，默认被选中 
* *`multiple`*参数选择`multiple`时，列表可进行多选，多选方法为按下`Ctrl`键同时`单击`需要多选的选项。不需要多选时候，可以直接不进行此参数配置 

* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>下拉列表框</title>
    </head>
    <body>
    <form action="save.php" method="post" >
        <label>爱好:</label>
        <select multiple="multiple">
        <option value="看书">看书</option>
        <option value="旅游" selected="selected">旅游</option>
        <option value="运动">运动</option>
        <option value="购物">购物</option>
        </select>
    </form>
    </body>
    </html>
    ```

    ![5_5_列表框_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592661806/Img/BlogCover/5_5_%E5%88%97%E8%A1%A8%E6%A1%86_%E9%85%8D%E5%9B%BE_1_axifcq.png)

## 提交按钮与重置按钮 
* `<input>`标签内`type`参数选择为`submit`，为提交按钮；若为`reset`，则为重置按钮 
* 用法：`<input type="submit/reset" value="按钮显示文字">` 
* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>重置按钮</title>
    </head>
    <body>
    <form action="save.php" method="post" >
        <label>爱好:</label>
        <select>
        <option value="看书">看书</option>
        <option value="旅游" selected="selected">旅游</option>
        <option value="运动">运动</option>
        <option value="购物">购物</option>
        </select>
        <input type="submit" value="确定"  />
        <input type="reset" value="重置"  />
    </form>
    </body>
    </html>
    ```

    ![5_6_提交按钮与重置按钮_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592661835/Img/BlogCover/5_6_%E6%8F%90%E4%BA%A4%E6%8C%89%E9%92%AE%E4%B8%8E%E9%87%8D%E7%BD%AE%E6%8C%89%E9%92%AE_%E9%85%8D%E5%9B%BE_1_tlofpz.png)

## label标签：鼠标选择 
* *`label`*标签不会向使用者呈现任何特殊效果，当在`label`标签内选中某条选项文本时，浏览器会自动选中和该label标签相关的表单选项上 
* 当启用`label`参数时候，在列表中，只要点到对应项的文字，就能选中该选项选框。未启用的话，点击选项的文字无效果，必须点击对应的选框才能选中对应选项 
* 用法：`<label for="控件id">` 
* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>form中的lable标签</title>
    </head>

    <body>

    <form>
    <p>你对什么运动感兴趣：</p>
    <label for="run">慢跑</label>
    <input type="checkbox" name="gender" id="run" />
    <br />
    <label for="mountain">爬山</label>
    <input type="checkbox" name="gender" id="mountain" />
    <br />
    <label for="basketball">篮球</label>
    <input type="checkbox" id="basketball">
    </form>

    </body>
    </html>
    ```

    ![5_7_label_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592662657/Img/BlogCover/5_7_label_%E9%85%8D%E5%9B%BE_1_kfwtre.png)


# 开始学习CSS：为网页添加样式 
## 认识CSS样式 
* *CSS*全称层叠样式表（Cascading Style Sheets），主要用于定义HTML内容的显示样式，如文字大小、颜色、字体加粗等内容 
* 使用CSS样式化的好处为可以通过定义某个样式，让不同网页位置的文字有着统一的字体、字号或颜色等 
* 用法 
    ```html
    <head>
    <style type="text/css">
    自定义标签名{
        color:green;
        具体样式内容；
        ......
    }
    </style>
    </head>
    <body>
        <p>
        <自定义标签名>...</自定义标签名>
        ......
    </body>
    ......
    ```

## 基本结构 
* CSS构成简要说明为`选择符{声明}`，具体为 
    ```css
    /*注释*/
    选择符{属性:值}
    ```

* *注释*：用`/*注释内容*/`表示，和html的注释`<!--注释内容-->`不同 
* *选择符*：又称为选择器，指明网页中应用样式规则的元素内容 
* *声明*：属性和值之间用英文冒号`:`隔开，多条声明之间用英文分号`;`隔开 
* 最后一条声明可以没有分号，可以将各个声明分行写，便于阅读 


# CSS样式基本知识 
## CSS样式插入方式 
* CSS样式代码插入方式：内联式、嵌入式、外部式 
* *内联式*：将CSS代码直接写在现有HTML标签中 
    * 例子：`<p style="color:red;font-size:12px">实例文段</p>` 
    * 注意：
        * 样式代码应写在元素的开始标签中，`style`的双引号内 
        * 有多条CSS样式代码，中间用英文分号`;`隔开 

* *嵌入式*： 将CSS样式代码写在`<style type="text/css"></style>`标签之间 
    * 例子： 
        ```css
        ......
        <style type="text/css">
        span{
            color:red;
        }
        </style>
        </head>
        ```

    * 注意： 
        * 嵌入式CSS样式必须写在`<style></style>`标签之间 
        * 一般情况下嵌入式CSS样式写在`<head></head>`标签内 

* *外部式*：外部式（也称为外联式）就是把CSS代码写在一个单独的外部文件中，这个CSS样式文件扩展名为`.css`，在`<head>`标签内使用`<link>`标签将CSS样式文件链接到HTML文件内 
    * 例子：`<link href="base.css" rel="stylesheet" type="text/css" />` 
    * 注意： 
        * CSS样式文件的名称尽量有意义，容易查找 
        * `rel="stylesheet" type="text/css"`是固定写法，无需修改 
        * `<link>`标签位置一般写在`<head>`标签内 
        * 外部的CSS样式文件内容直接写需要的样式内容，如`span{color:red;}` 

* 三种方式的优先级（相同权值下） 
    * `内联式 > 嵌入式 > 外部式` 
    * `嵌入式 > 外部式`的前提：嵌入式CSS样式在外部式的后面 
    * 总体概括：就近原则（距离被设置元素内容越近，样式优先级越高） 


# CSS选择器 
# 选择器、标签选择器 
* 选择器即CSS样式声明中的`{}`前的部分，选择器指明了`{}`中的样式作用的对象 
* 标签选择器即HTML代码中的各种标签 

# 类选择器、ID选择器 
* 类选择器用法：`.类选择器名称{CSS样式代码;}` 
    * 1.使用自定义的标签将想要修饰的内容包含进标签，如`<自定义标签>要修饰内容</自定义标签>` 
    * 2.使用`class="类选择器名称"`对标签设置一个类，如`<span class="类选择器名称"></span>` 
    * 3.设置类选择器的CSS样式具体内容，如`.类选择器名称{color:red;}` 

* ID选择器用法：ID选择器类似于嵌入式CSS样式和类选择器的结合,ID选择器以井号`#`开头，在整体头部标签内具体样式格式为`#ID名称{样式内容}`，在下方使用时候将类选择器中的`class`换为`id`即`<span id="ID名称">要修饰内容</span>` 

* 二者区别：
    * 二者都可以用于任何元素 
    * 类选择器在文档中可以使用（引用）多次，ID选择器只能使用（）引用一次 
    * 类选择器可以同时引用多个样式，如`<span class=类选择器名称1 类选择器名称2>`；而ID选择器只能引用一个样式 

* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>类选择器与ID选择器</title>
    <style type="text/css">
    .stress{
        color:red;
    }

    #setGreen{
        color:green;
    }
    </style>
    </head>
    <body><span id="setGreen">TEST</span>
        <h1>123</h1>
        <p>456<span class="stress">789</span>ABC</p>
        <p>DEF</p>
    </body>
    </html>
    ```

    ![8_2_类选择器_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592662689/Img/BlogCover/8_2_%E7%B1%BB%E9%80%89%E6%8B%A9%E5%99%A8_%E9%85%8D%E5%9B%BE_1_nbffuw.png)

## 子选择器 
* `>`子选择器用于指定标签元素的第一个子元素。如`.food>li{border:1px solid red;}`会使名为food下的子元素`li`(水果、蔬菜)加上红色实线边框 
* 简言之，就是类选择器多了对特定标签的样式化，仅对正文中引用区域中，被特定标签包含的文段进行样式化 
* 示例代码 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>子选择符</title>
    <style type="text/css">
    .food>li{border:1px solid red;}/*添加边框样式（粗细为1px， 颜色为红色的实线）*/
    .first>span{border:1px solid red;}
    </style>
    </head>
    <body>
    <p class="first">三年级时，<span>我还是一个<span>胆小如鼠</span>的小女孩</span>，上课从来不敢回答老师提出的问题，生怕回答错了老师会批评我。就一直没有这个勇气来回答老师提出的问题。学校举办的活动我也没勇气参加。</p>
    <h1>食物</h1>
    <ul class="food">
        <li>水果
            <ul>
                <li>香蕉</li>
                <li>苹果</li>
                <li>梨</li>
            </ul>
        </li>
        <li>蔬菜
            <ul>
                <li>白菜</li>
                <li>油菜</li>
                <li>卷心菜</li>
            </ul>
        </li>
    </ul>
    </body>
    </html>
    ```

    ![8_3_子选择器_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592662724/Img/BlogCover/8_3_%E5%AD%90%E9%80%89%E6%8B%A9%E5%99%A8_%E9%85%8D%E5%9B%BE_1_sncbzg.png)

## 包含（后代）选择器 
* 包含选择器是对于子选择器的进一步加强作用。子选择器对于指定标签的第一子层级起作用，而包含选择器对于无论是第几层，只要是子层级就会被起作用 
* 用法：`.first span{color:red}` 
* 注意 
    * 子选择器仅指它的直接后代（可理解为子元素的第一代后代）；后代选择器时作用于所有子后代元素 
    * 后代选择器通过`空格`来进行选择；子选择器通过`>`进行选择 
* 例子(子选择器) 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>后代选择器</title>
    <style type="text/css">
    .first span{color:red;}

    .food>li{
        border:1px solid red;
    }
    </style>
    </head>
    <body>
    <p class="first">123<span>456</span>789</p>

    <ul class="food">
        <li>ABC
            <ul>
                <li>DEF</li>
                <li>GHI</li>
                <li>JKL</li>
            </ul>
        </li>
        <li>MNO
            <ul>
                <li>PQR</li>
                <li>STU</li>
                <li>VWX</li>
            </ul>
        </li>
    </ul>

    </body>
    </html>
    ```

    ![8_4_包含选择器_配图_1.png](https://res.cloudinary.com/imgcave/image/upload/v1592662751/Img/BlogCover/8_4_%E5%8C%85%E5%90%AB%E9%80%89%E6%8B%A9%E5%99%A8_%E9%85%8D%E5%9B%BE_1_hdl2bx.png)

* 例子（包含选择器） 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>后代选择器</title>
    <style type="text/css">
    .first span{color:red;}

    .food li{
        border:1px solid red;
    }
    </style>
    </head>
    <body>
    <p class="first">123<span>456</span>789</p>

    <ul class="food">
        <li>ABC
            <ul>
                <li>DEF</li>
                <li>GHI</li>
                <li>JKL</li>
            </ul>
        </li>
        <li>MNO
            <ul>
                <li>PQR</li>
                <li>STU</li>
                <li>VWX</li>
            </ul>
        </li>
    </ul>

    </body>
    </html>
    ```

    ![8_4_包含选择器_配图_2](https://res.cloudinary.com/imgcave/image/upload/v1592662783/Img/BlogCover/8_4_%E5%8C%85%E5%90%AB%E9%80%89%E6%8B%A9%E5%99%A8_%E9%85%8D%E5%9B%BE_2_wrozjg.png)

## 通用选择器 
* `*`作用为用来匹配HTML中所有标签元素，即所有的标签元素都会默认应用`* ｛｝`中的样式，只需要在`style`标签中正常声明就行，在具体内容中无须引用 
* 用法：`* {color:red}` 

## 伪类选择符 
* 伪类选择符是用来给标签的某种状态设置（如鼠标滑过）样式，伪类选择符中在`a`标签上使用的`:hover`兼容性较好，即`a:hover{具体样式}......<a:hover></a>` 
* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>伪类选择符</title>
    <style type="text/css">
    a:hover{
        color:red;
        font-size:20px;
    }
    </style>
    </head>
    <body>
        <h1>TEST</h1>
        <p>123<a href="https:www.ezhq.xyz">aurdes</a>456</p>
        <p>789</p>
    </body>
    </html>
    ```

    ![8_6_伪类选择符_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592662808/Img/BlogCover/8_6_%E4%BC%AA%E7%B1%BB%E9%80%89%E6%8B%A9%E7%AC%A6_%E9%85%8D%E5%9B%BE_1_wehpiy.png)

## 分组选择符 
* 分组选择符为HTML多个标签设置同一个样式 
* 用法：`h1,span{具体样式}`，在内容中`h1``span`两个标签的样式会一样 
* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>分组选择符</title>
    <style type="text/css">
    .first,span{color:green;}
    #second{font-size:20px;}
    </style>
    </head>
    <body>
        <h1>TEST</h1>
        <p class="first">123<span>456</span>789</p>
        <p id="second">ABC<span>DEF</span>GHI</p>
    </body>
    </html>
    ```

    ![8_7_分组选择符_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592664279/Img/BlogCover/8_7_%E5%88%86%E7%BB%84%E9%80%89%E6%8B%A9%E7%AC%A6_%E9%85%8D%E5%9B%BE_1_eozee6.png)


# CSS的继承、层叠和特殊性 
## 继承 
* **继承**是指样式应用于某个特定标签后，此标签内的其他标签也会被应用此样式，即更次一级的子标签会被套用父层标签的样式 
* 例子1：下面代码会使`<p>`标签和`<span>`标签的内容都设置为红色 
    ```html
    p{color:red;}
    <p>ABC<span>DEF</span>GHI</p>
    ```

* 例子2：下面代码回事`<p>`标签加上红色1像素实心的边框，但`<p>`标签的子标签`<span>`并没有被应用此样式 
    ```html
    p{border:1px solid red;}
    <p>ABC<span>DEF</span>GHI</p>
    ```
    
* 有一些CSS样式不具有继承性，如：`border:1px solid red;` 

* 例子3： 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>继承</title>
    <style type="text/css">

    p{color:red;border:1px solid red;}
    </style>
    </head>
    <body>
        <h1>ezhq</h1>
        <p class="first">ABC<span>DEF</span>GHI</p>
        <p id="second">JKL<span>MNO</span>PQR</p>
    </body>
    </html>
    ```

    ![9_1_继承_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592664308/Img/BlogCover/9_1_%E7%BB%A7%E6%89%BF_%E9%85%8D%E5%9B%BE_1_hh1zus.png)

## 特殊性/权值 
* 当为同一个标签设定多种样式时候，元素启用哪一个样式，取决于样式的**权值** 
* 权值规则：
    * 标签权值为1，类选择符为10，ID选择符最高为100，继承的权值极低，可以近似为0 
    * `p{color:red;}`权值：1 
    * `p span{color:red;}`权值：1+1=2 
    * `.warning{color:red;}`权值：10 
    * `p span.warning{color:red}`权值：1+1+10=12 
    * `#footer .note p{color:red;}`权值：100+10+1=111 

* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>特殊性</title>
    <style type="text/css">
    p{color:red;}
    .first{color:green;}/*因为权值高显示为绿色*/

    span{color:pink;}/*设置为粉色*/
    p span{color:purple;}

    </style>
    </head>
    <body>
        <h1>ABC</h1>
        <p class="first">DEF<span>GHI</span>JKL</p>
        <p id="second">MNO</p>
    </body>
    </html>
    ```

    ![9_2_特殊性_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592664338/Img/BlogCover/9_2_%E7%89%B9%E6%AE%8A%E6%80%A7_%E9%85%8D%E5%9B%BE_1_enkacc.png)

## 层叠 
* 当权值相同的多个样式作用于同一个标签，会涉及到**层叠**的问题 
* 在HTML文件中对于同一个元素有多个CSS样式存在，当相同权重的样式存在时，根据这些CSS样式的前后顺序决定，处于最后面的CSS样式会被应用 
* CSS样式优先级：内联样式表（标签内部） > 嵌入样式表（）当前文件中 > 外部样式表（外部文件中） 
* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>层叠</title>
    <style type="text/css">
    p{color:red;}
    p{color:green;}
    p{color:pink;}
    </style>
    </head>
    <body>
        <h1>ABC</h1>
        <p class="first">DEF<span>GHI</span>JKL</p>
        <p id="second">MNO<span>PQR</span>STU</p>
        
    </body>
    </html>
    ```

    ![9_3_特殊性_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592664481/Img/BlogCover/9_3_%E7%89%B9%E6%AE%8A%E6%80%A7_%E9%85%8D%E5%9B%BE_1_j249pa.png)

## 重要性 
* `!important`用于在特殊情况下需要为某些样式设定最高权值 
* 例子 
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>!important</title>
    <style type="text/css">
    p{color:red!important;}
    p.first{color:green;}
    </style>
    </head>
    <body>
        <h1>ezhq</h1>
        <p class="first">ABC<span>DEF</span>GHI</p>
        <p id="second">JKL<span class="first">MNO</span>PQR</p>
        
    </body>
    </html>
    ```

    ![9_4_重要性_配图_1](https://res.cloudinary.com/imgcave/image/upload/v1592664509/Img/BlogCover/9_4_%E9%87%8D%E8%A6%81%E6%80%A7_%E9%85%8D%E5%9B%BE_1_ysxoi9.png)

* 注意：
    * `!important`要放在分号`;`的前面 
    * 当网页制作者不设置CSS样式时候，浏览器会按照自己的默认方式显示网页，并且访问者也可以自定义网页显示效果（如缩放字号等）。整个样式显示优先级为：浏览器默认样式 < 网页制作者定义的样式 < 访问者设置的浏览器显示样式 


# CSS格式化排版  


# CSS盒模型 


# CSS布局模型 


# CSS代码缩写：占用更少的带宽 


# 单位和值 


# CSS样式设置小技巧 
