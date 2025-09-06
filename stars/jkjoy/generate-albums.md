---
project: generate-albums
stars: 3
description: |-
    自动化生成相册Automatically generate photo albums
url: https://github.com/jkjoy/generate-albums
---

# 自动化生成相册

## 具体功能

把源仓库作为私有仓库,存放照片

脚本会自动抹除照片含有exif的信息(如果有).

在目标仓库生成缩略图和原图(已处理).

点击缩略图会打开展示原图.

## 免责

模板来自于网络

可以自行修改模板

## 使用方法

>[!TIP]
>使用方法
 
>1. 点击`Use this template`创建一个新的仓库
<a href="https://github.com/new?template_name=generate-albums&template_owner=jkjoy" target="_blank">点击这里</a>

在`action`中设置`secret`
![](https://file.imsun.pw/image/f1427467-b143-4db0-b736-d80872c475e6.png)

`TOKEN`为你的github token(获取方法https://github.com/settings/tokens 生成一个token)

`REPO`为你想要生成相册的仓库名称 如`username/repo`

>2. `template`目录下为模板文件,可自行调整 标题 等

>3. `photos`为图片文件夹,照片上传到此文件夹中,会自动生成相册

photos 根目录下的照片默认标题为`分享生活`

新建文件夹,文件夹名称为标题

照片同名txt中的文本为描述说明 最高优先级

如 `1.jpg` `1.txt` 则使用1.txt中的文本为描述说明

目录下`描述.txt`为此目录下所有图片的描述说明 第二优先级

如果两者都没有则使用照片文件名为描述说明


