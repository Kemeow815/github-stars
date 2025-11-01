---
project: VideoAdGuard
stars: 672
description: |-
    哔哩哔哩浏览器插件：基于大语言模型，对B站视频中的植入广告进行检测。一键跳过视频中的植入/口播广告。
url: https://github.com/Warma10032/VideoAdGuard
---

# VideoAdGuard - B站视频植入广告检测器

VideoAdGuard 是一个基于大语言模型的B站视频植入广告检测工具，能够自动识别B站视频中的植入广告内容，并提供跳过广告的功能。

如果你觉得这个插件有用，请给项目点个Star⭐支持一下！

[演示视频](https://www.bilibili.com/video/BV1UGeBztE2T/)

<div align="center">
  <img src="./icons/icon128.png" alt="VideoAdGuard Logo">

<!-- 浏览器插件下载 -->

<div style="margin-top: 20px;">
    <a href="https://microsoftedge.microsoft.com/addons/detail/videoadguard/mpfelbgplaolpbjmdbjjajonkmmgekgo/" target="_blank">
      <img src="https://img.shields.io/badge/Microsoft%20Edge-0078D4?style=for-the-badge&logo=Microsoft-edge&logoColor=white" alt="Edge插件下载">
    </a>
    <a href="https://chromewebstore.google.com/detail/videoadguard/nmkkpflniidbbodhjhjaijadbccidbgi/" target="_blank">
      <img src="https://img.shields.io/badge/Google%20Chrome-EEDD82?style=for-the-badge&logo=GoogleChrome&logoColor=red" alt="Chrome插件下载">
    </a>
    <a href="https://addons.mozilla.org/zh-CN/firefox/addon/videoadguard/" target="_blank">
      <img src="https://img.shields.io/badge/Firefox-FF7139?style=for-the-badge&logo=Firefox-Browser&logoColor=white" alt="Firefox插件下载">
    </a>
  </div>
</div>

## News

- v1.2.8 提供Groq代理服务
- v1.2.7 适配Firefox浏览器
- v1.2.6 支持 glm-4.5 系列模型，适配 Chrome浏览器
- v1.2.5 优化缓存机制；优化av号处理
- v1.2.4 新增限制模式，仅在有商品链接时进行识别；优化界面
- v1.2.3 新增音频识别功能，支持无字幕视频检测；新增广告检测结果缓存机制
- v1.2.2 新增关闭插件开关，优化界面，优化广告判断逻辑
- v1.2.1 支持自定义UP白名单
- v1.2.0 支持自动跳过
- v1.1.3 支持本地Ollama模型

## 功能特点

- 🎯 **精准识别**：采用大语言模型分析视频字幕，准确定位植入广告内容
- 🎵 **音频识别**：支持无字幕视频的音频识别检测，使用免费的Groq服务商（v1.2.3新增）
- 🚀 **便捷操作**：检测到广告后自动显示跳过按钮，一键跳过广告片段
- 🔄 **自动跳过**：支持自动跳过已识别的广告内容（v1.2.0新增）
- 💾 **智能缓存**：本地缓存检测结果，大幅提升重复访问速度（v1.2.3新增）
- 🌈 **广泛兼容**：支持多种主流浏览器，包括Edge、Chrome等
- ⚙️ **灵活定制**：支持多种AI模型接入，包括智谱AI、OpenAI、DeepSeek等
- 🏠 **本地部署**：支持本地Ollama模型，保护隐私数据（v1.1.3新增）

## 安装方法

### 浏览器插件版（推荐）

点击上方对应浏览器的图标即可下载安装：

- **Edge浏览器**：[Edge插件下载](https://microsoftedge.microsoft.com/addons/detail/videoadguard/mpfelbgplaolpbjmdbjjajonkmmgekgo/)
- **Chrome浏览器**：[Chrome插件下载](https://chromewebstore.google.com/detail/videoadguard/nmkkpflniidbbodhjhjaijadbccidbgi/)
- **Firefox浏览器**：[Firefox插件下载](https://addons.mozilla.org/zh-CN/firefox/addon/videoadguard/)

### 油猴脚本版

**注意**：油猴版本更新不及时，如果是chromium内核浏览器推荐采用插件版

1. 安装[篡改猴插件](https://www.tampermonkey.net/)
2. 从[GreasyFork](https://greasyfork.org/zh-CN/scripts/531743-b%E7%AB%99%E8%A7%86%E9%A2%91%E6%A4%8D%E5%85%A5%E5%B9%BF%E5%91%8A%E6%A3%80%E6%B5%8B%E5%99%A8-videoadguard/)安装脚本

## 使用方法

1. **浏览器插件版**：安装完成后，点击插件图标完成设置

   ![](https://imgbed.xiaobaozi.cn/file/blog/VideoAdGuard_popup1.webp)
2. **油猴脚本版**：安装完成后，进入B站视频页面，点击右下角齿轮图标进行设置

   ![](https://imgbed.xiaobaozi.cn/file/blog/VideoAdGuard2.webp)
3. 设置API密钥和模型（详见下方API设置说明）
4. 打开任意带有字幕的B站视频，插件会自动检测广告内容
5. 当检测到广告时，会在视频播放器右下角显示"跳过广告"按钮

## API设置说明

本插件需要配置大语言模型API才能正常工作。检测能力与大模型能力强相关，推荐使用性能更强的大模型。

### 大语言模型API（必需）

测试不同大模型的该项目上的效果，可选择 302.AI，立即[注册](https://share.302.ai/ckUgCA)获取$1赠金

- **API地址**：`https://api.302.ai/v1/chat/completions`
- **模型名称**：[模型列表](https://302.ai/product/list?cate=api&tag=%E8%AF%AD%E8%A8%80%E5%A4%A7%E6%A8%A1%E5%9E%8B)
- **API密钥**：需要在[302.AI](https://302.ai/apis/list)注册并获取（输入邀请码 `ckUgCA`  获取$1赠金）

免费体验可选择 智谱AI glm-4.5-flash 模型

- **API地址**：`https://open.bigmodel.cn/api/paas/v4/chat/completions`
- **模型名称**：`glm-4.5-flash`
- **API密钥**：需要在[智谱AI平台](https://bigmodel.cn/usercenter/proj-mgmt/apikeys)注册并获取

插件兼容几乎所有大语言模型。目前我们已经测试了部分模型，但还需要更多用户的测试反馈。如果您使用了下表中的模型，请通过GitHub Issues告诉我们您的使用体验，帮助我们完善兼容性列表。

| API集成平台 | 测试结果 | API密钥官网                                      |
| ----------- | -------- | ------------------------------------------------ |
| 302.AI      | ✅       | [302.AI](https://share.302.ai/ckUgCA)               |
| 硅基流动    | ✅       | [硅基流动](https://cloud.siliconflow.cn/i/VWOdVvvM) |
| 云雾API     | ✅       | [云雾API](https://yunwu.ai/register?aff=btu9)       |

| 模型名称         | 测试结果 | API密钥官网                                             |
| ---------------- | -------- | ------------------------------------------------------- |
| GLM              | ✅       | [智谱AI](https://bigmodel.cn/usercenter/proj-mgmt/apikeys) |
| DeepSeek         | ✅       | [DeepSeek](https://platform.deepseek.com/api_keys)         |
| OpenAI           | ✅       | [OpenAI](https://openai.com/api/)                          |
| 通义千问         | ✅       | [阿里云](https://bailian.console.aliyun.com/)              |
| Gemini           | ✅       | [Gemini](https://ai.google.dev/)                           |
| Grok             | ✅       | [Grok](https://console.x.ai/)                              |
| Anthropic Claude | ❓       | [Claude](https://console.anthropic.com/)                   |
| MiniMax          | ❓       | [MiniMax](https://api.minimax.chat/)                       |
| 豆包             | ❓       | [火山引擎](https://www.volcengine.com/)                    |

| 本地服务 | 测试结果 | 注意事项                                          |
| -------- | -------- | ------------------------------------------------- |
| Ollama   | ✅       | 因为跨域请求，需要设置环境变量 OLLAMA_ORIGINS = * |

### 音频识别API（可选）

- **用途**：用于无字幕视频的音频识别功能
- **推荐服务**：目前只支持Groq（免费Whisper模型）
- **API密钥获取**：在[Groq平台](https://console.groq.com/keys)注册并获取
- **注意**：如果要使用Groq AP，需要非国内（包括港澳台）的网络环境

## 注意事项

- **字幕检测**：优先使用视频字幕进行检测，准确度更高
- **音频识别**：无字幕视频将自动启用音频识别功能（v1.2.3新增）
- **API配置**：需要配置大语言模型API密钥，模型能力越强，检测效果越好
- **音频识别API**：使用音频识别功能需要额外配置Groq API密钥
- **费用提醒**：使用付费API时请注意token消耗和音频识别费用
- **缓存机制**：检测结果会自动缓存24小时，提升重复访问速度
- **调试信息**：众多调试信息会在控制台输出，遇到错误时可以查看控制台

## 技术原理

VideoAdGuard通过以下步骤检测视频中的植入广告

### 字幕检测模式（默认）

1. 获取视频字幕内容
2. 提取视频标题和置顶评论
3. 将数据发送给大语言模型进行分析
4. 根据分析结果确定广告时间段
5. 缓存检测结果到本地存储
6. 在界面上显示跳过按钮

### 音频识别模式

1. 当视频无字幕时，自动下载视频音频流
2. 使用Groq Whisper API进行语音识别
3. 将识别结果转换为文本格式
4. 后续流程与字幕检测模式相同

### 智能缓存机制

- 本地缓存检测结果，避免重复分析
- 缓存有效期为24小时，自动清理过期数据
- 大幅提升重复访问视频的检测速度

## 目录结构

```tree
VideoAdGuard
├── builds/                        # 构建产物（按浏览器区分）
│   ├── chrome/                    # Chrome 打包目录
│   └── firefox/                   # Firefox 打包目录
├── src/                           # 源代码目录
│   ├── services/                  # 业务逻辑与平台适配
│   ├── types/                     # 类型定义
│   └── utils/                     # 工具函数
├── manifests/                     # 浏览器清单文件
│   ├── manifest-chrome.json       # Chrome 清单
│   └── manifest-firefox.json      # Firefox 清单
├── _locales/                      # i18n 资源
├── icons/                         # 插件图标资源
├── docs/                          # 文档与站点
├── scripts/                       # 构建与辅助脚本
│   └── build.js
├── VideoAdGuard.Tampermonkey.js   # 油猴脚本版本
├── webpack.config.js              # Webpack 构建配置
├── tsconfig.json                  # TypeScript 配置
├── package.json                   # 项目依赖与脚本
├── LICENSE                        # 开源许可证
└── README.md                      # 项目说明文档
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
- ![与后端api通信的请求在这里查看](https://imgbed.xiaobaozi.cn/file/blog/插件管理界面.webp)

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

