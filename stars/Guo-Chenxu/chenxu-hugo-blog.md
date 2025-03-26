---
project: chenxu-hugo-blog
stars: 3
description: |-
    采用hugo框架, papermod主题搭建的博客
url: https://github.com/Guo-Chenxu/chenxu-hugo-blog
---

# hugo 博客搭建(本地)

本项目参考自[hugo框架](https://gohugo.io/), [paperMode主题](https://github.com/adityatelange/hugo-PaperMod), 以及[paperMod主题的改版](https://github.com/xyming108/sulv-hugo-papermod), 并做了一些修改, 目前是可以开箱即用

[我的博客地址](http://www.chenxutalk.top)

## 安装 hugo

windows 用户直接去[hugo 官网](https://gohugo.io/)下载框架
下载完之后在命令行中输入 `hugo version` 出现以下内容说明安装成功
<img src="https://cdn.jsdelivr.net/gh/Guo-Chenxu/imgs@main/imgs/202306211550901.png" alt = "hugo版本信息"/>

## 创建博客

本教程仅讲解本项目的使用, 具体从 0 开始的搭建博客请参考[这些文章](https://www.sulvblog.cn/posts/blog/)

首先把该项目拉下来`git clone https://github.com/Guo-Chenxu/chenxu-hugo-blog.git`

然后你的博客就创建完成啦~~有些敷衍~~, 具体配置可以参考上面的文章, 或者看代码内的注释进行配置即可

## 启动博客

在项目目录下进入终端, 在终端直接输入 hugo server -D , 出现下面这些信息就说明运行成功了

<img src="https://cdn.jsdelivr.net/gh/Guo-Chenxu/imgs@main/imgs/202306212141479.png"/>

浏览器输入 localhost:1313 就可以开始预览你的博客界面

输入 hugo 或者 hugo -F --cleanDestinationDir 就可以生成 public 文件夹, 这个文件夹可以部署到云服务器或者托管到 github 上, 推荐后者, 因为前者只会往 public 里面添加内容而不会删除, 后者则是保证每次生成的都是和外界一样的新的 public 文件夹

> windows 用户可以直接运行目录下的 updatePublic.dat 即可

## 写文章

输入`hugo new xxx.md`直接在 content 目录下生成该文章(文章头部信息的模板是 archetypes 下的 default.md)

或者可以输入`hugo new posts/study/xxx.md`, 在 study 目录下生成文章

至此, 你的本地博客就搭建完毕了, 快起试试吧(\*\^\_\^\*)


