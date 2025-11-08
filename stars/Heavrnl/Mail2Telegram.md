---
project: Mail2Telegram
stars: 104
description: |-
    Forward emails to Telegram/把邮件转发到Telegram
url: https://github.com/Heavrnl/Mail2Telegram
---

![img](./logo/logo-title.png)

<div align="center">
  <a href="./README.md">中文</a> |
  <a href="./readme/README_EN.md">English</a>
</div>
<br>


<div align="center">

![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white) [![License: GPL-3.0](https://img.shields.io/badge/License-GPL%203.0-4CAF50?style=flat-square)](https://github.com/Heavrnl/mail2telegram/blob/master/LICENSE) 




</div>

# Mail2Telegram

Mail2Telegram 可以实时监控多个邮箱并将邮件发送到 Telegram 中。扩展功能支持提取邮件验证码后发送到剪贴板

## 快速启动

### 准备工作

以Gmail为例：
1. 登录Gmail，在设置中开启IMAP访问服务
2. 若开启2FA，请参考[这里](https://support.google.com/mail/answer/185833?hl=zh-Hans)获取应用密码
3. 获取到应用密码后，在config.py中的PASSWORD填写应用密码

（其他邮箱同理，请自行前往邮箱设置开启IMAP访问服务）
>**注意**：由于微软修改了outlook的连接方式，导致outlook邮箱现在无法在本项目中使用。若有需求，可以设置邮件转发到本项目所使用的邮箱


### 部署步骤

1. 克隆仓库并进入项目目录：

```bash
git clone https://github.com/Heavrnl/Mail2Telegram.git
cd ./Mail2Telegram
```

2. 配置 `config.py`：
   - 复制 `config-template.py` 并重命名为 `config.py`
   - 填写必要的配置信息

```python
EMAILS = [
    {
        'EMAIL': 'example@gmail.com',
        'PASSWORD': 'password/application password',
        'IMAP_SERVER': 'imap.gmail.com',
        'IMAP_SERVER_PORT': 993,
    },
    {
        'EMAIL': 'example@qq.com',
        'PASSWORD': 'password/application password',
        'IMAP_SERVER': 'imap.qq.com',
        'IMAP_SERVER_PORT': 993,
    },
    # 可以添加更多邮箱配置... 
]
TELEGRAM_BOT_TOKEN = 'BOT_TOKEN'
TELEGRAM_CHAT_ID = 'CHAT_ID'  # 主要邮件转发到的chat_id，可以是自己的user_id
TELEGRAM_JUNK_CHAT_ID = 'CHAT_ID' # 把垃圾邮件转发到的chat_id，如果未设置(TELEGRAM_JUNK_CHAT_ID='')，则跳过垃圾邮件转发
RETRY_LIMIT = 5  # 失败后重试次数
RETRY_DELAY = 5  # 失败重试时间间隔 
RECONNECT_INTERVAL = 1800  # 主动断开重连时间，单位秒 
RETRY_PAUSE = 600  # 重试多次失败后，停止时间，单位秒 
```

3. 启动服务：

```bash
docker-compose up -d
```

4. 当您收到 Telegram 机器人发送的"登录成功"消息时，表示服务已成功运行。

## 扩展功能

### 提取邮件验证码并发送至剪贴板
支持本地正则匹配和AI（[GitHub Models](https://docs.github.com/zh/github-models/prototyping-with-ai-models)/[Gemini](https://aistudio.google.com/apikey)）提取验证码，具体配置在下面说明

1. 部署剪贴板同步服务 [Jeric-X/SyncClipboard](https://github.com/Jeric-X/SyncClipboard)，请自行前往该项目查看部署方法

2. 部署验证码提取服务 [Heavrnl/ExtractVerificationCode](https://github.com/Heavrnl/ExtractVerificationCode)

```bash
git clone https://github.com/Heavrnl/ExtractVerificationCode
```
```bash
cd ExtractVerificationCode
```

配置 `.env` 文件，把上面部署好的剪贴板同步服务相关配置填入：
```bash
cp .env.example .env
```
```ini
# 选择使用的API类型：azure(GitHub Models) 或 gemini
API_TYPE=gemini

# 是否启用本地正则匹配提取验证码（启用后会优先使用本地匹配，失败后再尝试API）
USE_LOCAL=false

# Prompt模板
PROMPT_TEMPLATE=从以下文本中提取验证码。只输出验证码，不要有任何其他文字。如果没有验证码，只输出'None'。\n\n文本：{input_text}\n\n验证码：

# Azure API相关配置
AZURE_ENDPOINT=https://models.inference.ai.azure.com
AZURE_MODEL_NAME=gpt-4o-mini
# Azure API认证Token（使用GitHub Token进行认证）
GITHUB_TOKEN=

# Gemini API相关配置
GEMINI_API_KEY=
GEMINI_MODEL=gemini-1.5-flash



# 剪贴板同步配置
SYNC_URL=your_sync_url
SYNC_USERNAME=your_username
SYNC_TOKEN=your_token

# 是否开启调试模式（true/false）
DEBUG_MODE=false
```


> **注意**：若想要最精确的提取验证码，请使用ai模型，本地正则匹配可能会有误差

启动服务：
```bash
docker-compose up -d
```

3.修改我们本项目中的`docker-compose.yml`文件，把`ENABLE_EVC=false`改为`ENABLE_EVC=true`


配置 `tools/send_code.py` 文件：
- 如果验证码提取服务与本项目部署在同一服务器且使用默认端口(5788)，则无需修改
- 否则需要修改服务地址和端口

```python
# 替换为您的 ExtractVerificationCode 应用程序的实际地址
url = 'http://evc:5788/evc'
```

启动
```bash
docker-compose up -d
```

## 关于隐私

ExtractVerificationCode 项目在处理邮件内容时采取了以下安全措施：

1. 邮件文本脱敏处理：在发送给 AI 模型前会自动移除敏感信息
2. 文本筛选：只有包含验证码相关内容的邮件才会被发送给AI模型，不会发送全部邮件

若还是怕AI提供商获取你的信息，可以本地部署大模型或者只用本地正则匹配提取验证码



## 致谢

- [Jeric-X/SyncClipboard](https://github.com/Jeric-X/SyncClipboard) - 跨平台剪贴板同步工具


## 捐赠

如果你觉得这个项目对你有帮助，欢迎通过以下方式请我喝杯咖啡：

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/0heavrnl)


