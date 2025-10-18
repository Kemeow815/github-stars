---
project: random-pictures
stars: 5
description: |-
    可以在 Vercel 一键免费部署的随机图 API
url: https://github.com/aizhiqian/random-pictures
---

# Random
在 Vercel 平台上部署一个具有分类功能的随机图片 API。通过这个 API，用户可以根据不同的分类获取随机图片链接，并且还可以从所有分类中随机获取一张图片。

## Demo

[https://random-pictures-iota.vercel.app](https://random-pictures-iota.vercel.app/)

## 部署

先 `Fork` 本项目，再登录 [Vercel](https://vercel.com/) 网站新建项目。

## 使用方法

在 `api` 目录下创建 `meinv.txt` 和 `dongman.txt` 文件，并在每个文件中添加图片链接，每行一个链接。例如：

> 当然你也可以自己创建新分类，只要文件后缀为`.txt`就行

**meinv.txt**：

```bash
https://example.com/meinv1.jpg
https://example.com/meinv2.jpg
```

**dongman.txt**：

```bash
https://example.com/dongman1.jpg
https://example.com/dongman2.jpg
```

## 路由

- `https://your-domain.vercel.app/` 显示项目的主页说明文档
- `https://your-domain.vercel.app/random` 获取所有 `.txt` 文件中的随机图片
- `https://your-domain.vercel.app/meinv` 获取 “meinv.txt” 文件中的随机图片
- `https://your-domain.vercel.app/dongman` 获取 “dongman.txt” 文件中的随机图片
- `https://your-domain.vercel.app/新分类` 获取 “新分类.txt” 文件中的随机图片

## 提示

主页说明文档中的新分类和链接自行修改，文件路径为 `./public/index.html`

主要就是修改下面的

```html
            <section>
                <h2>随机图片 API</h2>
                <p>欢迎使用随机图片 API！你可以通过以下路径获取随机图片：</p>
                <ul>
                    <li><strong>/random</strong> - 随机获取 <a>一张</a> 图片</li>
                    <li><strong>/meinv</strong> - 随机获取 <a>美女</a> 图片</li>
                    <li><strong>/dongman</strong> - 随机获取 <a>动漫</a> 图片</li>
                </ul>
                <p>示例：</p>
                <ul>
                    <li>
                        <a href="/random" target="_blank"
                            >https://random-pictures-iota.vercel.app/random</a
                        >
                    </li>
                    <li>
                        <a href="/meinv" target="_blank"
                            >https://random-pictures-iota.vercel.app/meinv</a
                        >
                    </li>
                    <li>
                        <a href="/dongman" target="_blank"
                            >https://random-pictures-iota.vercel.app/dongman</a
                        >
                    </li>
                </ul>
            </section>
```

## 许可证

[![license](https://img.shields.io/github/license/aizhiqian/random-pictures)](https://github.com/aizhiqian/random-pictures/blob/main/LICENSE)

random-pictures 使用 GPL-v3.0 协议开源，请遵守开源协议。

