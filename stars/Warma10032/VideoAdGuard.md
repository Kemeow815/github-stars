---
project: VideoAdGuard
stars: 348
description: |-
    哔哩哔哩浏览器插件：基于大语言模型，对B站视频中的植入广告进行检测。一键跳过视频中的植入/口播广告。
url: https://github.com/Warma10032/VideoAdGuard
---

# VideoAdGuard - B站视频植入广告检测器

VideoAdGuard 是一个基于大语言模型的B站视频植入广告检测工具，能够自动识别B站视频中的植入广告内容，并提供跳过广告的功能。
如果你觉得这个插件有用，请给项目点个Star⭐支持一下！

<div align="center">
  <img src="./icons/icon128.png" alt="VideoAdGuard Logo">
</div>

## News

- v1.2.1
  - 支持自定义UP白名单
- v1.2.0
  - 支持自动跳过
- v1.1.3
  - 支持本地Ollama模型

## 功能特点

- 🎯 **精准识别**：采用大语言模型分析视频字幕，准确定位植入广告内容
- 🚀 **便捷操作**：检测到广告后自动显示跳过按钮，一键跳过广告片段
- 🔄 **自动跳过**：支持自动跳过已识别的广告内容（v1.2.0新增）
- 🌈 **广泛兼容**：支持多种主流浏览器，包括Edge、Chrome等
- ⚙️ **灵活定制**：支持多种AI模型接入，包括智谱AI、OpenAI、DeepSeek等
- 🏠 **本地部署**：支持本地Ollama模型，保护隐私数据（v1.1.3新增）

## 安装方法

### 1.Edge浏览器

直接从Microsoft Edge插件商店安装：
[Edge插件商店 - VideoAdGuard](https://microsoftedge.microsoft.com/addons/detail/videoadguard/mpfelbgplaolpbjmdbjjajonkmmgekgo/)

### 2.其他浏览器（油猴脚本版）

**注意**：油猴版本更新不及时，如果是Chrome内核浏览器推荐采用第3种方法
1. 安装[篡改猴插件](https://www.tampermonkey.net/)
2. 从[GreasyFork](https://greasyfork.org/zh-CN/scripts/531743-b%E7%AB%99%E8%A7%86%E9%A2%91%E6%A4%8D%E5%85%A5%E5%B9%BF%E5%91%8A%E6%A3%80%E6%B5%8B%E5%99%A8-videoadguard/)安装脚本

### 3.Chrome内核浏览器手动安装（适合二次开发）

1. 下载插件压缩包：
   - [夸克网盘](https://pan.quark.cn/s/4afa6f60a5f2)
   - [GitHub Releases](https://github.com/Warma10032/VideoAdGuard/releases)
2. 解压压缩包
3. 打开浏览器，进入扩展管理页面，开启开发者模式
4. 点击"加载已解压的扩展程序"，选择解压后的文件夹

## 使用方法

1. **Edge浏览器**：安装完成后，点击插件图标完成设置
    
    ![](https://gcore.jsdelivr.net/gh/Warma10032/image@main/blog/VideoAdGuard1.png)
    
2. **其他浏览器**：安装完成后，进入B站视频页面，点击右下角齿轮图标进行设置

    ![](https://gcore.jsdelivr.net/gh/Warma10032/image@main/blog/VideoAdGuard2.png)

3. 设置API密钥和模型（详见下方API设置说明）

4. 打开任意带有字幕的B站视频，插件会自动检测广告内容

5. 当检测到广告时，会在视频播放器右下角显示"跳过广告"按钮

## API设置说明

本插件需要配置大语言模型API才能正常工作。可以使用以下免费模型：

- **API地址**：`https://open.bigmodel.cn/api/paas/v4/chat/completions`（智谱AI）
- **模型名称**：`glm-4-flash`（智谱AI免费模型）
- **API密钥**：需要在[智谱AI平台](https://bigmodel.cn/usercenter/proj-mgmt/apikeys)注册并获取

插件支持所有兼容OpenAI SDK的大语言模型。目前我们已经测试了部分模型，但还需要更多用户的测试反馈。如果您使用了下表中的模型，请通过GitHub Issues告诉我们您的使用体验，帮助我们完善兼容性列表。
| 模型名称 | 测试结果 | API地址填写示例 | API密钥官网 |
|---------|---------|----------------|--------|
| 智谱AI (GLM系列) | ✅ | https://open.bigmodel.cn/api/paas/v4/chat/completions | [智谱AI](https://bigmodel.cn/) |
| DeepSeek | ✅ | https://api.deepseek.com/chat/completions | [DeepSeek](https://deepseek.com/) |
| 硅基流动 | ✅ | https://api.siliconflow.com/v1/chat/completions | [硅基流动](https://cloud.siliconflow.cn/i/VWOdVvvM) |
| OpenAI (GPT系列) | ✅ | https://api.openai.com/v1/chat/completions | [OpenAI](https://openai.com/api/) / [国内直连镜像站](https://app.requesty.ai/join?ref=d9bb6cf2) |
| 阿里云 (通义千问系列) | ✅ | https://dashscope.aliyuncs.com/compatible-mode/v1/chat/completions | [通义千问](https://bailian.console.aliyun.com/) |
| Google Gemini | ✅ | https://generativelanguage.googleapis.com/v1beta/openai/chat/completions | [Gemini](https://ai.google.dev/) / [国内直连镜像站](https://app.requesty.ai/join?ref=d9bb6cf2) |
| Grok | ✅ | https://api.x.ai/v1/chat/completions | [Grok](https://console.x.ai/) |
| 本地Ollama | ✅ | http://localhost:11434/api/chat | 因为跨域请求，需要设置环境变量 OLLAMA_ORIGINS = * |
| 字节跳动 (豆包系列) | ❓ |  | [豆包](https://www.volcengine.com/) |
| Anthropic Claude | ❓ |  | [Claude](https://console.anthropic.com/) |
| MiniMax | ❓ |  | [MiniMax](https://api.minimax.chat/) |


## 注意事项

- 插件功能**需要视频具有字幕**才能正常工作
- 需要配置大语言模型API密钥，模型能力越强，检测效果越好
- 使用付费API时请注意token消耗
- 检测结果会在控制台输出，格式为：`【VideoAdGuard】检测到广告片段: [开始时间 ~ 结束时间]`

## 技术原理

VideoAdGuard通过以下步骤检测视频中的植入广告：

1. 获取视频字幕内容
2. 提取视频标题和置顶评论
3. 将数据发送给大语言模型进行分析
4. 根据分析结果确定广告时间段
5. 在界面上显示跳过按钮

## 目录结构

```tree
VideoAdGuard
├── VideoAdGuard/      # 构建输出目录
├── _locales/          # i18n资源
├── docs/              # 文档目录
├── icons/             # 插件图标资源
├── src/               # 源代码目录
├── VideoAdGuard.Tampermonkey.js   # 油猴脚本版本
├── manifest.json      # Chrome扩展配置文件
├── package.json       # 项目依赖配置
├── tsconfig.json      # TypeScript配置
├── webpack.config.js  # Webpack构建配置
├── LICENSE            # 开源许可证
└── README.md          # 项目说明文档
```

## 自行构建

如果你想自行构建VideoAdGuard，可以按照以下步骤进行：

1. 克隆本仓库到本地：
   ```bash
   git clone https://github.com/Warma10032/VideoAdGuard.git
   cd VideoAdGuard
   ```
2. 安装依赖：
   ```bash
   npm install
   ```
3. 构建插件：
   ```bash
   npm run build
   ```
## 开源与贡献

本项目完全开源，欢迎贡献代码和提出建议：

- GitHub仓库：[https://github.com/Warma10032/VideoAdGuard](https://github.com/Warma10032/VideoAdGuard)
- 问题反馈：[GitHub Issues](https://github.com/Warma10032/VideoAdGuard/issues)
- 如遇任何插件不起作用问题，在提出Issues同时，附上浏览器(F12)控制台的错误日志/截图，以便我们更好地帮助你。
- ![与后端api通信的请求在这里查看](https://gcore.jsdelivr.net/gh/Warma10032/image@main/blog/插件管理界面.png)

### 贡献者
<a href="https://github.com/Warma10032/VideoAdGuard/contributors">
  <img src="https://contrib.rocks/image?repo=Warma10032/VideoAdGuard" /></a>

## 免责声明

本插件仅用于学习和研究目的，不得用于任何商业或非法用途。使用本插件所产生的一切后果，与作者和插件开发者无关。

## 许可证

本项目采用GPLv2许可证开源。

## Star History

<a href="https://www.star-history.com/#Warma10032/videoadguard&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=Warma10032/videoadguard&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=Warma10032/videoadguard&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=Warma10032/videoadguard&type=Date" />
 </picture>
</a>


