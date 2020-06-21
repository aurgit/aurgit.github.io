---
title: Flask Web Dev
author: ezhq
top: false
cover: false
toc: true
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: cn
comments: true
date: 2018-06-16 22:05:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592669738/Img/BlogCover/FlaskWebDev_Cover_hlbuxq.png
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592669738/Img/BlogCover/FlaskWebDev_Cover_hlbuxq.png
password:
summary: 狗书阅读摘要备忘录
categories: 
- Read
tags:
- Dev
- Python
- Read
- Flask
keywords:
updated: 2018-06-17 22:05:00
---

# 第一章：安装  
## 1.1 安装Flask  
1. 全局安装（不推荐）  
    ```powershell
    pip install Flask
    ```
2. 虚拟环境安装  
    在想要安装虚拟环境的路径下执行系统powershell终端）。  
    ```powershell
    # 下方命令中“venv”为可自定义虚拟环境文件夹名称
    # 方案一：在当前系统环境所包含的第三方软件包基础之上创建混合环境
    virtualenv --system-site-packages venv
    # 方案二：新建全新不含第三方软件包的纯净环境
    virtualenv venv
    ```
3. 启动环境  
    执行虚拟环境安装路径中的“cativate”文件（powershell终端可执行“activate.ps1”文件）。  
    ```powershell
    ./venv/Scripts/activate.ps1
    ```
4. 启动Flask  
    * 项目文件设置：设置启动项目文件（当前项目主文件路径下执行下列命令）。  
        ```powershell
        # name.py为你指定的启动python文件
        $env:FLASK_APP = "name.py"
        ```
    * 项目文件设置：设置调试模式。  
        ```powershell
        $env:FLASK_DEBUG = "1"
        ```
    * 启动Flask。  
        ```powershell
        flask run
        ```

# 第二章：程序的基本结构  
```py
# Flask程序实例（初始化）
from flask import Flask
app = Flask(__name__)

# 路由函数
@app.route('/')

# 视图函数
def index():
    return '<h1>Welcome! Aurdes Member</h1>'

# 启动服务器
# 确保直接执行此脚本时才启动开发Web服务器
if __name__ == '__main__':
    app.run(debug=True)
```
## 2.1 基础程序例子  
### 2.1.1 程序实例(初始化)  
* 所有Flask程序都必须创建一个程序实例，程序实例是Flask类的对象。Web服务器使用 **WSGI**（**Web Server Gateway Interface** Web服务器网关接口）协议，将客户端发出的所有请求转交此对象进行处理。

### 2.1.2 路由函数  
* 处理URL和函数之间关系的程序成为 **路由**(**route**)  
* 程序实例保存了一个URL到Python函数的映射关系。  
* **修饰器** 是Python语言的标准特性，可以使用不同的方式修改函数的行为。通常使用修饰器将函数注册为时间的处理程序。  

### 2.1.3 视图函数  
* 像`index()`这样的函数成为**视图函数**（**view function**）,上方代码中将`index()`函数注册为根地址处理程序，访问域名后，服务器会执行`index()`函数，此函数返回值称为 **响应** ，响应可以为简单文本，也可以是复杂内容。  

### 2.1.4 启动服务器  
* 启动服务的`if`判断语句确保直接执行当前脚本文件时候才启动开发Web服务器。如果当前脚本由其他脚本引入，程序会认为引用该脚本的上级脚本（父脚本）会启动其他服务器，便不会启动当前脚本的服务器，即执行`app.run()`。  

### 2.1.5 访问测试网站  
* 设置好启动文件并通过`flask run`成功启动服务器后，可以在浏览器地址栏输入`http://127.0.0.1:5000/`来访问测试网站。  

## 2.2 请求处理  
### 2.2.1 上下文  
* Flask使用上下文让特定的变量在一个线程中全局可访问  
* **线程** 是可单独管理的最小指令集。**进程** 经常使用多个活动线程，有时还会共享内存或文件句柄等资源。多线程服务器会创建一个线程池，线程池中选择一个线程用于处理接收到的请求。
* Flask上下文全局变量：  

| 变量名 | 上下文 | 说明 |
| :- | :- | :- |
| current_app | 程序上下文 | 当前激活程序的程序实例 |
| g | 程序上下文 | 处理请求时用作临时存储的对象，每次请求都会重置此变量 |
| request | 请求上下文 | 请求对象，封装了客户端发出的HTTP请求内容 |
| session | 请求上下文 | 用户会话，用于存储请求之间需要“记住”的值的词典 |

### 2.2.2 推送与请求  
* **推送** :必须要先经过推送程序和请求上下文，才能分发请求，请求处理完再将其删除。相关信息被推送后，才能正常使用上下文全局变量。  
* **钩子函数**: 为了避免在每个视图函数中都使用重复代码，Flask提供了注册通用函数的功能，注册的函数可在请求被分发到视图函数之前或之后调用。Flask支持的4种钩子注册如下：
    * **before_first_requet**: 在处理第一个请求之前运行  
    * **before_request**: 在每次请求之前运行  
    * **after_request**: 如果没有未处理的异常抛出，在每次请求之后运行  
    * **teardown_request**: 即使有未处理的异常抛出，也在每次请求之后运行  
* 请求钩子函数和视图函数之间共享数据一般使用上下文全局变量`g`  

## 2.3 响应  
* **视图函数返回值** 响应: `响应文本,状态码,字典` 。**状态码** 用来表明不同相应状态。  
* **response** 响应 : `make_response()`函数可接受1、2或3个参数，并返回一个`response`对象。  
* **重定向** 响应: 没有页面文档，将响应引导到一个新的地址。重定向响应可使用3个值形式的返回值，也可在`response`对象中设置。Flask提供`redirect()`函数用于重定向响应，如`return redirect('http://www.ezhq.xyz')`  
* **abort** 响应: 此响应用于处理错误，`abort` 不会将控制权交还给调用它的函数，而是抛出异常把控制权交给Web服务器。如：`abort(404)`  

## 2.4 扩展  
### 2.4.1 基础扩展添加实例  
```python
from flask import Flask
from flask.ext.script import Manager
# new method
# from flask_script import Manager

app = Flask(__name__)
manager = Manager(app)

@app.route('/')
def index():
    return '<h1>Hello Veng~~</h1>'

if __name__ == '__main__':
    manager.run()
```
* **Flask-Script** 为一个Flask扩展，为Flask程序添加一命令行解析器。自带一组常用选项，且支持自定义命令。  
* `pip` 形式安装Flask-Script: 激活虚拟环境后执行以下命令进行安装：
    ```pyton
    python -m pip install flask-script
    ```
    有两点需要注意：  
    1. 在Windows下命令行中，虚拟环境下直接输入书中`pip...`命令不一定成功，可以使用命令`python -m pip...`代替。  
    2. 在国内网络环境下，电脑使用默认DNS有一定几率无法访问到需要下载的网络，可以通过更换电脑默认DNS来解决，DNS推荐（202.141.176.99）。  

# 第三章：模板  
## Jinja2  
* 默认情况下，Flask在程序文件夹中的templates子文件夹中寻找模板。  
* 在python文件中，使用`from flask import Flask, render_template`命令来实现把`Jinja2`模板引擎集成到程序中。
* `render_template`函数的第一个参数是模板的文件名。随后的参数是键值对（表示模板中变量对应的真实值），键值对`=`h号左侧表示参数名（模板中占位符），右侧为当前作用于中的变量（即同名参数的值）。
* Jinja2

# 附: 涉及到的扩展及其安装
* **Flask-Moment**   
  Flask程序扩展，能把 `moment.js`（可以在浏览器中渲染日期和时间） 集成到 `Jinja2` 模板中。  
  `pip install flask-moment` 

* **Flask-Bootstrap**  
  Flask 扩展，简化在程序中继承Bootstrap的过程。Bootstrap 是Twitter开发的一个开源框架，提供的用户界面组件可用于创建简洁有吸引力的网页，并兼容所有现代Web浏览器。  
  Bootstrap是客户端框架（不涉及服务器）.  
  `pip install flask-bootstrap` 

* **Flask-WTF**  
  Flask 扩展，将处理 Web 表单的过程简单化，对独立的 WTForm 包进行包装，方便集成到 Flask 中。  
  `pip install flask-wtf`  

* **Flask-SQLAlchemy**  
  Flask 扩展，简化在Flask程序中使用 SQLAlchemy 的操作。  
  `pip install flask-sqlalchemy`  

* **Flask-Migrate** 
  Flask 扩展，对 Alembic 做了轻量级包装并集成到 Flask-Script中，所有操作都通过Flask-Script命令完成。  
  Alembic 是SQLAlchemy的主力开发人员编写的一个数据库迁移框架，数据库迁移框架能够最终数据库**模式**的变化，然后增量式地把变化应用到数据库中。  
  `pip install flask-migrate`  

* **Flask-Mail**  
  Flask 扩展，连接到简单邮件传输协议（SMTP Simple Mail Transfer Protocol）服务器，并把邮件交给此服务器发哦是那个。若不进行配置，着会连接 localhost 上的25端口，无需验证即可发送电子邮件。  
  `pip install flask-mail`


# 附2：一些Python命令
* **pip 升级**：`python -m pip install --upgrade pip`  
* **自动生成项目需求文件**：`pip freeze >requirements.txt`  
