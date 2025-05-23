---
project: hexo-bilibili-card
stars: 45
description: |-
    一个 Hexo 插件，在你的文章中插入 b 站的视频卡片，样式模仿和借鉴自 b 站。A hexo plugin insert a bilibili card into your page or article.
url: https://github.com/maxchang3/hexo-bilibili-card
---

# hexo-bilibili-card

A hexo plugin insert a bilibili card into your page or article, some of css code is copy from bilibili.

一个Hexo插件，在你的文章中插入b站的视频卡片，样式模仿和借鉴自b站。

[![NPM](https://nodei.co/npm/hexo-bilibili-card.png)](https://nodei.co/npm/hexo-bilibili-card/)

> 目前此插件处于非积极维护中，可能需要修改代码样式以适配自己的网站。

> 此插件样式可能会受到站内样式污染，后期会改为 SVG 生成或 Web Component。短时间内获取大量图片信息可能会受到哔哩哔哩的访问限制。

> This plugin's CSS styles may be contaminated by the site's CSS styles, which will be changed to SVG generation at a later date. Fetching a large number of images/info over a period of time may be subject to access restrictions.


## Install 安装

```npm i hexo-bilibili-card```

## Preview 预览

You can click [here](https://zhangmaimai.com/2021/02/05/some-tests/) to see the preview website.

点击 [这里](https://zhangmaimai.com/2021/02/05/some-tests/) 看预览哦~

## Usage 使用

In your config file, insert follow codes:

在你的 config 文件中插入以下片段

```
{% bilicard your_video_id %}
```
`your_video_id` is the avid or bvid in Bilibili.

`your_video_id` 是b站的bv号或av号。

then you will get the card in your page.

然后你就可以看见文章中的卡片了。


## Config 配置

由于 b 站图片地址的跨域限制，因此需要配置图片代理，目前未找到大陆地区较为稳定的服务，默认使用的 `https://images.weserv.nl/?url=`，部分地区受到了 DNS 污染及反应过慢。建议参考 [rsstt-img-relay](https://github.com/Rongronggg9/rsstt-img-relay) 自建服务。

Due to the CORS strategy of Bilibili, you need to configure an image proxy to get the image correctly. Unfortunately, we haven’t found any stable image proxy in China Mainland yet. The default image proxy is provided by `https://images.weserv.nl/?url=`, which has DNS pollution in some areas and the response is too slow. We suggest referring to [rsstt-img-relay](https://github.com/Rongronggg9/rsstt-img-relay) to build your image proxy instead.

```yaml
hexo_bilibili_card:
    imageProxy: https://images.weserv.nl/?url=
```

