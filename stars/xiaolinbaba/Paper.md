---
project: Paper
stars: 105
description: |-
    Paper - 纯前端 | 单 html 文件执行 | 轻量级 Markdown 微信公众号编辑器。定制属于每个人自己的微信公众号样式！
url: https://github.com/xiaolinbaba/Paper
---

<center>
    <img src="https://raw.githubusercontent.com/xiaolinbaba/Paper/1f20bc8ca05cb74e6739ce21774f0ae07449ab13/favicon.svg" style="width: 100px;">
</center>


# Paper - Markdown 微信公众号编辑器

> Paper 是一款轻量级纯前端，单 html 文件可执行的微信公众号 Markdown 编辑器。现代化三栏布局，实时 Markdown 预览，响应式设计，支持多张图片横向滑动查看，支持信息卡片；支持大部分 Markdown 语法 (数学公式和 Mermaid除外,请在发布区进行手工渲染)，支持信息卡片。预览区与微信公众号编辑器等宽，所见即所得。欢迎使用👏！支持cloudflare pagesb部署。**定制属于每个人自己的微信公众号样式！**

![paperview.png](/paperview.png)


## 快速使用

1. 访问在线版 [paper.thus.chat](https://paper.thus.chat)
2. 下载 `html` 单文件到本地 chrome 直接打开运行
3. 下载 `html` 单文件部署到自己的服务器使用
4. 下载 `html` 单文件用 `AI` 修改成自己喜欢的样式后食用 
5. 免费部署到自己的 cloudflare pages，通过自己的域名访问。
    ![cf.png](/cf.png)


## ✨ 编辑器简介

[Paper 轻量级微信公众号 Markdown 编辑器 - 微信公众号文章简介](https://mp.weixin.qq.com/s/nbFNsOKvynUzzePMfkw79w)

### 🎯 核心特性

**1. 现代化三栏布局**
- **编辑区**：支持 Markdown 语法编写
- **预览区**：实时渲染，578px 宽度（与微信公众号编辑器等宽）
- **发布区**：提供一键复制和相关工具链接

**2. 微信公众号完美适配**
- 预览区严格按照微信公众号标准，预览区与微信公众号编辑器等宽（578px）
- 支持的样式完全兼容微信公众号平台
- 一键复制后可直接粘贴到公众号编辑器

**3. 丰富的功能支持**
- ✅ 基础 Markdown 语法（标题、段落、列表、表格等）
- ✅ 代码语法高亮（Kimbie Light 主题，Mac 风格）
- ✅ 自定义信息卡片（`:::info` 语法）
- ✅ 横屏滑动幻灯片（`<![alt](url),![alt](url)>` 语法）
- ✅ 同步滚动（编辑器与预览区联动）
- ❌ 数学公式（不支持，请使用发布区链接手工渲染）
- ❌ Mermaid 图表（不支持，请使用发布区链接手工渲染）

### 🛠️ 技术实现

**前端技术栈：**
- 纯 HTML + CSS + JavaScript（无框架依赖）
- Showdown.js（Markdown 转 HTML）
- Highlight.js（代码语法高亮）
- Canvas-Confetti（复制成功动画效果）

**核心功能：**
- 实时 Markdown 渲染
- 行内样式注入（确保微信兼容性）
- 响应式设计

### 📁 项目结构

```
Paper/
├── index.html         # 主应用文件（单文件应用）
├── README.md          # 项目说明和使用示例
├── WechatSupport.md     # 微信公众号支持的HTML标签说明
└── favicon.svg       	# 网站图标
```

### 🎨 特色功能

**1. 信息卡片**
```markdown
:::info 提示标题
这里是卡片内容，支持**粗体**和*斜体*
:::
```

**2. 横屏滑动幻灯片**
```markdown
<![图片1](url1),![图片2](url2),![图片3](url3)>
```

**3. Mac 风格代码块**
- 自动添加 Mac 样式的三色圆点
- 支持多种编程语言语法高亮

### 🚀 使用场景

这个项目特别适合：
- 微信公众号内容创作者
- 单 Html 文件本地编辑器
- 追求简洁高效的 Markdown 编辑体验


## 特别鸣谢

Paper Markdown 编辑器的设计灵感参考了两个项目[jackywine](https://dqxf1izhlm.feishu.cn/wiki/RxfQwz2qXi06aqk17Hocfj5Gnk1), [md.doocs.org](https://md.doocs.org/)，欢迎大家关注这两个项目，也感谢两个项目作者的付出，谢谢。

最后，本项目花费了不少精力，如果可以，请关注我的微信公众号，或加群讨论 Markdown 编辑器相关知识。感谢您的支持！
![keeptouch.png](/keeptouch.png)

## 更新记录

### 20250702
- 优化三级标题的显示样式
- 更新Markdown语法查询链接
- 编辑区和预览区时间显示修订

### 20250608
- 增加了两个卡片样式，浅橙色卡片和浅蓝色卡片，通过 `:::orange`、`:::blue` 来引用
- bug 修复，冗余代码删除

