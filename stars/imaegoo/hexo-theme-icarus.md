---
project: hexo-theme-icarus
stars: 93
description: |-
    魔改版 Hexo Icarus 主题
url: https://github.com/imaegoo/hexo-theme-icarus
---

## 🔷 提示 Tip

> 本 Hexo 主题为 Icarus 个人魔改版，官方主题请移步[ppoffice/hexo-theme-icarus](https://github.com/ppoffice/hexo-theme-icarus)。<br>
> This is an Hexo theme Icarus for personal use, the official one is [ppoffice/hexo-theme-icarus](https://github.com/ppoffice/hexo-theme-icarus).

> 本魔改主题不提供文档（因为存在大量硬编码），代码可以随意参考，有使用上的疑问可在 [Issue](https://github.com/imaegoo/hexo-theme-icarus/issues) 中提问，也可[在博客中留言](https://www.imaegoo.com/messages/)。<br>
> No documentations are provided, codes are free to use, if you have any question, please [open an issue](https://github.com/imaegoo/hexo-theme-icarus/issues) or [leave me a message](https://www.imaegoo.com/messages/).

## 🔷 用法 Usage

```sh
npm i -g hexo
mkdir blog
cd blog
hexo init --no-clone
git clone https://github.com/imaegoo/hexo-theme-icarus.git themes/icarus
hexo config theme icarus
```

## 🔷 配置 Config

以下是 iMaeGoo 自用配置，供您参考。

<details>
<summary>点击展开</summary>

```yml
# Version of the configuration file
version: 5.1.0
# Icarus theme variant, can be "default" or "cyberpunk"
variant: default
# Path or URL to the website's logo
logo:
    light: /images/logo.png
    dark: /images/logo-dark.png
# Page metadata configurations
head:
    # URL or path to the website's icon
    favicon: /favicon.ico
    # Canonical URL of the current page
    #canonical_url:
    # Open Graph metadata
    # https://hexo.io/docs/helpers.html#open-graph
    #open_graph:
        # Page title (og:title) (optional)
        # You should leave this blank for most of the time
        #title:
        # Page type (og:type) (optional)
        # You should leave this blank for most of the time
        #type: blog
        # Page URL (og:url) (optional)
        # You should leave this blank for most of the time
        #url:
        # Page cover (og:image) (optional) Default to the Open Graph image or thumbnail of the page
        # You should leave this blank for most of the time
        #image:
        # Site name (og:site_name) (optional)
        # You should leave this blank for most of the time
        #site_name:
        # Page author (article:author) (optional)
        # You should leave this blank for most of the time
        #author:
        # Page description (og:description) (optional)
        # You should leave this blank for most of the time
        #description:
        # Twitter card type (twitter:card)
        #twitter_card:
        # Twitter ID (twitter:creator)
        #twitter_id:
        # Twitter ID (twitter:creator)
        #twitter_site:
        # Google+ profile link (deprecated)
        #google_plus:
        # Facebook admin ID
        #fb_admins:
        # Facebook App ID
        #fb_app_id:
    # Structured data of the page
    # https://developers.google.com/search/docs/guides/intro-structured-data
    structured_data:
        # Page title (optional)
        # You should leave this blank for most of the time
        title:
        # Page description (optional)
        # You should leave this blank for most of the time
        description:
        # Page URL (optional)
        # You should leave this blank for most of the time
        url:
        # Page author (article:author) (optional)
        # You should leave this blank for most of the time
        author:
        # Page images (optional) Default to the Open Graph image or thumbnail of the page
        # You should leave this blank for most of the time
        image:
    # Additional HTML meta tags in an array
    meta:
        # Meta tag specified in <attribute>=<value> style
        # E.g., name=theme-color;content=#123456 => <meta name="theme-color" content="#123456">
        - ''
    # URL or path to the website's RSS atom.xml
    rss: /atom.xml
# Page top navigation bar configurations
navbar:
    # Naviagtion menu items
    menu:
        首页: /
        时间轴: /archives/
        分类: /categories/
        标签: /tags/
        网盘: 'https://imaegoo.azurewebsites.net'
        留言板: /messages/
        友情链接: /friends/
        关于: /about/
    # Links to be shown on the right of the navigation bar
    links:
        # Admin:
        #     icon: fas fa-cog
        #     url: 'https://admin.imaegoo.com'
# Page footer configurations
footer:
    # Links to be shown on the right of the footer section
    links:
        Creative Commons:
            icon: fab fa-creative-commons
            url: 'https://creativecommons.org/'
        Attribution 4.0 International:
            icon: fab fa-creative-commons-by
            url: 'https://creativecommons.org/licenses/by/4.0/deed.zh'
    copyright: '<a href="https://beian.mps.gov.cn/#/query/webSearch?code=41010502005985" rel="noreferrer" target="_blank">豫公网安备41010502005985</a>&nbsp;&nbsp;<a href="https://beian.miit.gov.cn" target="_blank" rel="noreferrer noopener">豫ICP备18017229号</a>'
# Article related configurations
article:
    # Code highlight settings
    highlight:
        # Code highlight themes
        # https://github.com/highlightjs/highlight.js/tree/master/src/styles
        theme: atom-one-light
        # Show copy code button
        clipboard: true
        # Default folding status of the code blocks. Can be "", "folded", "unfolded"
        fold: unfolded
    # Whether to show thumbnail image for every article
    thumbnail: true
    # Whether to show estimated article reading time
    readtime: true
    # Whether to show updated time. For \"auto\", shows article update time only when page.updated is set and it is different from page.date
    update_time: auto
    # Article licensing block
    licenses:
        Creative Commons:
            icon: fab fa-creative-commons
            url: 'https://creativecommons.org/'
        'CC BY 4.0': 'https://creativecommons.org/licenses/by/4.0/deed.zh'
    # og_image
    og_image: /images/og_image.png
# Search plugin configurations
# https://ppoffice.github.io/hexo-theme-icarus/categories/Plugins/Search/
search:
    type: insight
    json: /content.json
# Comment plugin configurations
# https://ppoffice.github.io/hexo-theme-icarus/categories/Plugins/Comment/
comment:
    # Name of the comment plugin
    type: twikoo
    env_id: https://twikoo.imaegoo.com
    js_url: /js/imaegoo/twikoo/1.6.31/twikoo.min.js
    # type: utterances
    # repo: imaegoo/imaegoo.github.io
    # issue_term: pathname
    # label: utterances
    # theme: preferred-color-scheme
# Donate plugin configurations
donates:
    # Alipay donate button configurations
    -
        type: alipay
        # Alipay qrcode image URL
        qrcode: '/images/alipay.jpg'
    # Wechat donate button configurations
    -
        type: wechat
        # Wechat qrcode image URL
        qrcode: '/images/wechat.png'
# Share plugin configurations
# https://ppoffice.github.io/hexo-theme-icarus/categories/Plugins/Share/
# Sidebar configurations.
# Please be noted that a sidebar is only visible when it has at least one widget
sidebar:
    # Left sidebar configurations
    left:
        # Whether the sidebar sticks to the top when page scrolls
        sticky: true
    # Right sidebar configurations
    right:
        # Whether the sidebar sticks to the top when page scrolls
        sticky: true
# Sidebar widget configurations
# http://ppoffice.github.io/hexo-theme-icarus/categories/Widgets/
widgets:
    # Profile widget configurations
    -
        # Where should the widget be placed, left sidebar or right sidebar
        position: left
        type: profile
        # Author name
        author: iMaeGoo
        # Author title
        author_title: 虹墨空间站
        # Author's current location
        location: Zhengzhou, China
        # URL or path to the avatar image
        avatar: /images/avatar.jpg
        # Whether show the rounded avatar image
        avatar_rounded: true
        # Email address for the Gravatar
        gravatar:
        # URL or path for the follow button
        follow_link: 'https://space.bilibili.com/4750943'
        # Links to be shown on the bottom of the profile widget
        social_links:
            GitHub:
                icon: fab fa-github
                url: 'https://github.com/imaegoo'
            QQ:
                icon: fab fa-qq
                url: 'https://jq.qq.com/?_wv=1027&k=2l9ZGIoL'
            Mail:
                icon: fas fa-envelope
                url: 'mailto:hello@imaegoo.com'
            RSS:
                icon: fas fa-rss
                url: '/atom.xml'
    # Archives widget configurations
    -
        # Where should the widget be placed, left sidebar or right sidebar
        position: left
        type: archives
        group_by: monthly
        format: 'YYYY 年 M 月'
    # Categories widget configurations
    #-
    #    # Where should the widget be placed, left sidebar or right sidebar
    #    position: left
    #    type: categories
    # Tags widget configurations
    #-
    #    # Where should the widget be placed, left sidebar or right sidebar
    #    position: left
    #    type: tags
    # Recommendation links widget configurations
    #-
    #    # Where should the widget be placed, left sidebar or right sidebar
    #    position: left
    #    type: links
    #    # Names and URLs of the sites
    #    links:
    #        maemoの風船が！: 'https://maemo.cc'
    #        米米的博客: 'https://zhangshuqiao.org'
    #        辣椒の酱: 'https://removeif.github.io'
    #        Sakitami的集装箱: 'https://blog.skihome.xyz'
    #        明月逐人归: 'https://mingshan.fun'
    #        宇宙湾: 'https://yuzhouwan.com'
    #        Ray’s Blog: 'https://raycoder.me'
    # Google AdSense unit configurations
    #-
    #    # Where should the widget be placed, left sidebar or right sidebar
    #    position: left
    #    type: adsense
    #    # AdSense client ID
    #    client_id: 'ca-pub-5716633754544549'
    #    # AdSense AD unit ID
    #    slot_id: '6035187824'
    # Table of contents widget configurations
    -
        # Where should the widget be placed, left sidebar or right sidebar
        position: right
        type: toc
    # Recent posts widget configurations
    -
        # Where should the widget be placed, left sidebar or right sidebar
        position: right
        type: recent_posts
        limit: 5
    # Twikoo new comment widget configurations
    -
        # Where should the widget be placed, left sidebar or right sidebar
        position: right
        type: twikoo_new
        env_id: https://twikoo.imaegoo.com
# Plugin configurations
plugins:
    # Enable page startup animations
    animejs: false
    # Show the "back to top" button
    back_to_top: true
    # netlify identity
    netlify: false
    # Baidu Analytics plugin settings
    # https://tongji.baidu.com
    baidu_analytics:
        # Baidu Analytics tracking ID
        tracking_id: # 4d5b97d11341c6f57b58fc622dc1ac38
    # BuSuanZi site/page view counter
    # https://busuanzi.ibruce.info
    busuanzi: true
    # Enable the lightGallery and Justified Gallery plugins
    # https://ppoffice.github.io/hexo-theme-icarus/Plugins/General/gallery-plugin/
    gallery: true
    # Google Analytics plugin settings
    # https://analytics.google.com
    google_analytics:
        # Google Analytics tracking ID
        tracking_id: G-RCCCLYKRH5
    # Hotjar user feedback plugin
    # https://www.hotjar.com/
    hotjar:
        # Hotjar site id
        site_id:
    # Enable the KaTeX math typesetting supprot
    # https://katex.org/
    katex: false
    # Enable the MathJax math typesetting support
    # https://www.mathjax.org/
    mathjax: false
    # Enable the Outdated Browser plugin
    # http://outdatedbrowser.com/
    outdated_browser: false
    # Show a progress bar at top of the page on page loading
    progressbar: false
    cookie_consent:
        # 同意对话框类型。可以为"info"，"opt-in"，或"opt-out"
        type: info
        # 弹出框主题。可以为"block"，"edgeless"，或"classic"
        theme: edgeless
        # 是否使弹出框固定，不随页面滚动而滚动
        static: false
        # 弹出框在屏幕上的位置
        position: bottom-right
        # 你网站的Cookie协议的URL
        policyLink: '/cookies/'
# CDN provider settings
# https://ppoffice.github.io/hexo-theme-icarus/Configuration/Theme/speed-up-your-site-with-custom-cdn/
providers:
    # Name or URL template of the JavaScript and/or stylesheet CDN provider
    cdn: host
    # Name or URL template of the webfont CDN provider
    fontcdn: host
    # Name or URL of the fontawesome icon font CDN provider
    iconcdn: host
```

</details>

