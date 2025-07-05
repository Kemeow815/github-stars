---
project: MixFile
stars: 254
description: |-
    使用图床储存任意文件
url: https://github.com/InvertGeek/MixFile
---




<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/InvertGeek/MixFile">
    <img src="https://invertgeek.github.io/mixfile-doc/logo.png" alt="Logo" width="200" height="200">
  </a>
  <h1 align="center">MixFile</h1>
  <p align="center">
    无限空间,不限速,加密储存
  </p>
</div>

## MixFile 介绍
MixFile是一款可以上传加密文件并分享的安卓APP \
可实现本地加密上传,加密下载文件,在线播放加密视频 \
加密时会自动生成随机密钥进行加密,上传完成后,密钥 文件地址 文件大小等信息会附加在分享码中 \
将分享码发送给他人即可实现分享文件 \
已发布版本: https://github.com/InvertGeek/MixFile/releases \
使用帮助: https://invertgeek.github.io/mixfile-doc/help.html \
TG群: https://t.me/mixfilefx

## 命令行版本
https://github.com/InvertGeek/mixfilecli

## 详细原理
将文件切割为1MB的分片,然后加密隐藏到空白图片中 \
非伪装,图片都是真实有效可被解析,然后上传所有分片,最后聚合分片索引信息 \
再将信息压缩隐写到一张索引图片中,最后上传索引图片 \
下载时优先解析索引,再根据索引信息获取到所有分片链接进行逆操作即可还原文件 \
视频上传后可直接在线播放,已实现range请求,可切换进度条,智能实时解析进度对应的图片信息 \
基于kotlin协程优化并发,上传下载均可达到数十Mb每秒,和普通文件直链基本无区别

## 安全性
文件是在本地加密后上传的,不泄漏分享码任何人无法解密 \
MixFile采用256位的AES-GCM算法进行加密,所有的文件分片,以及包含所有分片地址的索引文件都是加密储存的 \
256位的密钥即使是量子计算机采用grover算法,也具有经典计算机下128位的安全性,破解时间远超已知宇宙年龄

## WebDAV
原生支持WebDav,可挂载到Alist中 \
Alist中新建储存,选择webdav驱动,地址填写http://127.0.0.1:4719/api/webdav即可 \
上传.mix_list 列表文件，会将解析其中所有文件并添加到当前文件夹 \
上传.mix_dav存档文件到目录中,会解析其中存档的数据结构，添加到当前文件夹 \
每个不为空的文件夹中会显示一个"当前目录存档.mix_dav"文件,包含当前文件夹以及其子文件夹的webdav数据 \
注意: 当前目录存档.mix_dav 文件在存档中并不存在，只是显示效果，每次下载时动态生成内容,无法移动,复制,删除 \
使用Alist挂载后,点击下载,即可下载当前目录以及其子文件夹所有数据作为webdav存档 \
在Alist等没有文件名长度限制的系统中挂载,如果新建文件夹,名称直接填写文件分享码(需要去掉mf://),则会自动将分享码解析并导入到当前文件夹

### 防篡改
SHA256校验在分享码泄露的情况下,也可确保文件不会被篡改,每个分片都会在下载时进行校验,即使是视频从中间播放也可确保百分百是原文件  \
单一分享码对应单一文件,同一个分享码即使是上传到自己的储存服务,也没有任何办法进行数据篡改(包括二次利用mixfile原理使用相同的密钥加密不同数据),下载解析或播放时检测到篡改会自动中断数据流 \
也就是可以保证同一个分享码，不可能下载到不同的文件,只要分享码内容相同,无论以什么手段修改云端的返回的内容都是无法通过校验的 \
原理: 索引文件结构中会储存所有URL以及其SHA256原内容哈希值,分享码中包含索引文件地址以及其SHA256哈希值,


## 免责声明

+   不能百分百保证文件永久有效,请自行对重要文件做好本地备份。
+   请勿使用本项目上传不符合社会主义核心价值观的文件。
+   该项目仅用于学习和技术交流，开发者不承担任何由使用者的行为带来的法律责任。

## Github Star
[![Stargazers over time](https://starchart.cc/InvertGeek/MixFile.svg?variant=adaptive)](https://starchart.cc/InvertGeek/MixFile)
