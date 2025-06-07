---
project: nextjs-markdown-blog
stars: 12
description: |-
    null
url: https://github.com/machadop1407/nextjs-markdown-blog
---

# Next.js Blog Tutorial - pedrotech

Welcome to the official project for the **Next.js Blog Tutorial** by **pedrotech**! This project is a step-by-step guide for building a personal blog with Next.js and Markdown, and is perfect for beginners looking to dive into modern web development practices.

## 🚀 What You Will Learn

In this tutorial, you will:

- Learn how to create a personal blog using **Next.js**.
- Integrate **Markdown** to easily manage blog posts.
- Utilize **Static Generation** with `getStaticProps` and `getStaticPaths` for SEO-friendly pages.
- Build a clean, responsive, and professional blog design.
- Gain insights into **React** and **Next.js** best practices.

## 📺 YouTube Tutorial

This repository accompanies my YouTube tutorial on **pedrotech**. In the video, I walk you through the entire process of building this blog from scratch. Check out the tutorial here:

[**pedrotech YouTube Channel**](https://www.youtube.com/channel/your-channel-link)

## 🔧 Prerequisites

Before you start, ensure you have the following installed on your computer:

- **Node.js** (Version 14 or higher)
- **npm** (Node Package Manager) or **yarn**

## 📝 Getting Started

### 1. Clone the repository

Clone this repository to your local machine:

\```bash
git clone https://github.com/your-username/nextjs-blog-tutorial.git
\```

### 2. Install dependencies

Navigate into the project directory and install the required dependencies:

\```bash
cd nextjs-blog-tutorial
npm install
# OR
yarn install
\```

### 3. Create your blog posts

To add blog posts, navigate to the `posts/` directory and create Markdown files (e.g., `sample-article.md`). Each file should contain your article's front matter and content in Markdown format.

Here’s a simple example of a Markdown file:

\```markdown
---
title: "My First Blog Post"
date: "2024-11-01"
---

This is my first blog post using **Markdown** and **Next.js**. It’s really easy to create content!
\```

### 4. Run the development server

Once the dependencies are installed, start the Next.js development server:

\```bash
npm run dev
# OR
yarn dev
\```

Visit `http://localhost:3000` in your browser to view your blog. The posts will automatically be pulled from the `posts/` directory and rendered dynamically.

## 📜 Project Structure

Here’s a breakdown of the main files and directories:

- **pages/**: Contains all of your application’s pages. The `index.tsx` file renders the homepage and `posts/[slug].tsx` handles individual blog post pages.
- **lib/posts.ts**: A utility file to read the Markdown files and parse them into content.
- **posts/**: Directory where your blog posts in Markdown format reside.
- **public/**: Contains static assets like images, CSS, and fonts.

## 🖋️ Customization

- **Styling**: Feel free to customize the design by modifying `styles/globals.css` or adding your own CSS.
- **SEO**: You can improve SEO by adding a `<Head>` tag inside the `pages/_document.tsx` to include metadata for better search engine indexing.

## 🤝 Contributing

If you find any issues or have suggestions for improvements, feel free to open an issue or a pull request. Contributions are welcome!

## 🔗 Links

- [pedrotech YouTube Channel](https://www.youtube.com/channel/your-channel-link)
- [Next.js Documentation](https://nextjs.org/docs)
- [Markdown Syntax Guide](https://www.markdownguide.org/)

## 🧑‍💻 License

This project is open-source and available under the [MIT License](LICENSE).

