---
project: SaveAny-Bot
stars: 559
description: |-
    保存 Telegram 文件到各类存储空间 📂 (Alist、本地磁盘、Webdav, Minio...)  , 支持破解禁止保存的频道
url: https://github.com/krau/SaveAny-Bot
---

<div align="center">

# <img src="docs/logo.jpg" width="45" align="center"> Save Any Bot

**简体中文** | [English](README_EN.md)

把 Telegram 的文件保存到各类存储端.

> _就像 PikPak Bot 一样_

</div>

## 部署

### 从二进制文件部署

在 [Release](https://github.com/krau/SaveAny-Bot/releases) 页面下载对应平台的二进制文件.

在解压后目录新建 `config.toml` 文件, 参考 [config.example.toml](./config.example.toml) 编辑配置文件.

运行:

```bash
chmod +x saveany-bot
./saveany-bot
```

#### 添加为 systemd 服务

创建文件 `/etc/systemd/system/saveany-bot.service` 并写入以下内容:

```
[Unit]
Description=SaveAnyBot
After=systemd-user-sessions.service

[Service]
Type=simple
WorkingDirectory=/yourpath/
ExecStart=/yourpath/saveany-bot
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

设为开机启动并启动服务:

```bash
systemctl enable --now saveany-bot
```

#### 为 OpenWrt 及衍生系统添加开机自启动服务

创建文件 ` /etc/init.d/saveanybot` ，参考[saveanybot](./docs/saveanybot)自行修改.

`chmod +x /etc/init.d/saveanybot`

完成后，将文件复制到 `/etc/rc.d`并重命名为`S99saveanybot`.

`chmod +x /etc/rc.d/S99saveanybot`

#### 为 OpenWrt 及衍生系统添加快捷指令

创建文件` /usr/bin/sabot` ，参考[sabot](./docs/sabot)自行配置修改，注意此处文件编码仅支持 ANSI 936 .

`chmod +x /usr/bin/sabot`

之后，终端输入`sabot start|stop|restart|status|enable|disable`即可.

### 使用 Docker 部署

#### Docker Compose

下载 [docker-compose.yml](./docker-compose.yml) 文件, 在同目录下新建 `config.toml` 文件, 参考 [config.example.toml](./config.example.toml) 编辑配置文件.

启动:

```bash
docker compose up -d
```

#### Docker

```shell
docker run -d --name saveany-bot \
    -v /path/to/config.toml:/app/config.toml \
    -v /path/to/downloads:/app/downloads \
    ghcr.io/krau/saveany-bot:latest
```

## 更新

使用 `upgrade` 或 `up` 升级到最新版

```bash
./saveany-bot upgrade
```

如果是 Docker 部署, 使用以下命令更新:

```bash
docker pull ghcr.io/krau/saveany-bot:latest
docker restart saveany-bot
```

## 使用

向 Bot 发送(转发)文件, 或发送公开频道的消息链接, 按照提示操作.

---

## 赞助

本项目受到 [YxVM](https://yxvm.com/) 与 [NodeSupport](https://github.com/NodeSeekDev/NodeSupport) 的支持.

如果这个项目对你有帮助, 你可以考虑通过以下方式赞助我:

- [爱发电](https://afdian.com/a/acherkrau)

## Thanks

- [gotd](https://github.com/gotd/td)
- [TG-FileStreamBot](https://github.com/EverythingSuckz/TG-FileStreamBot)
- [gotgproto](https://github.com/celestix/gotgproto)
- All the dependencies

