---
project: Rin
stars: 7
description: |-
    我的博客
url: https://github.com/liuran001/Rin
---

# Rin 自用修改版

本仓库为 [笨蛋小破站](https://blog.obdo.cc) 的源代码

由于本人的代码写的依托答辩所以强烈不建议你使用我的版本

原仓库: https://github.com/OXeu/Rin

Rin 博客简易部署教程 — 笨蛋小破站: https://blog.obdo.cc/feed/10

## 相较官方版本的修改

1. 在文章中和页脚加入访问计数  

2. 友链申请页添加站长信息  
因为是从变量中获取站点链接，所以你需要先在 Cloudflare Pages 的环境变量中新增一个 `URL` 值为自己的站点链接

3. 加入音乐播放器  
在页面底部加入 MetingJS 播放器，歌单自己在 [App.tsx](/client/src/App.tsx) 改  

4. 将站点描述修改为一言  

5. 字体更换为 MiSans  

6. 增加 Live2D 看板娘  

注：上方所调用的所有 API 均为本人自托管，你也可以直接加到自己的站点中使用  
- 计数: https://api.obdo.cc/count  
- MetingAPI: https://api.obdo.cc/meting  
- 一言: https://api.obdo.cc/hitokoto  
- 看板娘: https://api.obdo.cc/live2d.js  

**由于 Rin 是一个刚起步的项目，功能方面存在着很多不足，或许这里的功能今后都会在官方版本中实现，这里只是因为自己需要所以就改了**  
~~因为代码基本上都是gpt写的，实现逻辑一个比一个屎，所以不考虑给官方提pr了~~

# Rin

English | [简体中文](./README_zh_CN.md)

![Cover](https://repository-images.githubusercontent.com/803866357/958bc2c1-1703-4127-920c-853291495bdc)

![GitHub commit activity](https://img.shields.io/github/commit-activity/w/OXeu/Rin?style=for-the-badge)
![GitHub branch check runs](https://img.shields.io/github/check-runs/OXeu/Rin/main?style=for-the-badge)
![GitHub top language](https://img.shields.io/github/languages/top/OXeu/Rin?style=for-the-badge)
![GitHub License](https://img.shields.io/github/license/OXeu/Rin?style=for-the-badge)
![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/OXeu/Rin/deploy.yaml?style=for-the-badge)

# Introduction

Rin is a blog based on Cloudflare Pages + Workers + D1 + R2. It does not require a server to deploy. It can be deployed just with a domain name that resolves to Cloudflare.

## Demo

[xeu.life](https://xeu.life)

## Features
1. Support GitHub OAuth login. By default, the first logged-in user has management privileges, and other users are ordinary users
2. Support article writing and editing
3. Support local real-time saving of modifications/edits to any article without interfering between multiple articles
4. Support setting it as visible only to yourself, which can serve as a draft box for cloud synchronization or record more private content
5. Support dragging/pasting uploaded images to a bucket that supports the S3 protocol and generating links
6. Support setting article aliases, and access articles through links such as https://xeu.life/about
7. Support articles not being listed in the homepage list
8. Support adding links of friends' blog, and the backend regularly checks and updates the accessible status of links every 20 minutes
9. Support replying to comment articles/deleting comments
10. Support sending comment notifications through Webhook
11. Support automatic identification of the first picture in the article and display it as the header image in the article list
12. Support inputting tag texts such as "#Blog #Cloudflare" and automatically parsing them into tags
13. For more features, please refer to https://xeu.life

# Documentation
1. [Deployment Documentation](./docs/DEPLOY.md)

2. [Environment Variables List](./docs/ENV.md)

3. [SEO Optimization Configuration](./docs/SEO.md)

4. [Contribution Guide](./CONTRIBUTING.md)

5. [Code of Conduct](./CODE_OF_CONDUCT.md)

## Star History

<a href="https://star-history.com/#OXeu/Rin&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=OXeu/Rin&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=OXeu/Rin&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=OXeu/Rin&type=Date" />
 </picture>
</a>

# License
```
MIT License

Copyright (c) 2024 Xeu

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

