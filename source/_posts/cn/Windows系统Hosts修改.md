---
title: Windows系统Hosts修改
author: ezhq
top: false
cover: false
toc: true
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: cn
comments: true
date: 2016-11-11 17:30:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592717859/Img/BlogCover/WindowsTerminal_gafcjn.jpg
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592717859/Img/BlogCover/WindowsTerminal_gafcjn.jpg
password:
summary: 关于hosts
categories:
- Life
tags:
- Life
- OS
keywords:
updated: 2016-11-11 17:30:00
---

## 提示  
本教程不提供任何hosts文件，也不提供任何翻墙之类的软件或文件，相关文件自行网络搜索，使用之前请自行确保文件的安全性，本教程不对此方法的后果负责。  

## 前言  
只要一碰到无法正常浏览网络，正常使用Google、twitter、facebook等国外网站，搜索相关解决方法，都会在网上搜索到一种名为“修改系统hosts文件”的方法。到底如何操作，如何进行相关系统文件的更改？本文段即对此操作流程进行说明。废话不多所，开始教程。  

## 需要文件  
* 网络寻找好的hosts（自行google或百度相关站点搜索下载）。  

## 本地hosts文件复制  

### 本地文件准备  
将本地电脑的hosts文件复制到桌面，准备进行下一步的编辑。  
hosts文件位于本地电脑的位置：C:\Windows\System32\drivers\etc ，在这个etc文件夹内，有个没有后缀名的hosts文件，将它复制到桌面一份。不要急着将这个窗口关闭，后续要用到。  

### 下载文件的编辑  
将下载的hosts文件打开，打开方式选择记事本（右键——打开方式——记事本），在打开的记事本中，找到 # Modified hosts start 这一行，从此行#号前面开始到最后结尾处，选中这一部分进行复制（在#号前面点一下鼠标，拖动右侧滑块到最下方，然后按住键盘Shift按键不放，同时在最后一个字母处点击鼠标左键，即可选中这一部分，然后直接松开Shift，并随后同时按下Ctrl和C两个按键，即可完成复制）。  

### 本地文件的编辑  
将复制到桌面的hosts文件打开，打开方式选择记事本，在文档最后面另起一行（为了以后更改此处文件方便，可以另起一行后输入十来个#号，然后另起一行再输入十来个#号，最后再另起一行准备下一步操作。这些符号会被系统自动忽略，但是可以让自己以后便于寻找位置。）对上一步复制的文段进行粘贴（同时按下键盘Ctrl和V两个按键）然后直接对此文件进行保存（不要修改文件名，弹出文件重名的话，选择替换）。  

### 使修改后的本地文件生效  
第3步中已经将原先的hosts文件修改了。接下来，直接将修改后的hosts文件拖到第1步中的etc文件夹中，若有“替换或跳过文件”的提示，则选择“替换目标中的文件”，若有“你需要提供管理员权限才能移动到此文件夹”的提示，则选择继续即可。然后即可正常访问相关网站。  

### 扫尾工作  
第1步中的文件窗口可以关闭，网上下载的hosts文件可以直接删除了。更改hosts文件至此结束。  
