---
title: macOS 前端开发环境构建
author: ezhq
top: false
cover: false
toc: true
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: cn
comments: true
date: 2020-10-23 11:00:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592747899/Img/BlogCover/JS_gliloe.png
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592747899/Img/BlogCover/JS_gliloe.png
password:
summary: 前端开发环境构建备忘录
categories:
- Dev
tags:
- Dev
- Frontend
keywords:
updated: 2020-10-23 11:20:00
---

# 基本初始信息
* 系统版本：macOS Catalina（10.15）
* 终端Shell： `zsh` （已安装 `oh my zsh` ）
* 代理软件 `ShadowsocksX-NG` 正常工作

# 终端代理配置
1. 通过代理软件查询代理监听代理端口（如：地址为 `127.0.0.1` ，端口为 `1086` ）
2. 在系统 `zshrc` 配置文件(一般为 `private/ect/zshrc` )末尾追加如下配置：
    ```bash
    alias proxy="
        export http_proxy=http://127.0.0.1:1086;
        export https_proxy=http://127.0.0.1:1086;
    "
    alias unproxy="
        unproxy='unset all_proxy'
    "
    ```
3. 在系统终端中需要代理时候直接输入 `proxy` 即可开启代理，需要初始化代理配置时直接运行命令 `unproxy` 即可。

# Homebrew 安装
1. 开启终端代理
2. 运行如下 `Homebrew` 安装命令：
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
   ```

# Git 安装
1. 终端运行如下命令，通过 Homebrew 安装 Git
   ```bash
   brew install git
   ```
2. 重启终端

# NVM 安装
1. 到 [NVM 官方 repo](https://github.com/nvm-sh/nvm) 复制安装命令（一般安装位置为 username/.nvm）
2. 打开终端，执行复制的安装命令
3. 重启终端即可通过命令 `nvm --version` 查看 NVM 版本

# Node.js 安装
1. 在终端中通过下面命令安装最新版本 Node.js
   ```bash
   nvm install node
   ```

2. 在终端中通过下面命令安装 LTS 版本 Node.js
   ```bash
   nvm install --lts
   ```

3. 查询目前安装的 Node.js 版本，及当前使用的版本
   ```bash
   nvm ls
   ```

4. 修正当前 Node.js 使用版本为最新版（下方代码中最新版为刚刚安装的 v15.0.0 版）
   ```bash
   nvm use v15.0.0
   ```

# 配置本地 Git 多账户
## 初始化
1. 先查询是否已经配置全局账户信息
    ```bash
    git config --global user.name
    git config --global user.email
    ```
2. 若有配置查询结果，则需要清除已有配置
    ```bash
    git config --global --unset user.name
    git config --global --unset user.email
    ```

3. 判断本地是否存在默认 .ssh 文件
    ```bash
    cd ~/.ssh
    ```
    若提示没有此文件或目录，则通过下述命令生成该目录及相关文件（命令执行过程中的配置询问可会车使用认值）
    ```bash
    ssh-keygen
    ```
    这样即在 `username/` 文件夹下创建 `.ssh` 隐藏目录

## 配置
1. 进入 `.ssh` 目录
    ```bash
    cd ~/.ssh
    ```

2. 根据账户邮箱生成密钥
    ```bash
    ssh-keygen -t rsa -C "email@email.com"
    ```
    备注：配置过程中考虑到多账户因素，可自定义密钥名，如 `github_yourname_rsa` 等形式；其他自定义可采用默认配置。

3. 重复步骤1～步骤2，将多个账户的密钥依次生成
4. 将上述步骤生成的密钥**逐个**在本地启用
    ```bash
    ssh-add ~/.ssh/github_yourname_rsa
    ```
    备注：执行命令后出现 `Identity added: /Users/.....` 为本地密钥启用成功
5. 设置本地密钥配置文件
   1. 在目录 `user/username/.ssh` 下创建文件 `config` ，也可直接通过下述命令创建：
        ```bash
        cd ~/.ssh
        touch config
        ```

   2. 编辑 `config` 文件，按照下列格式，逐个添加账户配置，并保存
        ```bash
        Host yourname
            HostName github.com
            PreferredAuthentications publickey
            User Git
            IdentityFile ~/.ssh/github_****_rsa
        ```
        备忘：个别字段说明
        * Host: 自定义昵称，唯一，便于后续通过这个自定义昵称匹配对应密钥
        * HostName: 域名，Git 账号网站域名
6. 分别将步骤 1～3 中生成的**公钥文件内容（`github_yourname_rsa.pub`，一定要 `.pub` 结尾的文件）**粘贴到对应到平台账号设置中。

## 测试
1. 通过以下命令测试是否配置成功，`yourHost` 指配置步骤 5.2 中的 `Host` 字段
    ```bash
    ssh -T yourHost
    ```
    备注：若结果为 `Hi <yourname>! You've ...... , but GitHub does not provide shell access.` 即为配置成功。

## 使用
1. 后续执行 `git clone` 命令时需要进行以下变化(以往使用第一条命令，现在配置多账户后，通过第二条命令形式执行命令，即把 `github.com` 替换为配置文件中配置对应的 `Host` 字段值，不包括尖引号 `<` 和 `>`)
    ```bash
    # Past
    git clone git@github.com:yourname/whatever.git

    # Now
    git clone git@<yourHostValue>:yourname/whatever.git
    ```

2. 后续建议 `git clone` 代码之后尽早设定编辑此代码的**账户**和**分支**，避免提交代码时才发现是使用默认全局 Git 账户或主分支进行的代码更改。下面代码为示例代码：
    ```bash
    git clone git@alice:alice/whatever.git
    cd whatever
    git config user.name "alice"
    git config suer.email "alice@email.com"
    ```

3. 若同时使用博客框架 Hexo，则有以下地方需要修改
   1. 博客配置文件 `_config.yml` 中 `deploy` 内容下的 `respository` 字段值要做相应改变（由 `respository: git@github.com:......` 改为 `git@alice:......`）。
   2. 博客项目 Git 文件 `.git/config` 中，`remote "origin"`  部分 `url` 字段值要改为 `url = git@alice:......` 。

# Yarn
# Hexo
# VSCode