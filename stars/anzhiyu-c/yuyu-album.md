---
project: yuyu-album
stars: 5
description: |-
    这是一个优雅的相册展示项目，你可以用于展示你的相册或者壁纸
url: https://github.com/anzhiyu-c/yuyu-album
---

# 这是一个极简的相册展示项目

![首页](https://upload-bbs.miyoushe.com/upload/2025/06/12/125766904/edc34204be7ed35ecf2cf928095f7501_5939306686125312503.png?x-oss-process=image//resize,s_2000/quality,q_100/auto-orient,0/interlace,1/format,avif)

![预览大图](https://upload-bbs.miyoushe.com/upload/2025/06/12/125766904/d3d5abb0863416f034135a720b39bc29_1721098606931651516.png)

预览地址：[http://album.anheyu.com/](http://album.anheyu.com/)

## 技术栈

前端: vue3 + vite + element-plus

后端: go + gin

UI设计：[张洪](https://plog.zhheo.com/)

得益于社区有良好的生态后台直接使用了 [Pure Admin](https://pure-admin.cn/) 构建

## 项目运行

1. 从[https://github.com/anzhiyu-c/yuyu-album/releases](https://github.com/anzhiyu-c/yuyu-album/releases)下载对应服务器最新的发布版本，本项目目前使用 Linux 版本，下载yuyu-album-linux-amd64.zip

2. 目前只支持服务器部署

3. 将压缩包上传到服务器上，解压后会有一个yuyu-album-linux-amd64可执行文件

4. 在本目录新建一个.env 文件，内容如下

```env
ADMIN_USERNAME=anzhiyu
ADMIN_PASSWORD=anzhiyu
DB_USER=root
DB_PASS=root
DB_NAME=album
REDIS_ADDR=localhost:6379
REDIS_PASSWORD=
REDIS_DB=10
JWT_SECRET=yuyu_album
DB_HOST=127.0.0.1
DB_PORT=3306
ABOUT_LINK=https://github.com/anzhiyu-c/yuyu-album
APP_NAME=鱼鱼相册
APP_VERSION=1.0.0
ICP_NUMBER=湘ICP备2023015794号-2
USER_AVATAR=https://npm.elemecdn.com/anzhiyu-blog-static@1.0.4/img/avatar.jpg
API_URL=https://album.anheyu.com/
LOGO_URL=https://album.anheyu.com/logo.svg
ICON_URL=https://album.anheyu.com/logo.svg
DEFAULT_THUMB_PARAM=""
DEFAULT_BIG_PARAM=""
```

![服务器](https://upload-bbs.miyoushe.com/upload/2025/06/12/125766904/b2f2f7f1e4b064ca440fe07d19f9fda8_5236966675569255351.png)

## 配置说明

| 配置分类       | 参数名称              | 示例值                                                                                     | 说明                                                                   |
| :------------- | :-------------------- | :----------------------------------------------------------------------------------------- | :--------------------------------------------------------------------- |
| **管理员账户** | `ADMIN_USERNAME`      | `anzhiyu`                                                                                  | 管理员用户的登录名                                                     |
|                | `ADMIN_PASSWORD`      | `anzhiyu`                                                                                  | 管理员用户的登录密码                                                   |
| **数据库连接** | `DB_USER`             | `root`                                                                                     | 数据库连接用户名                                                       |
|                | `DB_PASS`             | `root`                                                                                     | 数据库连接密码                                                         |
|                | `DB_NAME`             | `album`                                                                                    | 要连接的数据库名称                                                     |
|                | `DB_HOST`             | `127.0.0.1`                                                                                | 数据库服务器的 IP 地址或主机名                                         |
|                | `DB_PORT`             | `3306`                                                                                     | 数据库服务器的端口号                                                   |
| **Redis 连接** | `REDIS_ADDR`          | `localhost:6379`                                                                           | Redis 服务器的地址和端口                                               |
|                | `REDIS_PASSWORD`      | (空字符串)                                                                                 | Redis 连接密码（如果无密码则留空）                                     |
|                | `REDIS_DB`            | `10`                                                                                       | 要连接的 Redis 数据库索引                                              |
| **安全及应用** | `JWT_SECRET`          | `yuyu_album`                                                                               | 用于 JWT 签名和验证的密钥，请务必使用强密钥                            |
|                | `ABOUT_LINK`          | `https://github.com/anzhiyu-c/yuyu-album`                                                  | 关于页面或项目相关信息的外部链接                                       |
|                | `APP_NAME`            | `鱼鱼相册`                                                                                 | 应用程序的名称                                                         |
|                | `APP_VERSION`         | `1.0.0`                                                                                    | 应用程序的版本号                                                       |
|                | `ICP_NUMBER`          | `湘ICP备2023015794号-2`                                                                    | 网站的 ICP 备案号（用于国内网站）                                      |
| **资源链接**   | `USER_AVATAR`         | `https://npm.elemecdn.com/anzhiyu-blog-static@1.0.4/img/avatar.jpg`                        | 默认用户头像的 URL                                                     |
|                | `API_URL`             | `https://album.anheyu.com/`                                                            | 应用程序的 API 基础 URL                                                |
|                | `LOGO_URL`            | `https://album.anheyu.com/logo.svg`                                                    | 应用程序 Logo 图片的 URL                                               |
|                | `ICON_URL`            | `https://album.anheyu.com/logo.svg`                                                    | 应用程序 Icon 图片的 URL                                               |
| **图片处理**   | `DEFAULT_THUMB_PARAM` | `"x-oss-process=image//resize,h_600/quality,q_100/auto-orient,0/interlace,1/format,avif"`  | 图片缩略图处理的默认参数字符串，通常用于 OSS（对象存储服务）的图片处理 |
|                | `DEFAULT_BIG_PARAM`   | `"x-oss-process=image//resize,s_2000/quality,q_100/auto-orient,0/interlace,1/format,avif"` | 大图处理的默认参数字符串，通常用于 OSS 的图片处理                      |

## 运行保活

然后你需要按照你填写的配置文件来配置你的数据库和redis，数据库目前只支持mysql，当你配置完数据库和redis就可以启动了，你可以直接在当前目录下面执行 ./yuyu-album-linux-amd64 来运行项目
如果你想要在后台运行并保活，可以使用以下命令：

```bash
nohup ./yuyu-album-linux-amd64 > yuyu-album.log 2>&1 &
```

或者如果你使用宝塔可以和我一样下载 宝塔面板进程守护管理器来运行
![宝塔守护进程](https://upload-bbs.miyoushe.com/upload/2025/06/12/125766904/55a3ba4db6d895772bda91797d3d73c2_1389209062891576208.png?x-oss-process=image//resize,s_2000/quality,q_100/auto-orient,0/interlace,1/format,avif)

启动命令和启动目录如下

```env
command=/www/wwwroot/album.anheyu.com/yuyu-album-linux-amd64
directory=/www/wwwroot/album.anheyu.com/
```

`你可以进入到 网站的 /login 路径登录上传你的相册图片`

另外你需要注意，现在没有修改密码的功能，所以请务必在环境变量中设置好 `ADMIN_USERNAME` 和 `ADMIN_PASSWORD`，并且不要泄露给他人。

