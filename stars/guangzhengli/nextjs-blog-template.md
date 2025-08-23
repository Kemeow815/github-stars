---
project: nextjs-blog-template
stars: 124
description: |-
    Next.js Blog Template for ladder theme
url: https://github.com/guangzhengli/nextjs-blog-template
---

# [中文文档](README.zh.md)

<h1 align=center>Nextjs Blog Template | Ladder Theme | <a href="https://guangzhengli.com">Blog</a></h1>

This repository is a Next.js implementation of the [hugo-ladder-theme](https://github.com/guangzhengli/hugo-theme-ladder).

This is a Next.js blog template, and here's an introduction to the basic usage of this template.

## How to develop locally?

```bash
npm install


npm run dev
```

## How to deploy

Clone or fork locally, modify the configuration as described below, then select this repository for deployment on [Vercel](https://vercel.com).

All deployment configurations can use the default settings, no special configuration is needed.

If you need to use edge or fluid compute, please modify the code or vercel configuration yourself.

# Blog Configuration

## 1. How to write blogs

Blog files in this repository need to be placed in the `src/content/blog` directory, they can be markdown files or mdx files.

The following metadata needs to be configured according to your needs:

- `title`: Blog title
- `date`: Blog publication date
- `updated`: Blog update date
- `keywords`: Blog keywords for SEO optimization
- `featured`: Whether to display on the homepage
- `summary`: Blog summary

## 2. Blog Configuration

All blog configurations are centralized in the `src/lib/config.ts` file, which has the following advantages:

1. Centralized management: All configurations are in one file, making it easy to maintain and modify
2. Type safety: Using TypeScript provides type checking and auto-completion
3. Reusability: Avoids duplicate configurations scattered across different files
4. Consistency: Ensures the same configuration values are used everywhere

### 2.1 Site Basic Configuration

```typescript
site: {
  title: "Your blog title",
  name: "Your blog name",
  description: "Blog description",
  keywords: ["keyword1", "keyword2"],
  url: "https://yourdomain.com",
  baseUrl: "https://yourdomain.com",
  image: "https://yourdomain.com/og-image.png",
  favicon: {
    ico: "/favicon.ico",
    png: "/favicon.png",
    svg: "/favicon.svg",
    appleTouchIcon: "/favicon.png",
  },
  manifest: "/site.webmanifest",
}
```

These configurations are used for:
- Basic website information display
- SEO optimization
- Browser tab icons
- Social media share previews

### 2.2 Author Information Configuration

```typescript
author: {
  name: "Your name",
  email: "Your email",
  bio: "Personal bio",
}
```

Author information is used for:
- Homepage display
- RSS feed information
- Author information in blog posts

### 2.3 Social Media Configuration

```typescript
social: {
  github: "https://github.com/yourusername",
  x: "https://x.com/yourusername",
  xiaohongshu: "https://www.xiaohongshu.com/user/profile/yourID",
  wechat: "Your WeChat QR code image link",
  buyMeACoffee: "https://www.buymeacoffee.com/yourusername",
}
```

These links will be displayed in:
- Social media links area on the homepage
- Social media icons in the navigation bar

### 2.4 Comment System Configuration

```typescript
giscus: {
  repo: "Your GitHub repository name",
  repoId: "Repository ID",
  categoryId: "Category ID",
}
```

Using Giscus as the comment system requires:
1. Install the Giscus app on GitHub
2. Enable Discussions in your repository
3. Get the configuration information and fill it in here

### 2.5 Navigation Menu Configuration

```typescript
navigation: {
  main: [
    { 
      title: "Articles", 
      href: "/blog",
    },
    // You can add more navigation items
  ],
}
```

This configures the website's navigation menu, supporting:
- Regular links
- Dropdown menus with submenus

### 2.6 SEO Configuration

```typescript
seo: {
  metadataBase: new URL("https://yourdomain.com"),
  alternates: {
    canonical: './',
  },
  openGraph: {
    type: "website" as const,
    locale: "en_US",
  },
  twitter: {
    card: "summary_large_image" as const,
    creator: "@yourtwitterusername",
  },
}
```

These configurations are used for:
- Search engine optimization
- Social media sharing cards
- Website metadata

### 2.7 RSS Subscription Configuration

```typescript
rss: {
  title: "Your blog title",
  description: "Blog description",
  feedLinks: {
    rss2: "/rss.xml",
    json: "/feed.json",
    atom: "/atom.xml",
  },
}
```

These configurations are used to generate:
- RSS 2.0 feeds
- JSON Feed
- Atom feeds

## 3. How to modify configuration

1. Open the `src/lib/config.ts` file
2. Modify the corresponding configuration items according to your needs
3. After saving the file, Next.js will automatically rebuild and apply the new configuration

Notes:
- Ensure all URLs are valid
- Image links should be accessible
- Social media links should be complete URLs
- After modifying configuration, it's recommended to check the website's:
  - Homepage display
  - Navigation menu
  - SEO information
  - Social media sharing effects
  - RSS feeds

## 4. How to generate RSS feeds

Modify the configuration in the scripts/generate-rss.js file, then run:

```bash
npm run generate-rss
```

## 5. How to generate Sitemap

Modify the configuration in the scripts/generate-sitemap.js file, then run:

```bash
npm run generate-sitemap
```


## Support

This repository is open source, welcome to star and fork. If you find this repository helpful, you can support me in the following ways:


<h2 align=center><a href="https://guangzhengli.com/blog/zh/build-nextjs-template">Support the best Next.js indie developer starter template</a></h2>

<h3 align=center><a href="https://nextdevkit.com">NextDevKit</a></h3>

![nextdevkit](/public/blog/nextdevkit-template.png)
