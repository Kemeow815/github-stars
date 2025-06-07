---
project: VitePress_butterfly
stars: 5
description: |-
    Butterfly theme of VitePress。一个基于Vitepress的仿Butterfly卡片式博客主题+脚本工具。
url: https://github.com/57Darling02/VitePress_butterfly
---

---
title: VitePress-Butterfly 主题 README
date: 2024-05-20
author: 57Darling02
---

# VitePress-Butterfly 主题

基于VitePress和Element Plus的卡片式仿butterfly主题。

示例站点：[模板站点](https://vitepress.57d02.cn/)

[57Darling02's Blog](https://57darling02.github.io/)

##  特色

- 静态博客，不需要服务器也能有自己的个人网站
- vitepress完善的工作流自动构建，只需要首次配置，发文章只需要简单三条命令（见脚本deploy2github.sh）
- vite的静态资源自动优化，不需要图床也能够插入图片

##  快速开始（简单部署）

### **1. Fork 仓库并克隆到本地**

点击 GitHub 上的**star**和 **Fork** 按钮，给你的仓库起名（如your-username.github.io），然后克隆到本地：

```bash
git clone https://github.com/your-username/your-username.github.io.git
cd VitePress_butterfly
```

### 2. 修改配置

将网站变成你的形状😤修改 site_config.ts进行主题配置信息，更改首页背景图、网站名称、侧边栏个人信息等等。具体配置见下文。

### 3.写一篇文章

在posts/文件夹中创建helloworld.md,内容如下：

```markdown
---
title: 文章标题
date: 2024-03-20
author: 作者
layout: doc # 这行不写也行，涉及到自定义页面才会涉及
---

# Hello World!
这是一篇文章，蛤蛤蛤！！！外币巴伯....

```

 **上传到GitHub**

**推荐使用博客管理脚本.sh**

或者手动上传

```
git add . && git commit -m "update" && git push origin main
```

> [!WARNING]
> 使用 -f 强制上传会导致最后更新时间失效。

### （可选，如果你仅仅使用默认样式，请跳过）预览文章

确保你有nodejs环境后，在命令行完成：

##### 安装依赖

```cmd
npm install
```

##### 打包

```
npm run docs:build
```

##### 预览
```
npm run preview
```



### 4.部署（二选一）

##### 工作流（推荐）

如果你是直接复刻仓库，那么完全不需要，我已经帮给你写好了。如果你非要自己搞，请参考vitepress官方文档。工作流将会在你push文件时触发，仓库上方点击actions查看部署进度。

这种方式能够：

- 只需要写文章，push内容。github page自动构建后救恩那个在你的网站看到更新的内容

##### 本地构建

> 该方式需要你手动打包，并让github部署,类似hexo

1. 构建生产版本

```bash
npm run build
```
>  注意：这里build将打包到最外边docs文件夹中

2. 上传到github

3. 配置GitHub Page，选择docs

![1741082221235](https://resource-un4.pages.dev/article/1741082221235.png)

4. 后续每次修改配置和文章，都要打包构建并上传到github

## 主题更新

主题更新前，请先完成一次上传到github，确保回到github云端的最新仓库能够避免损失。

#### 直接更新（小白用）：通过 博客管理脚本.sh 完成

请移步最新仓库获得这份脚本。

```
git fetch upstream
git checkout upstream/main -- 博客管理脚本.sh
git add 博客管理脚本.sh
```



> [!WARNING]
> 这将仅保留 "posts/" "site_config.ts"  "public/"  ".github/"，其余文件将被覆盖。如果只修改了以上文件，简单更新即可。如果不小心出现覆盖，请使用git reset --hard origin/main 回到当前已经部署再网页上的状态。


> [!IMPORTANT]
> 注意，主题更新后，请查看.vitepress目录中的模板site_config_template.ts与你的配置文件区别，完成配置。

更新的文件会拉到本地，请确认无误后，上传至你的github仓库触发更新.

#### 手动更新，同步仓库并合并冲突

## 配置指南

修改根目录下的 site_config.ts进行主题配置：内容可参考.vitepress目录中的模板site_config_template.ts。[VitePress_butterfly/.vitepress/site_config_template.ts](https://github.com/57Darling02/VitePress_butterfly/blob/main/.vitepress/site_config_template.ts)可将其重命名复制到根目录下的 site_config.ts。

> 注意，修改模板没什么效果，还可能导致你更新主题时面临合并问题。

### 目录结构

```plainText
Blog/                   # 项目根目录
├── .vitepress/         # 主题组件 不会为这部分提供文档 (一般不用动)
│   ├── theme/
│   ├── site_config.ts  # 模板文件，可以复制到根目录下修改使用          
│   ├── config.mjs   
│   ├── index.js
│   └── ...   
├── site_config.ts     # 站点配置 自定义的配置，主要修改这个文件来配置站点信息
├── posts/             # Markdown文章 文章放这里
├── public/            # 静态资源 例如背景图片，例如 public/a.png 则配置中对应 /a.png
└── package.json       # 依赖配置 (一般不用动)
```
### 文章规范

图片使用相对路径即可。建议使用typra编辑器，可以方便的插入相对路径图片

```markdown
---
title: 文章标题
date: 2024-03-20
author: 作者
cover: url... 
layout: doc # 可选布局
---
```
贡献
欢迎贡献代码和反馈问题。


