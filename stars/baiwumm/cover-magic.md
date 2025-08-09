---
project: cover-magic
stars: 10
description: |-
    一个专业的封面设计工具，支持实时预览和高质量导出
url: https://github.com/baiwumm/cover-magic
---

<div align="center">
  <img alt="Cover Magic Logo" src="./public/logo.svg" width="120"/>
  <h1>Cover Magic - 专业的封面设计工具</h1>
  <p><strong>一款专业的封面设计工具，支持实时预览和高质量导出，帮助您轻松创建精美的封面图像</strong></p>
  
  <p>
  <img src="https://img.shields.io/github/stars/baiwumm/cover-magic?style=flat-square&logo=github" alt="GitHub stars"/>
    <img src="https://img.shields.io/badge/Vue-v3.5.17-brightgreen" alt="Vue.js"/>
    <img src="https://img.shields.io/badge/Vite-v7.0.4-yellow" alt="Vite.js"/>
    <img src="https://img.shields.io/badge/Tailwind_CSS-4.1.11-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS"/>
    <img src="https://img.shields.io/badge/License-MIT-green" alt="License MIT" />
  </p>
</div>

## 🌟 功能特点

### 🎨 背景设计
- 自定义纯色背景
- 上传自定义图片
- 多方向渐变背景
- 背景模糊效果调整

### 🖼️ 内容编辑
- 丰富的图标库（基于Iconify）
- 自定义标题文本
- 字体样式调整（粗体、斜体、大写）
- 水印保护功能

### 🌓 主题模式
- 多种精美主题
- 一键主题切换
- 个性化主题定制

### 📤 导出选项
- 多种格式导出（PNG、JPEG、WebP）
- 自定义尺寸
- 高质量图像
- 随机文件名生成

### 🛠️ 本地开发

```bash
# 1. 克隆项目
git clone git@github.com:baiwumm/cover-magic.git

# 2. 进入项目目录
cd cover-magic

# 3. 安装依赖
pnpm install

# 4. 启动开发服务器
pnpm dev

# 5. 打开浏览器访问
# http://localhost:5173
```

## 🛠️ 技术栈

- **前端框架**: [Vue 3](https://vuejs.org/)
- **构建工具**: [Vite](https://vitejs.dev/)
- **语言**: [TypeScript](https://www.typescriptlang.org/)
- **UI组件库**: [Naive UI](https://www.naiveui.com/)
- **CSS框架**: [TailwindCSS](https://tailwindcss.com/)
- **图标库**: [Iconify](https://iconify.design/)
- **图像处理**: [html2canvas](https://html2canvas.hertzen.com/)

## 📝 项目结构

```
cover-magic/
├── public/             # 静态资源
├── src/
│   ├── components/     # 组件
│   │   ├── BackgroundPanel.vue    # 背景设置面板
│   │   ├── DefaultTheme.vue       # 默认主题组件
│   │   ├── ExportPanel.vue        # 导出设置面板
│   │   ├── FooterPanel.vue        # 底部版权组件
│   │   ├── GithubCorner.vue       # GitHub角标组件
│   │   ├── HeaderPanel.vue        # 顶部标题栏
│   │   ├── IconPanel.vue          # 图标设置面板
│   │   ├── LoadingScreen.vue      # 加载动画组件
│   │   ├── ThemeSelector.vue      # 主题选择器组件
│   │   ├── TitlePanel.vue         # 标题设置面板
│   │   └── WatermarkPanel.vue     # 水印设置面板
│   ├── lib/            # 工具库
│   │   ├── constant.ts # 常量定义
│   │   └── type.ts     # 类型定义
│   ├── App.vue         # 应用入口组件
│   └── main.ts         # 应用入口文件
├── .env                # 环境变量
├── index.html          # HTML模板
├── package.json        # 项目配置
├── tsconfig.json       # TypeScript配置
└── vite.config.ts      # Vite配置
```

## 🔧 配置说明

项目使用`.env`文件进行基本配置：

```
# 项目名称
VITE_APP_SITE_NAME = 'Cover Magic'
# 页面描述
VITE_APP_SITE_DESCRIPTION = "专业的封面设计工具，支持实时预览和高质量导出"
# 关键词
VITE_APP_SITE_KEYWORDS = "封面设计,封面,设计,cover,designer"
```

## 📄 许可证

本项目采用 [MIT](LICENSE) 许可证。

## 👨‍💻 作者

- **姓名**: baiwumm
- **邮箱**: [me@baiwumm.com](mailto:me@baiwumm.com)
- **博客**: [https://baiwumm.com](https://baiwumm.com)
- **GitHub**: [https://github.com/baiwumm](https://github.com/baiwumm)

## 🔗 相关链接

- **问题反馈**: [https://github.com/baiwumm/cover-magic/issues](https://github.com/baiwumm/cover-magic/issues)
- **项目仓库**: [https://github.com/baiwumm/cover-magic](https://github.com/baiwumm/cover-magic)

## ⭐ Star History

<div align="center">
  <img src="https://api.star-history.com/svg?repos=baiwumm/cover-magic&type=Date" alt="Star History Chart" width="600"/>
</div>

---

<div align="center">
  <p>如果这个项目对你有帮助，请给它一个 ⭐️</p>
  <p>Made with ❤️ by <a href="https://github.com/baiwumm">@baiwumm</a></p>
  <p>© 2025 Cover Magic. All rights reserved.</p>
</div>

