---
title: "My First Blog"
date: 2021-10-07T22:38:26+08:00

---

#### **1、Hugo简介**

搭建个人搭建个人博客有很多开源的博客框架，我使用的框架是[Hugo](https://gohugo.io/)。Hugo 是一个基于Go 语言的框架，可以快速方便的创建自己的博客。

Hugo 支持Markdown 语法，我们可以将自己的文章写成Markdown 的格式，放在我们用Hugo 创建的博客系统中，从而展示给他人。

#### **2、Git、Hugo安装**

*本人电脑操作系统为Windows 10 64位*

(1)、安装[Git for Windows](https://git-scm.com/download/win)

(2)、安装[Hugo二进制版](https://github.com/gohugoio/hugo/releases)

下载Hugo Windows 64位版压缩包，解压，将包含hugo.exe的目录添加到path变量，打开Git Bash，执行

`hugo version`

结果如下图所示，表示安装成功

![1](/images/1.png)

#### **3、创建一个GitHub仓库**

![2](/images/2.png)

这个仓库将用于发布在Hugo上生成的博客

#### **4、创建Hugo站点**

在Git Bash中，进入想要保存站点文件夹的路径，执行

`hugo new site myblog`

系统会生成一个名为myblog的站点工程文件夹

##### 目录结构如下：

>archetypes/ 
>
>content/     		#静态页面目录
>
>data/
>
>layouts/
>
>resourse/
>
>static/      		  #静态文件目录
>
>themes/     	   #主题目录
>
>config.toml 	  #配置文件

#### **5、添加主题**

在[Hugo 主题](https://themes.gohugo.io/)选择一款主题（我选择的是[hugo-theme-noteworthy](https://github.com/kimcc/hugo-theme-noteworthy)）,将其下载到themes目录下（或者在themes目录下使用指令添加）

然后修改根目录中的config.toml文件

![3](/images/3.png)

其中baseurl为要发布的GitHub网址，title为博客的名字，theme为主题的名字

#### **6、创建一篇博客**

在根目录中执行

`hugo new posts/my-first-blog.md`

在content\posts\目录下新增了my-first-blog.md文件，使用markdown编辑器即可编辑其中的内容（我使用的是[Typora](https://www.typora.io/)）

*在发布时需要把 draft: true 改为 draft: false 或者直接删除*

#### **7、本地服务器测试**

在根目录下执行

`hugo server`

然后在浏览器打开http://localhost:1313/即可进行本地预览，Ctrl+c即可停止服务器

#### **8、部署到GitHub**

在根目录下执行如下指令：

> `hugo` 
> #生成一个public文件夹，这个文件夹中的内容就是博客中的全部内容，需要将它们存放在Git仓库中
>
> `git init`
> #初始化仓库
>
> `git add -A`
> #将所有内容添加到git
>
> `git commit -m "first commit"`
> #提交到git本地
>
> `git remote add origin https://github.com/mosemandie/mosemandie.github.io.git`
> #关联到远程git，*这里需要写自己的git地址*
>
> `git push origin master`
> #推送到远程git

#### **9、修改GitHub上的分支**

因为站点部署在master分支上的，需要将分支修改到master分支

在库——Seetting——Pages：

![4](/images/4.png)



到这里，就把博客内容托管在了GitHub上，此时就可以通过https://mosemandie.github.io来访问博客了
