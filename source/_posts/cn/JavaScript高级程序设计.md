---
title: JavaScript 高级程序设计
author: ezhq
top: false
cover: false
toc: true
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: cn
comments: true
date: 2020-02-10 12:00:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592747899/Img/BlogCover/JS_gliloe.png
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592747899/Img/BlogCover/JS_gliloe.png
password:
summary: 《JavaScript高级程序设计》
categories:
- Read
tags:
- Read
- Frontend
- JavaScript
keywords:
updated: 2020-02-10 12:00:00
---

# 1. JavaScript 简介

## 1.1 JavaScript 简史
### 1.1.1 完整 JavaScript 实现
* **ECMAScript**：核心。
* **DOM**：Docoment Object Model 文档对象模型。
  * 针对 XML 但经过扩展用于 HTML 的应用程序编程接口（API: Application Programming Interface）
* **BOM**：Browser Object Model 浏览器对象模型。

### 1.1.2 ECMAScript 实现可能的宿主环境
* **Web 浏览器**
* **Node**
* **Adobe Flash**
* ...

## 1.2 JavaScript 实现

## 1.3 JavaScript 版本


# 2. 在 HTML 中使用 JavaScript
## 2.1 `<script>` 元素
### 2.1.1 属性
* **`type`**：必选
  * `text/javascript`
  * `text/ecmascript`
  * `application/javascript`
  * `application/ecmascript`
* **`src`**：可选
* **`charset`**：可选
* **`defer`**：可选，延迟脚本
  * 只适用于外部脚本文件
  * 脚本在执行时不会影响页面的构造
  * 脚本将立即下载，但被延迟到整个页面都解析完毕后运行
  * HTML5 规范要求脚本按照出现但先后顺序执行，故延迟脚本会先于 `DOMContentLoaded` 事件按照顺序执行
  * 最好只包含一个延迟脚本: 现实中延迟脚本不一定按照先后顺序执行，也不一定会在 `DOMContentLoaded` 事件出发前执行
* **`async`**：可选，异步脚本
  * 只适用于外部脚本文件，并告诉浏览器立即下载文件
  * 不保证按照指定的先后顺序执行
  * 指定 `async` 属性的目的是不让页面等待两个脚本下载和执行
  * 异步脚本不要在加载期间修改 DOM
  * 异步脚本一定会在页面的 `load` 事件前执行，但可能会在 `DOMContentLoaded` 事件之前或之后执行
* ~~**`language`**：废弃~~

### 2.1.2 使用方式
* 直接在页面中嵌入 JavaScript 代码
  * 必须指定 `type` 属性
  * 代码中不能出现 `</script>`
    * 通过转义字符解决：`<\/script>`
* 包含外部 JavaScript 文件
  * 必须指定 `src` 属性
  * 下载及解析外部 JavaScript 时，页面的处理会暂时停止
  * XHTML 文档中使用，可以将 `</script>` 省略为 `/>` 。HTML 文档中不能使用，不符合 HTML 规范，有时会得不到 IE 正确解析
  * 带有 `src` 属性的 `<script>` 元素中，只会下载并执行外部脚本文件，起始标签之间嵌入的代码会被忽略

### 2.1.3 引入位置
* **放在`<script>`元素中**
  * 必须等到全部 JavaScript 代码都被下载、解析和执行完成之后，才开始呈现页面内容。导致页面延迟、空白
* **放在`<body>`元素中页面内容的后面**
  * 解析包含的 JavaScript 代码之前，页面内容就先展示出来

## 2.2 嵌入代码与外部文件
* 嵌入代码与外部文件的有点
  * 可维护性
  * 可缓存
  * 适应未来

## 2.3 文档模式

## 2.4 `<noscript>` 元素


# 3. 基本概念
## 3.1 语法
* 区分大小写: ECMAScript 中的一切（变量、函数名、操作符）都区分大小写
  
* 标识符规则
  * 字母、数字、下划线`_`、美元符号`$`
  * 第一个字符必须是字母、下划线或美元符号
  * 字母可以包含扩展的 ASCII 或 Unicode 字母字符
  * 采用驼峰大小写格式
  * 不能用关键字、保留字、true、false 和 null 用作标识符

* 注释
  * 单行注释: 
    ```js
    // 注释内容
    ```

  * 块级注释:（第一行和最后一行的星号不是必须的）
    ```js
    /*
     * 注释内容
     * 注释内容
     * /
    ```

* 严格模式
  * 在顶部添加代码 `"use strict";`
  * 严格模式下，ECMAScript 3 中的一些不确定行为将得到处理，某些不安全的操作也会抛出错误

* 语句
  * ECMAScript 中的语句以分号 `;` 结尾
  * 如果省略分号，则由解析器确定语句的结尾
  * 

## 3.2 关键字和保留字
### 3.2.1 ECMA-262 关键字（debugger 为第五版新增关键字）
* break
* case
* catch
* continue
* debugger
* default
* delete
* do
* else
* finally
* for
* function
* if
* in
* instanceof
* new
* return
* switch
* this
* throw
* try
* typeof
* var
* void
* while
* with

### 3.2.2 ECMA-262 保留字(第三版)
* abstract
* boolean
* byte
* char
* class
* const
* debugger
* double
* enum
* export
* extends
* final
* float
* goto
* implements
* import
* int
* interface
* long
* native
* package
* private
* protected
* public
* short
* static
* super
* synchronized
* throws
* transient
* volatile

### 3.2.3 ECMA-262 非严格模式保留字(第五版)
* class
* const
* enum
* export
* extends
* import
* super

### 3.2.4ECMA-262 严格模式追加保留字(第五版)
* implements
* interface
* **let**
* package
* private
* protected
* public
* static
* **yield**

## 3.3 变量
* ECMAScript 的变量是 **松散类型** 
* 松散类型即可以用来保存任何类型的数据，每个变量仅是一个用于保存值的占位符
* 未初始化的变量值为 `undefined`
* 用 var 操作符定义的变量将成为定义该变量的作用域中的局部变量。 也就是说, 如果在函数中使用 var 定义一个变量,那么这个变量在函数退出后就会被销毁
* 一次性定义多个变量: 将每个变量（初始化与否都行）用逗号分隔开，换行和缩进非必须操作
  ```js
  var strA = 'Alice',
      booA = true,
      numA = 365
  ```

## 3.4 数据类型
### 3.4.1 分类
#### 基本类型
* **`Undefined`**
* **`Null`**
* **`Boolean`**
* **`Number`**
* **`String`**
* **`Symbol`**

#### 复杂数据类型
* **`Object`**
  * **`Array`**
  * **`Date`**
  * **`RegExp`**
  * **`Function`**

### 3.4.2 判断数据类型: `typeof`
* 返回值
  * `undefined`: 值未定义
  * `boolean`: 值为布尔值
  * `string`: 值为字符串
  * `number`: 值为数值
  * `object`: 值为对象或 `null`
  * `function`: 值为函数
* `typeof` 是操作符而非函数，故括号非必需

### 3.4.3 类型详细内容
#### `undefined`
* 变量被定义声明但未被初始化时，值为 `undefined`
* 值为 `underfined` 不等同于 未定义变量

#### `Null`
* `null` 表示一个空**对象**指针，故 `typeof` 检测 `null` 会返回 `object`
* 如果定义的变量准备在将来用于保存对象,那么最好将该变量初始化为 null 而不是其他值。这样一来,只要直接检查 null 值就可以知道相应的变量是否已经保存了一个对象的引用
* undefined 派生自 null , 故两者的相等性测试要返回 true

#### `Boolean`
* `true`, `false` 与数字值不是同一类型,故 true 不一定等于 1, 而 false 也不一定等于 0
* `true` `false` 区分大小写
* ECMAScript 中所有的类型的值都有与 Boolean 对应的值
* 要将一个值转换为对应的 Boolean 值,可以调用转型函数 `Boolean()`
* 转换规则
  | 数据类型 | 转换为 true 的值 | 转换为 false 的值 | 
  | -------- | -------- | -------- | 
  | Boolean | true | flase |
  | String | 任何非空字符串 | "(空字符串)" |
  | Number | 任何非零数值(包括无穷大) | 0, NaN |
  | Object | 任何对象 | null |
  | Undefined | n/a(N/A) | undefined |

#### `Number`
* Number 类型使用 [IEEE754](https://zh.wikipedia.org/wiki/IEEE_754) 格式来表示整数和浮点数值
* 各种数值类型字面量格式
  * 十进制整数
  * 八进制
    * 第一位是 `0`, 其后为数字序列(0 ~ 7)
    * 如果字面值中的数值超出了范围, 则前导零(`0`)将被忽略,后面的数值当作十进制解析
    * 八进制在严格模式下无效,会导致 JavaScript 引擎抛出错误
  * 十六进制
    * `0x` 开头
    * `0 ~ 9` 及 `A ~ F` 表示, `A ~ F` 大小写均可
* 在进行算术计算时候, 所有以八进制和十六进制保湿的数值最终都被转换成十进制数值

##### 浮点数值
* **永远不要测试某个特定的浮点数值**
* 数值必须包含一个小数点,小数点后面必须至少有一位数字
* 小数点前面可以没有整数,但不推荐该写法
* 浮点数值的最高精度是 17 位小数,**但是在进行算数运算时精确度远不如整数**
* ECMAScript 会将下列浮点数自动转换为整数值存储
  * 小数点后没有任何数字(`1.`)
  * 浮点数值本身表示的为整数(`1.0`)
* 极大或极小数值可以用 e 表示法(科学技术法)表示的浮点数值表示
  * ECMAScript 中 e 表示法的格式也是如此,即前面是一个数值(可以是整数也可以是浮点数) ,中间是一个大写或小写的字母 E,后面是 10 的幂中的指数, 该幂值将用来与前面的数相乘
* 默认情况下,ECMAScript 会将哪些小数点后面带有6个零以上的浮点数值转换为以 e 表示法表示的数值

##### 数值范围
* 最小数值: `Number.MIN_VALUE`, 绝大多数浏览器中该值为 `5e-324`
* 最大数值: `Number.MAX_VALUE`, 绝大多数浏览器中该值为 `1.7976931348623157e+308`
* 如果某个值超出 JavaScript 数值范围, 则该数值会被自动转换成特殊的 `Infinity` 值
  * 超出范围的正值被转化为 `Infinity`
  * 超出范围的负值被转化为 `-Infinity`
  * 如果某次计算返回了正或负的 Infinity 值,那么该值将无法继续参与下一次的计算, 因为 Infinity 不是能够参与计算的数值
  * 可以使用 `isFinite()` 函数来判断数值范围是否超标。这个函数在参数位于最小与最大数值之间时会返回 true

##### `NaN`
* `NaN` 非数值(Not a Number) 是特殊数值, 用于表示一个本来应该要返回数值的操作数未返回数值的情况(这样避免了抛出错误)
* ECMAScript 中, 任何数值除以非数值会返回 NaN,因此不会影响其他代码的执行
* 任何涉及 `NaN` 的操作都会返回 `NaN`
* `NaN` 与任何值都不相等, 包括 `NaN` 本身
* 可以使用 `isNaN()` 函数来确定传入参数是否为 `NaN`
  * 不是数值的参数会被尝试转换为数值
  * 任何能被转换为数值的参数都会导致返回 `false`
  * 任何不能被转换为数值的参数都会导致返回 `true`
  * isNaN()确实也适用于对象。 在基于对象调用 isNaN() 函数时,会首先调用对象的 [valueOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/valueOf) 方法,然后确定该方法返回的值是否可以转换为数值。如果不能,则基于这个返回值再调用 toString()方法,再测试返回值。
而这个过程也是 ECMAScript 中内置函数和操作符的一般执行流程

##### 数值转换
* 把非数值转换为数值
  * `Number()`
    * 可以用于任何类型
      * 转换规则
        * Boolean: true 和 false 将分别被转换为 1 和 0
        * 数值型: 简单的传入和返回
        * null: 返回 0
        * undefined: 返回 NaN
        * 字符串:
          * 字符串中只包含数字 (包括前面带正号或负号的情况): 将其转换为十进制数值, 即"1" 会变成 1,"123"会变成 123,而"011"会变成 11(注意:**前导的零被忽略了**)
          * 字符串中包含有效的浮点格式(如"1.1"): 将其转换为对应的浮点数值(同样,也会忽略前导零)
          * 字符串中包含有效的十六进制格式(如"0xf"): 将其转换为相同大小的十进制整数值
          * 字符串是空的(不包含任何字符): 将其转换为 0
          * 字符串中包含除上述格式之外的字符: 将其转换为 NaN
  * `ParseInt()`
    * 用于把字符串转换为数值
  * `parseFloat()`
    * 用于把字符串转换为数值


## 3.5 操作符

## 3.6 语句

## 3.7 函数


# 4. **变量、作用域和内存问题**
## 4.1 基本类型和引用类型的值

## 4.2 执行环境及作用域

## 4.3 垃圾搜集


# 5. **引用类型**
## 5.1 Object 类型

## 5.2 Array 类型

## 5.3 Date 类型

## 5.4 RegExp 类型

## 5.5 Function 类型

## 5.6 基本包装类型

## 5.7 单体内置对象


# 6. **面向对象的程序设计**
## 6.1 理解对象

## 6.2 创建对象

## 6.3 继承


# 7. **函数表达式**
## 7.1 递归

## 7.2 闭包

## 7.3 模仿块级作用域

## 7.4 私有变量


# 8. BOM
## 8.1 window 对象

## 8.2 location 对象

## 8.3 navigator 对象

## 8.4 screen 对象

## 8.5 history 对象


# 9. 客户端检测
## 9.1 能力检测

## 9.2 怪癖检测

## 9.3 用户代理检测


# 10. DOM
## 10.1 节点层次

## 10.2 DOM 操作技术


# 11. DOM 扩展
## 11.1 选择符 API

## 11.2 元素遍历

## 11.3 HTML 5

## 11.4 专有扩展


# 12. DOM2 和 DOM3
## 12.1 DOM 变化

## 12.2 样式

## 12.3 遍历

## 12.4 范围


# 13. 事件
## 13.1 事件流

## 13.2 事件处理程序

## 13.3 事件对象

## 13.4 事件类型

## 13.5 内存和性能

## 13.6 模拟事件


# 14. 表单脚本
## 14.1 表单的基础知识

## 14.2 文本框脚本

## 14.3 选择框脚本

## 14.4 表单序列化

## 14.5 富文本编辑


# 15. 使用 Canvas 绘图
## 15.1 基本用法

## 15.2 2D 上下文

## 15.3 WebGL


# 16. HTML5 脚本编程
## 16.1 跨文档消息传递

## 16.2 原生拖放

## 16.3 媒体元素

## 16.4 历史状态管理


# 17. 错误处理与调试
## 17.1 浏览器报告的错误

## 17.2 错误处理

## 17.3 调试技术

## 17.4 常见的 IE 错误


# 18. JavaScript 与 XML
## 18.1 浏览器对 XML DOM 对支持

## 18.2 浏览器对 XPath 的支持

## 18.3 浏览器对 XSLT 的支持


# 19. E4X
## 19.1 E4X 的类型

## 19.2 一般用法

## 19.3 其他变化

## 19.4 全面启用 E4X

# 20. JSON
## 20.1 语法

## 20.2 解析与序列化


# 21. Ajax 与 Comet
## 21.1 XMLHttpRequest 对象

## 21.2 XMLHttpRequest 2级

## 21.3 进度事件

## 21.4 跨域源资源共享

## 21.5 其它跨域技术

## 21.6 安全

# 22. 高级技巧
## 22.1 高级函数

## 22.2 防篡改对象

## 22.3 高级定时器

## 22.4 自定义事件

## 22.5 拖放


# 23. 离线应用与客户端存储
## 23.1 离线检测

## 23.2 应用缓存

## 23.3 数据存储


# 24. 最佳实践
## 24.1 可维护性

## 24.2 性能

## 24.3 部署


# 25. 新兴的 API
## 25.1 requestAnimationFrame()

## 25.2 Page Visibility API

## 25.3 Geolocation API

## 25.4 File API

## 25.5 Web 计时

## 25.6 Web Workers
