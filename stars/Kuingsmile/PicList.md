---
project: PicList
stars: 3027
description: |-
    An image upload and manage tool, base on PicGo
url: https://github.com/Kuingsmile/PicList
---

<div align="center">
  <img src="https://imgx.horosama.com/admin_uploads/2022/10/2022_10_05_633d79e401694.png" alt="PicList Logo">
  <h1>PicList</h1>
  <p><strong>强大的云存储与图床管理工具</strong></p>
  <a href="https://github.com/Kuingsmile/PicList/actions">
    <img src="https://img.shields.io/badge/code%20style-standard-green.svg?style=flat-square" alt="Code Style">
  </a>
  <a href="https://github.com/Kuingsmile/PicList/releases">
    <img src="https://img.shields.io/github/downloads/Kuingsmile/PicList/total.svg?style=flat-square" alt="Downloads">
  </a>
  <a href="https://github.com/Kuingsmile/PicList/releases/latest">
    <img src="https://img.shields.io/github/release/Kuingsmile/PicList.svg?style=flat-square" alt="Release">
  </a>
</div>

![仓库统计](https://repobeats.axiom.co/api/embed/9e4ec90b7b50f8e9c10d77439e49e26b303fabed.svg "Repobeats analytics image")

简体中文 | [English](https://github.com/Kuingsmile/PicList/blob/dev/README_en.md)

## 📑 目录

- [📑 目录](#-目录)
- [简介](#简介)
- [官方网址](#官方网址)
- [如何从PicGo迁移](#如何从picgo迁移)
- [PicList-Core](#piclist-core)
- [特色功能](#特色功能)
- [如何使用](#如何使用)
  - [如何在VSCode中使用](#如何在vscode中使用)
  - [如何在Typora中使用](#如何在typora中使用)
    - [**1.6.0版本及以上**](#160版本及以上)
    - [**1.6.0版本以下**](#160版本以下)
  - [如何在Obsidian中使用](#如何在obsidian中使用)
  - [如何在Docker中使用](#如何在docker中使用)
    - [使用docker run命令](#使用docker-run命令)
    - [使用docker-compose](#使用docker-compose)
- [已支持平台](#已支持平台)
- [下载安装](#下载安装)
  - [直接下载](#直接下载)
  - [Scoop（Windows）](#scoopwindows)
  - [Winget (Windows)](#winget-windows)
  - [Homebrew（macOS）](#homebrewmacos)
  - [系统版本要求](#系统版本要求)
    - [Windows](#windows)
    - [macOS](#macos)
    - [Linux](#linux)
- [应用截图](#应用截图)
- [开发说明](#开发说明)
  - [前提条件](#前提条件)
  - [开始开发](#开始开发)
  - [开发模式](#开发模式)
  - [生产构建](#生产构建)
- [其它相关](#其它相关)
- [License](#license)
- [Star Me](#star-me)

## 简介

PicList是一款高效的云存储和图床平台管理工具，基于PicGo深度二次开发，提供完整的图床功能和全面的云存储管理能力，主要特点包括：

- 完整保留PicGo所有功能，兼容大部分PicGo插件
- 扩展了内置图床平台，如WebDav、本地图床和SFTP等
- 相册支持同步云端删除文件
- 全面的云存储管理功能，包括文件操作、搜索和预览
- 内置图像处理工具，如水印、压缩、缩放、旋转和格式转换

## 官方网址

请访问 [PicList官网 piclist.cn](https://piclist.cn) 获取更多信息。

此外，你也可以访问[DeepWiki of PicList](https://deepwiki.com/Kuingsmile/PicList)了解更多关于项目架构和开发的内容。

## 如何从PicGo迁移

PicList `V1.5.0`以上版本提供 `一键迁移`功能，进入 `设置`页面，然后在 `从PicGo迁移`选项点击右侧按钮即可，迁移后请重启应用生效。

## PicList-Core

PicList的内核使用[PicList-core](https://github.com/Kuingsmile/PicList-Core)，这是基于原版PicGo-Core修改的版本，具有以下增强功能：

- 水印添加
- 图片压缩、缩放、旋转和格式转换
- CLI命令行支持
- 通过`picgo-server`命令启动上传服务器

如果您希望单独使用PicList-core，请访问[GitHub仓库](https://github.com/Kuingsmile/PicList-Core)或[npm包](https://www.npmjs.com/package/piclist)。

## 特色功能

- **完全兼容性**：适用于Typora、Obsidian和大多数PicGo插件
- **扩展平台支持**：新增WebDav、兰空图床、本地图床、SFTP等，原内置imgur图床额外支持账号登录上传
- **云端同步相册**：支持同步删除云端图片，兼容所有内置图床和多个插件
- **高级相册功能**：高级搜索、排序和批量URL修改
- **内置图像工具**：水印添加、图片压缩、图片缩放、图片旋转和格式转换，支持高级重命名
- **表单上传**：支持多电脑共享使用
- **配置同步**：支持配置同步至GitHub/Gitee/Gitea仓库
- **云存储管理**：云端目录查看、文件搜索、批量操作等功能
- **多格式预览**：支持预览图片、视频、文本和Markdown文件（查看[支持的文件格式列表](https://github.com/Kuingsmile/PicList/blob/dev/supported_format.md)）
- **批量操作**：支持使用正则表达式批量重命名云端文件
- **链接分享**：为私有存储桶生成预签名链接
- **易用性改进**：软件自动更新、多种启动模式、界面优化等

## 如何使用

### 如何在VSCode中使用

安装[VS-PicList](https://marketplace.visualstudio.com/items?itemName=Kuingsmile.vs-piclist)插件，与vs-picgo插件相比，该插件直接依赖于PicList桌面端软件，支持多种上传方式和直接在VSCode中进行云端删除等功能。

### 如何在Typora中使用

#### **1.6.0版本及以上**

**Typora 1.6.0-dev以及以上版本已原生支持PicList**。在1.10.6版本以下中，需要将Typora的语言设置为中文。

如果您使用的是1.8.0以下版本的Typora，需要同时设置PicList和PicGo(app)上传服务的路径为PicList的安装路径。

[Typora下载链接](https://typora.io/releases/all)

#### **1.6.0版本以下**

Windows系统：

1. 进入Typora设置页面，选择"图像"
2. 将上传服务设置为`PicGo(app)`
3. 在`PicGo路径`中填写PicList的安装路径

![Typora配置](https://user-images.githubusercontent.com/96409857/226522101-b3531b7b-534c-4149-b527-8738d4ebb041.png)

或者，您也可以使用`npm install piclist`命令安装PicList-core，然后将上传服务设置为`PicGo-Core(command line)`。

### 如何在Obsidian中使用

1. 在社区插件中搜索安装`Image auto upload Plugin`
2. 进入插件设置页面，将默认上传器修改为`PicGo(app)`
3. 设置`PicGo server`为`http://127.0.0.1:36677/upload`
4. 如需启用云端删除功能，请在删除接口中填入`http://127.0.0.1:36677/delete`

![Obsidian配置](https://user-images.githubusercontent.com/96409857/226522718-8378c480-9fb4-4785-87e1-d59808862016.png)

### 如何在Docker中使用

#### 使用docker run命令

```bash
docker pull kuingsmile/piclist:latest
docker run -d \
  --name piclist \
  --restart always \
  -p 36677:36677 \
  -v "./piclist:/root/.piclist" \
  kuingsmile/piclist:latest \
  node /usr/local/bin/picgo-server -k piclist123456
```

请将`./piclist`修改为您的配置文件`config.json`所在路径，将`piclist123456`修改为您自己的密钥。

#### 使用docker-compose

```yaml
version: '3.3'

services:
  node:
    image: 'kuingsmile/piclist:latest'
    container_name: piclist
    restart: always
    ports:
      - 36677:36677
    volumes:
      - './piclist:/root/.piclist'
    command: node /usr/local/bin/picgo-server -k piclist123456
```

使用`docker-compose up -d`命令启动。

## 已支持平台

|      平台      | 相册云删除 | 云存储管理 |
| :------------: | :--------: | :--------: |
|   内置AList    |     ✔️      |     ✔️      |
|     SM.MS      |     ✔️      |     ✔️      |
|     Github     |     ✔️      |     ✔️      |
|     Imgur      |     ✔️      |     ✔️      |
|   腾讯COS V5   |     ✔️      |     ✔️      |
|   阿里云OSS    |     ✔️      |     ✔️      |
|     又拍云     |     ✔️      |     ✔️      |
|     七牛云     |     ✔️      |     ✔️      |
| S3 API兼容平台 |     ✔️      |     ✔️      |
|     WebDAV     |     ✔️      |     ✔️      |
|   本地文件夹   |     ✔️      |     ✔️      |
|    内置SFTP    |     ✔️      |     ✔️      |
|     多吉云     |     ✔️      |     ✔️      |
| PicList(套娃)  |     ✔️      |     ✔️      |
|    兰空图床    |     ✔️      |     ✔️      |
|   自定义图床   |     x      |     x      |

**支持云删除功能的插件：**

- [picgo-plugin-s3](https://github.com/wayjam/picgo-plugin-s3)
- [picgo-plugin-alist](https://github.com/jinzhi0123/picgo-plugin-alist)
- [picgo-plugin-huawei-uploader](https://github.com/YunfengGao/picgo-plugin-huawei-uploader)
- [picgo-plugin-dogecloud](https://github.com/w4j1e/picgo-plugin-dogecloud)

## 下载安装

### 直接下载

[下载最新版本](https://github.com/Kuingsmile/PicList/releases/latest)

### Scoop（Windows）

```bash
scoop bucket add lemon https://github.com/hoilc/scoop-lemon
scoop install lemon/piclist
```

### Winget (Windows)

```bash
winget install Kuingsmile.PicList
```

### Homebrew（macOS）

```bash
# 安装
brew install piclist --cask

# 卸载
brew uninstall piclist
```

### 系统版本要求

#### Windows

- **支持的版本**: Windows 10及以上版本
- **架构**: `ia32` (x86), `x64` (amd64), `arm64`

#### macOS

- **支持的版本**: macOS Big Sur (11)及以上
- **架构**: Intel (x64)和Apple Silicon (arm64)

#### Linux

- **包括不限于**:
  - Ubuntu 18.04及更新版本
  - Fedora 32及更新版本
  - Debian 10及更新版本

## 应用截图

![上传界面](https://github.com/Kuingsmile/PicList/blob/dev/imgs/upload.png?raw=true)
![相册视图](https://github.com/Kuingsmile/PicList/blob/dev/imgs/gallery.png?raw=true)
![云存储管理](https://github.com/Kuingsmile/PicList/blob/dev/imgs/cloud_storage.png?raw=true)
![设置页面](https://github.com/Kuingsmile/PicList/blob/dev/imgs/settings.png?raw=true)
![图像编辑](https://github.com/Kuingsmile/PicList/blob/dev/imgs/image_editing.png?raw=true)
![深色主题](https://github.com/Kuingsmile/PicList/blob/dev/imgs/dark.png?raw=true)

## 开发说明

### 前提条件

1. 需要Node.js 20+ 和 Git
2. 了解npm相关知识
3. Mac需要Xcode环境，Windows需要Visual Studio环境

### 开始开发

```bash
git clone https://github.com/Kuingsmile/PicList.git
cd PicList
yarn  # 不要使用npm install
```

如需贡献代码，请参考[贡献指南](https://github.com/Kuingsmile/PicList/blob/dev/CONTRIBUTING.md)。

### 开发模式

```bash
yarn run dev
```

开发模式具有热重载特性，但可能不稳定。如果进程崩溃，请用`Ctrl+C`退出并重新启动。

注意：开发模式运行后，PicList的应用图标会出现在任务栏/系统托盘中。

### 生产构建

```bash
yarn run build
```

构建成功后，安装文件将出现在`dist_electron`目录中。

如果遇到网络问题导致electron-builder下载失败，可以设置镜像源：

**Linux/macOS:**

```bash
export ELECTRON_MIRROR="https://npmmirror.com/mirrors/electron/"
```

**Windows:**

```cmd
set ELECTRON_MIRROR=https://npmmirror.com/mirrors/electron/
```

## 其它相关

- [PicList-Core](https://github.com/Kuingsmile/PicList-Core)：基于PicGo-Core的核心库，用于CLI操作和项目开发
- [PicHoro](https://github.com/Kuingsmile/PicHoro)：配合PicList使用的手机APP
- [VS-PicList](https://github.com/Kuingsmile/vs-PicList/)：配合PicList使用的VSCode插件

## License

本项目基于MIT协议开源，欢迎大家使用和贡献代码，感谢原作者Molunerfinn的开源精神。

[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2017-present Molunerfinn  
Copyright (c) 2023-present Kuingsmile

## Star Me

[![GitHub stars](https://img.shields.io/github/stars/kuingsmile/PicList?logo=github&style=social)](https://github.com/kuingsmile/PicList/stargazers)

[![Stargazers over time](https://starchart.cc/kuingsmile/PicList.svg)](https://github.com/kuingsmile/PicList/stargazers)

