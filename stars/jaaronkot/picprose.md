---
project: picprose
stars: 741
description: |-
    Better cover image generator tool for Medium, Blog, Youtube, BiliBili and many others
url: https://github.com/jaaronkot/picprose
---

# PicProse - Better Cover Image Generator

[![GitHub stars](https://img.shields.io/github/stars/jaaronkot/picprose)](https://github.com/jaaronkot/picprose/stargazers)
[![License](https://img.shields.io/github/license/jaaronkot/picprose)](https://github.com/jaaronkot/picprose/blob/main/LICENSE) 

<a href="./README.md">English</a> | <a href="./README_CN.md">简体中文</a>

## Overview

PicProse is a powerful cover image generator designed for bloggers, content creators, developers, and designers. Create professional and stunning cover images in just a few steps for Medium, YouTube, BiliBili, personal blogs, and other platforms.

**Preview:** [picprose.pixpark.net](https://picprose.pixpark.net/)



![PicProse Preview](./doc/demo-1.jpg )

![PicProse Preview](./doc/demo-2.jpg )

![PicProse Preview](./doc/demo-3.jpg )

## ✨ Key Features

- 🖼️ **Rich Image Resources** - Access high-quality images directly through the Unsplash API
- 🎨 **Flexible Editing** - Customize titles, author info, fonts, colors, and transparency
- 📱 **Multiple Aspect Ratios** - Support for both landscape and portrait formats for different platforms
- 🔍 **Real-time Preview** - See all changes instantly with a WYSIWYG interface
- 🌈 **Developer Icons** - Built-in tech-related icons perfect for technical article covers
- 📥 **Multiple Export Formats** - Support for JPG, PNG, and SVG exports
- 🌐 **Multilingual Support** - Interface available in multiple languages
- 🎯 **Responsive Design** - Perfectly adapts to both desktop and mobile devices

## 🚀 Getting Started

### Installation

```bash
# Clone the repository
git clone https://github.com/jaaronkot/picprose.git

# Navigate to the project directory
cd picprose

# Install dependencies
npm install

# Start the development server
npm run dev
```

### Environment Variables

Create a `.env.local` file with the following content:

```bash
UNSPLASH_API_KEY = your_unsplash_api_key
NEXT_PUBLIC_GOOGLE_ANALYTICS_ID=your_ga_id
```
Refer: [https://unsplash.com/documentation](https://unsplash.com/documentation)


## Deploy to Vercel
You can start by creating your own Nextra site and deploying to Vercel by clicking the link:

<a className="mt-3 inline-flex"
  target="_blank"
  href="https://vercel.com/new/clone?s=https://github.com/jaaronkot/picprose&showOptionalTeamCreation=false">![](https://vercel.com/button)</a>

## Deploy with Docker

```sh
docker run -d --name picprose -e UNSPLASH_API_KEY=xxx -p 3000:3000 hausen1012/picprose
```

## License
PicProse is open-source under the [MIT License](https://github.com/jaaronkot/picprose/blob/main/LICENSE).

