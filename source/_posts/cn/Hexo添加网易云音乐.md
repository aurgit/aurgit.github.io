---
title: Hexo添加网易云音乐
author: ezhq
top: false
cover: false
toc: true
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: en
comments: true
date: 2016-12-24 22:00:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592666216/Img/BlogCover/NeteaseMusic_qghpi9.png
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592666216/Img/BlogCover/NeteaseMusic_qghpi9.png
password:
summary: Hexo博客框架Next主题添加网易云音乐播放器
categories:
- Blog
tags: 
- Blog
keywords:
updated: 2016-12-24 22:00:00
---

## 一 简要介绍  
本方法适用于对Hexo框架网站添加网易云音乐播放器插件，本例在Hexo框架的Next主题下进行，将网易云音乐插件添加到侧边栏上。另外，浏览器广告拦截插件有一定几率造成插件不加载。  

## 二 选择音乐  
1. 在网易云音乐网页版上选择想要布置的音乐（这里以Family of the Year的《Hero》为例）；  
2. 在歌曲详细页上点击“生成外链播放器”；  
   ![1.Example](https://res.cloudinary.com/imgcave/image/upload/v1592666275/Img/BlogCover/aurdes_01_hwowlt.png)
3. 对插件进行个性化修改（建议为了网站浏览体验，，取消自动播放），并点击“复制代码”； 
   ![2.Example](https://res.cloudinary.com/imgcave/image/upload/v1592666315/Img/BlogCover/aurdes_02_jgm2t9.png)

## 三 修改网页样式文件  
1. 打开本地网页Hexo文件夹内的sidebar.swig文件，具体目录为：Hexo\themes\Next\layout\_macro\sidebar.swig（注：本路径中Next为自己的网页主题文件夹名，不同主题名称不同，路径都类似。）  
2. 在打开的sidebar.swig文件如图合适位置上粘贴上面复制的代码。
   ![3.Example](https://res.cloudinary.com/imgcave/image/upload/v1592666343/Img/BlogCover/aurdes_03_juffot.png)
3.在主目录下执行Git Bash命令,完成修改后文件上传：
```bash
hexo clean
hexo g
hexo d
```
## 四 最终效果  
![4.Example](https://res.cloudinary.com/imgcave/image/upload/v1592666374/Img/BlogCover/aurdes_04_dl0kco.png)
