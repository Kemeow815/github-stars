---
project: blog-solitude
stars: 16
description: |-
    hexo博客+solitude主题，已经配置好的源码文件，所有插件都已安装，可以直接部署到 cf pages
url: https://github.com/yutianqq/blog-solitude
---

## 部署到 cloudflare pages

基本流程如下：

- 新建一个 pages
- 链接 github
- 导入刚刚生成的仓库，例如我的是
- 重点 1：构建命令填 npm run build
- 重点 2：构建输出填 public
- 其他留空，点击部署
- 部署完成后等待两分钟，点击 cf 分配的域名访问一下博客

如果没有问题，在 pages 设置中绑定自定义域，就可以使用自己的域名进行访问了

## 如何设置博客

- `_config.yml`文件：设置博客的基本信息，如网站名称、作者等
- `_config.solitude.yml`文件：主题配置文件，参照[官方文档](https://solitude.js.org/zh/)进行配置
- `source\_data`：页面文件的内容，可自定义

## 如何发布博文

- `source\_posts`：博客文章文件夹，直接在仓库里写`md`文档，文档头部带上`Front Matter`信息，提交即可发布到博客

Front Matter 写法示例
```
---
title: 测试
data: 2024-10-01  # 文章发布时间
updated: 2024-10-05 # 最后更新时间
description: 文章摘要或描述
cover: 文章封面图，填写url图片外链
reprint: false为原创，true为转载
comment: true为允许评论，默认允许，false为关闭评论
---
```

## Front Matter 是什么？

Front Matter 是 Markdown 的一种特殊语法，用于定义页面的元数据。

## 主题可使用的 Front Matter 属性

提示

不需要在页面中全部添加，有些属性是必须的，有些是可选的。

|属性|值类型|解释|
|---|---|---|
|title|string|必需 页面标题|
|date|datetime|必需 页面创建日期|
|type|string|必需 关于、友情链接、朋友圈、即刻、工具箱页面需要配置|
|updated|datetime|可选 页面更新日期|
|desc|string|可选 页面描述|
|description|string|可选 页面描述|
|aside|boolean|可选 是否开启侧边栏（默认 true）|
|comment|boolean|可选 显示页面评论模块 (默认 true)|
|cover|string|可选 页面顶部图片 URL|
|reprint|boolean|可选 版权（默认为原创）为 true 时为转载|
|katex|boolean|可选 显示 katex(默认 false)|
|locate|string|可选 文章创作地点|
|leftend|string|可选 banner 底部左侧文字|
|rightend|string|可选 banner 底部右侧文字|
|rightbtn|string|可选 banner 底部右侧按钮文字|
|rightbtnlink|string|可选 banner 底部右侧按钮跳转链接|
|container|boolean|可选 是否开启容器（默认 true）|
|author|string|可选 文章作者|
|avatar|string|可选 文章作者头像 URL|

**自定义拥有 banner 图的页面**

markdown

```
---
title: 测试
type: banner
container: true
---
```

>注意  
>如果只需要普通的实现`banner`效果，可以不写`container`属性

