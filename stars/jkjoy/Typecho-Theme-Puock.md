---
project: Typecho-Theme-Puock
stars: 3
description: |-
    移植开源项目 Licoy/wordpress-theme-puock
url: https://github.com/jkjoy/Typecho-Theme-Puock
---

## 说明

### 主题介绍

源主题为`wordpress`主题`puock`,现移植到`Typecho`平台。

### 主题特点
- 主题简洁，适合个人博客使用
- 支持`Typecho`的所有功能

### 主题预览

![主题预览](/screenshot.png)

### 使用说明

1. 将主题文件夹放入`Typecho`的`usr/themes`目录下。
2. 在后台管理界面启用该主题。
3. 根据需要自定义主题设置。
4. 主题部分功能需要安装插件`Puock`。项目地址: [Puock Plugin](https://github.com/jkjoy/typecho-plugin-puock)
5. 友情链接功能需要使用插件`Links`。项目地址: [Links Plugin](https://file.imsun.org/upload/2025-06/Links-1.2.7.zip),首页友情链接需要在`友链分类`中添加分类`home`。

### 更新

- 2025.07.05
  - 1.1.3 
    - 兼容typecho 1.3.0版本
    - 修复pjax黑暗模式下闪烁问题
    - 修复说说页面的pjax加载问题
    - 修复上一篇与下一篇文章的链接
    - 增加归属地显示设置
    - 增加系统显示设置
    - 增加浏览器信息显示设置
    - 修复pjax模式下的404跳转

- 2025.07.07 表情短代码解析集成
  - 1.1.5
  
   - 将表情短代码（如 :smile:）自动解析为图片表情，集成到主题评论内容输出中。

- 2025.07.08

  - 1.1.6
  
   - 修复头像区域背景的bug
   - 优化php8.3兼容性

  - 1.1.8

   - 优化github链接的正则表达式，只解析主仓库链接（如 https://github.com/用户名/仓库名），不再解析子路径（如 /tree/、/blob/ 等）为卡片。
   - 实现文章内容图片懒加载，自动将常见图片格式（jpg、jpeg、png、webp）的<img>标签替换为带懒加载属性的格式。
   - 修正getPostCover函数，确保只从原始内容中提取第一张真实图片地址，不受懒加载替换影响，避免首页首图变成load.svg。

   - 新增支持[success]、[primary]、[danger]、[warning]、[info]、[dark]等alert类短代码，自动渲染为对应的Bootstrap风格提示框。
   - 新增支持[collapse title='xxx']内容[/collapse]折叠面板短代码，自动渲染为带唯一ID的Bootstrap折叠结构。
   - 新增支持[download file='xxx.zip' size='12MB']文件地址[/download]下载短代码，自动渲染为带文件名、大小、声明和下载地址的下载信息块。
   - 新增支持[reply]隐藏内容[/reply]回复可见短代码，未满足条件时前端显示提示，已评论且审核通过后显示隐藏内容。

  - 1.2.0

   - 新增支持首页登录

- 2025.08.02

  - 1.2.2

    - 增加侧边栏显示的全局开关
    - 修复代码块中的短代码解析问题
    - 新增一个随机文章阅读的独立页面

- 2025.08.03

  - 1.2.3

    - 修复随机页面在 PJAX 模式下的缓存问题
    - 在随机页面添加缓存控制头，防止 PJAX 缓存
    - 在 JavaScript 中添加随机页面检测，强制刷新确保获取新文章
    - 修复后端登录验证问题，确保密码错误时返回正确的错误信息
    - 重新设计随机页面模板，添加完整的页面结构和加载动画
    - 修复随机页面重定向问题，使用 JavaScript 跳转避免缓存
    - 修复随机页面 JavaScript 错误，移除不存在的 InstantClick.preload 方法调用
    - 优化随机页面跳转逻辑，确保在 PJAX 模式下也能正常自动跳转
