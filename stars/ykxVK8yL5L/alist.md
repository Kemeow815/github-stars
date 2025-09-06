---
project: alist
stars: 282
description: |-
    🗂️A file list/WebDAV program that supports multiple storages, powered by Gin and Solidjs. / 一个支持多存储的文件列表/WebDAV程序，使用 Gin 和 Solidjs。
url: https://github.com/ykxVK8yL5L/alist
---

<div align="center">
  <a href="https://alist.nn.ci"><img width="100px" alt="logo" src="https://cdn.jsdelivr.net/gh/alist-org/logo@main/logo.svg"/></a>
  <p><em>🗂️A file list program that supports multiple storages, powered by Gin and Solidjs.</em></p>
<div>
  <a href="https://goreportcard.com/report/github.com/alist-org/alist/v3">
    <img src="https://goreportcard.com/badge/github.com/alist-org/alist/v3" alt="latest version" />
  </a>
  <a href="https://github.com/Xhofe/alist/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/Xhofe/alist" alt="License" />
  </a>
  <a href="https://github.com/Xhofe/alist/actions?query=workflow%3ABuild">
    <img src="https://img.shields.io/github/actions/workflow/status/Xhofe/alist/build.yml?branch=main" alt="Build status" />
  </a>
  <a href="https://github.com/Xhofe/alist/releases">
    <img src="https://img.shields.io/github/release/Xhofe/alist" alt="latest version" />
  </a>
  <a title="Crowdin" target="_blank" href="https://crwd.in/alist">
    <img src="https://badges.crowdin.net/alist/localized.svg">
  </a>
</div>
<div>
  <a href="https://github.com/Xhofe/alist/discussions">
    <img src="https://img.shields.io/github/discussions/Xhofe/alist?color=%23ED8936" alt="discussions" />
  </a>
  <a href="https://discord.gg/F4ymsH4xv2">
    <img src="https://img.shields.io/discord/1018870125102895134?logo=discord" alt="discussions" />
  </a>
  <a href="https://github.com/Xhofe/alist/releases">
    <img src="https://img.shields.io/github/downloads/Xhofe/alist/total?color=%239F7AEA&logo=github" alt="Downloads" />
  </a>
  <a href="https://hub.docker.com/r/xhofe/alist">
    <img src="https://img.shields.io/docker/pulls/xhofe/alist?color=%2348BB78&logo=docker&label=pulls" alt="Downloads" />
  </a>
  <a href="https://alist.nn.ci/guide/sponsor.html">
    <img src="https://img.shields.io/badge/%24-sponsor-F87171.svg" alt="sponsor" />
  </a>
</div>
</div>

---

English | [中文](./README_cn.md)| [日本語](./README_ja.md) | [Contributing](./CONTRIBUTING.md) | [CODE_OF_CONDUCT](./CODE_OF_CONDUCT.md)

## 与官方版本区别： 
- PikPak和迅雷X加入反代选项使用更方便
- 前台文件夹对比功能，文件夹下显示文件选中数量
- 提醒功能：文件复制完成或失败会提醒
- 复制功能：加入覆盖选项，复制文件夹时如果文件已经存在会跳过，后台复制任务列表进行了优化，进行中置顶，显示复制文件大小
- 存储功能：添加复制存储功能，存储分组及同步修改组内存储功能
- 离线下载逻辑和官方不一样：具体使用可以参考迅雷X的使用视频:<https://www.youtube.com/watch?v=5lh2o9Z_Kds>
- 可以添加自定义播放器方便调用其他APP播放
- 6盘(2dland.cn)、迅雷X实现other接口返回下载的原始链接，其中6盘为webdav的下载直链包含webdav的用户名和密码，如无必要请勿使用。调用地址:/api/fs/other   方法:Post 请求Body:{"path":"/path"}    
- 关于Other接口，目前迅雷X加入了网络请求的接口，这样可以进行其它的接口请求不需要再重复实现登陆操作，body,params可选。请求示例:
```
{"path":"/xunlei","password":"","data":{"action":"request","url":"https://api-pan.xunleix.com/drive/v1/tasks","method":"get","body":{"id":"__FILEID__","name":"__FILENAME__","PATH":"__FILEPATH__"},"params":{}}}
```
上面的代码进行了一次Alist之外的请求来获取下载任务列表。可通过url,method,body来构造自定义的请求,__FILEID__、__FILENAME__、__FILEPATH__ 分别对应文件的id,name和path信息。演示视频:<https://youtu.be/T8RpBbeoPqw>

<details>
<summary>Other接口请求说明：</summary>

<blockquote>
<details>
<summary>6盘Other接口请求说明：</summary>
  如需使用分享功能需要修改appid和secret如下：
  
  ```
	AppID      = "devDebugger/1.0"
	AppVersion = "1.0.0"
	AppSecret  = "Nkx3Y2xvZ2luLmNu"
  ```
  由于6盘不是采用http请求因此不能像迅雷X那样发送请求，固定请求格式如下:

- 获取分享列表请求:
```
{
  "path": "/2dland",
  "data": {
    "action": "share",
    "method": "list",
    "body": {
        "token": "",
        "limit":10
    }
  }
}
```

- 创建分享请求:
```
{
  "path": "/2dland",
  "data": {
    "action": "share",
    "method": "create",
    "body": {
        "path_list":["路径""],
        "lifetime":-1
    }
  }
}
```

- 获取分享信息请求:
```
{
  "path": "/2dland",
  "data": {
    "action": "share",
    "method": "get",
    "body": {
        "identity":"分享ID"
    }
  }
}
```
- 保存分享请求:
```
{
  "path": "/2dland",
  "data": {
    "action": "share",
    "method": "save",
    "body": {
        "identity":"分享ID"
    }
  }
}
```
- 删除分享请求:
```
{
  "path": "/2dland",
  "data": {
    "action": "share",
    "method": "delete",
    "body": {
        "identity":["分享ID"]
    }
  }
}
```

- 解析离线请求:
```
{
  "path": "/2dland",
  "data": {
    "action": "offline",
    "method": "parse",
    "body": {
        "url":"磁力链接",
    }
  }
}
```

- 添加离线请求:
```
{
  "path": "/2dland",
  "data": {
    "action": "offline",
    "method": "add",
    "body": {
        "url":"磁力链接",
        "save_path":"/"
    }
  }
}
```
获取离线列表:
```
{
  "path": "/2dland",
  "data": {
    "action": "offline",
    "method": "list",
    "body": {
        "token": "",
        "limit":10
    }
  }
}
```

- 删除离线请求:
```
{
  "path": "/2dland",
  "data": {
    "action": "offline",
    "method": "delete",
    "body": {
        "identity":["离线ID"]
    }
  }
}
```
</details>
</blockquote>
</details>

## Linux安装脚本
```
curl -fsSL "https://raw.githubusercontent.com/ykxVK8yL5L/alist/main/linux.sh" | bash -s install
```

## Serv00
```
wget -O alist-freebsd.sh https://raw.githubusercontent.com/ykxVK8yL5L/alist/main/serv00.sh && sh alist-freebsd.sh
```
## Android可使用Termux运行 项目地址如下：
https://github.com/ykxVK8yL5L/termux-packages/releases   
https://github.com/ykxVK8yL5L/AListFlutter/releases

## Docker 配置文件路径 /opt/alist 访问端口:10021 
```
docker run  --name="alist" -p 10021:5244 -v /opt/alist:/opt/alist/data -e ALIST_ADMIN_PASSWORD='admin' ykxvk8yl5l/alist:latest
```

## Features

- [x] Multiple storages
    - [x] Local storage
    - [x] [Aliyundrive](https://www.alipan.com/)
    - [x] OneDrive / Sharepoint ([global](https://www.office.com/), [cn](https://portal.partner.microsoftonline.cn),de,us)
    - [x] [189cloud](https://cloud.189.cn) (Personal, Family)
    - [x] [GoogleDrive](https://drive.google.com/)
    - [x] [123pan](https://www.123pan.com/)
    - [x] FTP / SFTP
    - [x] [PikPak](https://www.mypikpak.com/)
    - [x] [S3](https://aws.amazon.com/s3/)
    - [x] [Seafile](https://seafile.com/)
    - [x] [UPYUN Storage Service](https://www.upyun.com/products/file-storage)
    - [x] WebDav(Support OneDrive/SharePoint without API)
    - [x] Teambition([China](https://www.teambition.com/ ),[International](https://us.teambition.com/ ))
    - [x] [Mediatrack](https://www.mediatrack.cn/)
    - [x] [139yun](https://yun.139.com/) (Personal, Family)
    - [x] [YandexDisk](https://disk.yandex.com/)
    - [x] [BaiduNetdisk](http://pan.baidu.com/)
    - [x] [Terabox](https://www.terabox.com/main)
    - [x] [UC](https://drive.uc.cn)
    - [x] [Quark](https://pan.quark.cn)
    - [x] [Thunder](https://pan.xunlei.com)
    - [x] [Lanzou](https://www.lanzou.com/)
    - [x] [ILanzou](https://www.ilanzou.com/)
    - [x] [Aliyundrive share](https://www.alipan.com/)
    - [x] [Google photo](https://photos.google.com/)
    - [x] [Mega.nz](https://mega.nz)
    - [x] [Baidu photo](https://photo.baidu.com/)
    - [x] SMB
    - [x] [115](https://115.com/)
    - [X] Cloudreve
    - [x] [Dropbox](https://www.dropbox.com/)
    - [x] [FeijiPan](https://www.feijipan.com/)
    - [x] [dogecloud](https://www.dogecloud.com/product/oss)
- [x] Easy to deploy and out-of-the-box
- [x] File preview (PDF, markdown, code, plain text, ...)
- [x] Image preview in gallery mode
- [x] Video and audio preview, support lyrics and subtitles
- [x] Office documents preview (docx, pptx, xlsx, ...)
- [x] `README.md` preview rendering
- [x] File permalink copy and direct file download
- [x] Dark mode
- [x] I18n
- [x] Protected routes (password protection and authentication)
- [x] WebDav (see https://alist.nn.ci/guide/webdav.html for details)
- [x] [Docker Deploy](https://hub.docker.com/r/xhofe/alist)
- [x] Cloudflare Workers proxy
- [x] File/Folder package download
- [x] Web upload(Can allow visitors to upload), delete, mkdir, rename, move and copy
- [x] Offline download
- [x] Copy files between two storage
- [x] Multi-thread downloading acceleration for single-thread download/stream

## Document


## Demo

<https://al.nn.ci>

## Discussion

Please go to our [discussion forum](https://github.com/Xhofe/alist/discussions) for general questions, **issues are for bug reports and feature requests only.**

## Sponsor

AList is an open-source software, if you happen to like this project and want me to keep going, please consider sponsoring me or providing a single donation! Thanks for all the love and support:
https://alist.nn.ci/guide/sponsor.html

### Special sponsors

- [VidHub](https://okaapps.com/product/1659622164?ref=alist) - An elegant cloud video player within the Apple ecosystem. Support for iPhone, iPad, Mac, and Apple TV.
- [亚洲云](https://www.asiayun.com/aff/QQCOOQKZ) - 高防服务器|服务器租用|福州高防|广东电信|香港服务器|美国服务器|海外服务器 - 国内靠谱的企业级云计算服务提供商 (sponsored Chinese API server)
- [找资源](https://zhaoziyuan.pw/) - 阿里云盘资源搜索引擎

## Contributors

Thanks goes to these wonderful people:

[![Contributors](http://contrib.nn.ci/api?repo=alist-org/alist&repo=alist-org/alist-web&repo=alist-org/docs)](https://github.com/alist-org/alist/graphs/contributors)

## License

The `AList` is open-source software licensed under the AGPL-3.0 license.

## Disclaimer
- This program is a free and open source project. It is designed to share files on the network disk, which is convenient for downloading and learning Golang. Please abide by relevant laws and regulations when using it, and do not abuse it;
- This program is implemented by calling the official sdk/interface, without destroying the official interface behavior;
- This program only does 302 redirect/traffic forwarding, and does not intercept, store, or tamper with any user data;
- Before using this program, you should understand and bear the corresponding risks, including but not limited to account ban, download speed limit, etc., which is none of this program's business;
- If there is any infringement, please contact me by [email](mailto:i@nn.ci), and it will be dealt with in time.

---

> [@Blog](https://nn.ci/) · [@GitHub](https://github.com/Xhofe) · [@TelegramGroup](https://t.me/alist_chat) · [@Discord](https://discord.gg/F4ymsH4xv2)

