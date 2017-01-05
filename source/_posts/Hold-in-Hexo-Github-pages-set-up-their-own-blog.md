---
title: 手把手教用 Hexo + Github pages搭建属于自己的博客
date: 2016-08-17 15:51:53
tags: Hexo
---

#### **前言**
对于每一个自己写过博客的同学来说，拥有自己的个人博客站点是一件很让人值得兴奋的事情，接下来就让我们一起来利用“Hexo + Github pages“搭建属于自己的个人博客吧……^^

<!-- more -->

#### **效果图**
先放一张搭建完成后的效果图给大家瞧瞧。
感兴趣的同学也可以前往[我的个人博客](https://guowj.github.io/ "我的个人博客")溜达溜达。

![搭建成功效果图](http://img.blog.csdn.net/20160728130431476)

#### **准备**
**1、安装Node.js**（[下载](https://nodejs.org/en/download/ "下载node")）

因为 Hexo 是一个基于nodejs 的静态博客网站生成器，所以安装node.js是必不可少的。

![img](http://img.blog.csdn.net/20160728141718383)

**2、安装git**（[下载](https://git-scm.com/downloads "下载git")）

既然是基于Github pages搭建的Blog,安装Git肯定是必须的，安装好以后，直接通过指令即可将Hexo部署到 GitHub Pages。
如果有装Xcode的同学，此步可省略，因为Xcode自带有Git。

![img](http://img.blog.csdn.net/20160728141748809)

#### **开始安装Hexo**
竟然 Node.js 和 Git 都已经安装好了，那么我们就可以开始安装Hexo了。

**1、在本地建立一个文件夹，用户存放Hexo的配置文件,例如：Blog。**

![img](http://img.blog.csdn.net/20160728140157923)

**2、然后打开 终端（Terminal） 定位到 Blog 文件夹。**

![img](http://img.blog.csdn.net/20160728140542134)

**3、正式开始安装 hexo**

执行命令：`sudo npm install -g hexo`

![img](http://img.blog.csdn.net/20160728141331834)

输入密码

![img](http://img.blog.csdn.net/20160728141357429)

**4、初始化 Hexo**

执行命令：`hexo init`

![img](http://img.blog.csdn.net/20160728142717747)

**5、生成静态页面**

执行命令：`hexo generate`

![img](http://img.blog.csdn.net/20160728143103014)

**6、启动本地服务**

执行命令：`hexo server`

![img](http://img.blog.csdn.net/20160728143627537)

浏览器输入 [http://localhost:4000](http://localhost:4000)

![img](http://img.blog.csdn.net/20160728143830274)

好了，到此为止，Hexo就已经安装好了， Blog就是你的博客根目录。

#### **关联Github**

**1、New repository**

![img](http://img.blog.csdn.net/20160728144840210)

Repository name 固定写法为：

``` bash
your_user_name.github.io
```

![img](http://img.blog.csdn.net/20160728150800968)

把 your_user_name 替换为你的用户名然后点击 Create repository 就可以了。

PS：因为我已经新建过了，所有会报错。

**2、准备 Clone repository**

在本地新建一个文件夹Backup，然后把Blog中的文件和文件夹都剪切到Backup中去，让Blog为空。

PS：这一步操作是为了Clone repository时不报错。

**3、开始 Clone repository**

copy地址：

![img](http://img.blog.csdn.net/20160728160126975)

clone到Blog文件夹中：

![img](http://img.blog.csdn.net/20160728160152460)

**3、开始关联**

把Backup中的文件和文件夹都剪切到Blog中去，然后就可以把Backup给delete了。

打开文件夹中的 _config.yml 文件：

![img](http://img.blog.csdn.net/20160728160718541)

翻到最后面：

![img](http://img.blog.csdn.net/20160728161030434)

修改deploy：

``` bash
deploy:
  type: git
  repo: 填写你的repository clone地址
  branch: master
```

保存并退出

push 一下 git

![img](http://img.blog.csdn.net/20160728164643124)

打开终端定位到Blog

执行 install 命令：

``` bash
npm install hexo-deployer-git --save
```

执行部署命令：

``` bash
hexo deploy
```

回到 Github 点击 Settings：

![img](http://img.blog.csdn.net/20160728162323064)

在浏览器打开这个链接：

![img](http://img.blog.csdn.net/20160728162431891)

看到下面这个界面，恭喜你，你的个人博客已经搭建成功了：

![img](http://img.blog.csdn.net/20160728162539532)

PS：每次部署都需要依次执行命令：

``` bash
hexo clean
```

``` bash
hexo generate
```

``` bash
hexo deploy
```

#### **修改主题**

既然是个人博客站点，当然要选一套符合自己气质的主题［[Themes](https://github.com/hexojs/hexo/wiki/Themes "主题列表")］咯～

这里以我的为例：

[Oishi](https://github.com/henryhuang/oishi#%E6%89%80%E6%9C%89%E6%96%B0%E7%89%B9%E6%80%A7 "Oishi") - A white theme based on Landscape plus and Writing. - [Demo](https://guowj.github.io/)

**安装：**

终端定位到你博客的根目录然后执行命令：

``` bash
git clone https://github.com/henryhuang/oishi.git themes/oishi
```

安装完成以后你会发现在你本地的 themes 文件夹中多了一个 oishi 文件夹

![img](http://img.blog.csdn.net/20160728172518209)

**启用**

修改设置文件 _config.yml，把 theme 的值设置为 oshi

![img](http://img.blog.csdn.net/20160728172347559)

这里可以修改一下 title 和 author 信息，改成你喜欢的就好了。

![img](http://img.blog.csdn.net/20160728172924606)

修改好以后重新部署（前面有写）一下，然后push一下git，就可以在你的个人博客站点上面看到符合你气质的主题效果了～

``` bash
> 本文由作者原创，转载请注明出处，谢谢 ^ ^
```
