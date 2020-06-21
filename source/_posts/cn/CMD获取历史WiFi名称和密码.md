---
title: CMD获取历史WiFi名称和密码
author: ezhq
top: false
cover: false
toc: false
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: cn
comments: true
date: 2017-08-04 10:06:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592717859/Img/BlogCover/WindowsTerminal_gafcjn.jpg
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592717859/Img/BlogCover/WindowsTerminal_gafcjn.jpg
password:
summary: 命令行获取历史 WiFi 名称和密码
categories:
- Life
tags:
- Life
- Terminal
keywords:
updated: 2017-08-04 10:06:00
---

1. 按下组合键 ` Win + R `   
2. 在打开的窗口中输入 ` cmd ` 并回车  
3. 将下列代码复制粘贴到打开的黑色背景的窗口中并回车即可  
```shell
    for /f "skip=9 tokens=1,2 delims=:" %i in ('netsh wlan show profiles') do  @echo %j | findstr -i -v echo | netsh wlan show profiles %j key=clear
```
