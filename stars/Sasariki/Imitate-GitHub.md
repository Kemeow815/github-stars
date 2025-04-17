---
project: Imitate-GitHub
stars: 3
description: |-
    一个仿制github的个人主页（仅供学习交流个人使用禁止商用）
url: https://github.com/Sasariki/Imitate-GitHub
---

# GitHub Profile Portfolio

[English](README.md) | [中文](README_zh.md)

A beautiful and modern portfolio website that showcases your GitHub projects, contributions, and skills. This project provides a clean and professional interface to display your work and connect with others.

## preface
It is for personal learning and communication purposes only, and should not be used for commercial purposes

## Features

- 🌓 Dark/Light theme support
- 📊 GitHub contribution graph
- 📱 Responsive design
- 🔄 Real-time GitHub data integration
- 📝 Project showcase with detailed information
- ⭐ Starred repositories display
- 💬 Social media integration
- 📱 QR code support for WeChat and QQ

## Preview

[Add your preview image here]

## Getting Started

### Prerequisites

- A GitHub account
- Basic knowledge of HTML, CSS, and JavaScript
- A web server to host the files

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/github-profile-portfolio.git
cd github-profile-portfolio
```

2. Download required dependencies:
   - [github.min.css](https://github.com/sindresorhus/github-markdown-css)
   - [github-dark.min.css](https://github.com/sindresorhus/github-markdown-css)
   - [highlight.min.js](https://highlightjs.org/)
   - [marked.min.js](https://marked.js.org/)

3. Place these files in your project root directory.

### Configuration

1. Update `index.html`:
   - Change the title
   - Update your profile information
   - Add your social media links
   - Update the footer information

2. Update `main.js`:
   - Set your GitHub username:
   ```javascript
   const GITHUB_USERNAME = 'yourusername';
   ```
   - Add your GitHub token (optional, but recommended for higher API limits):
   ```javascript
   const GITHUB_TOKEN = 'your_github_token';
   ```
   - Update QR code paths for WeChat and QQ:
   ```javascript
   function showWechat(event) {
       showQRCode('WeChat', 'path/to/your/wechat-qr.png', 'Scan to add WeChat');
   }
   
   function showQQ(event) {
       showQRCode('QQ', 'path/to/your/qq-qr.png', 'Scan to add QQ');
   }
   ```

3. Customize your tech stack in the `renderOverview` function:
```javascript
[
    "HTML", "CSS", "JavaScript", "React", "Node.js",
    "Git", "Vue", "TypeScript", "MongoDB", "PHP",
    "Python", "MySQL", "Linux"
]
```

### GitHub Token Setup

1. Go to GitHub Settings > Developer settings > Personal access tokens
2. Generate a new token with the following permissions:
   - `repo` (Full control of private repositories)
   - `user` (Read user information)
3. Copy the token and paste it in `main.js`

## Customization

### Theme Colors

The project uses CSS variables for theming. You can customize the colors by modifying the variables in `css.css`:

```css
:root {
    --color-bg-primary: #ffffff;
    --color-bg-secondary: #f6f8fa;
    --color-text-primary: #24292e;
    --color-text-secondary: #57606a;
    /* Add more color variables as needed */
}

[data-theme="dark"] {
    --color-bg-primary: #0d1117;
    --color-bg-secondary: #161b22;
    --color-text-primary: #c9d1d9;
    --color-text-secondary: #8b949e;
    /* Add more dark theme color variables */
}
```

### Project Cards

You can customize the project card layout by modifying the `renderProjectCard` function in `main.js`. The current implementation includes:
- Project name
- Description
- Language tags
- Stars and forks count
- Last update date

### Contribution Graph

The contribution graph is automatically generated based on your GitHub activity. You can customize its appearance by modifying the CSS classes in `css.css`.

## Deployment

1. Choose a hosting service (GitHub Pages, Netlify, Vercel, etc.)
2. Upload your files to the hosting service
3. Configure your domain (if using a custom domain)

### GitHub Pages Deployment

1. Go to your repository settings
2. Navigate to "Pages"
3. Select your branch and folder
4. Save the settings

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [GitHub Markdown CSS](https://github.com/sindresorhus/github-markdown-css)
- [Highlight.js](https://highlightjs.org/)
- [Marked](https://marked.js.org/)

## Support

If you encounter any issues or have questions, please open an issue in the GitHub repository. 

