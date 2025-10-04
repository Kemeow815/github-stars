---
project: appicon-forge
stars: 963
description: |-
    An intuitive app icon generator that lets you customize colors, borders, shadows, and more to create unique app icons effortlessly.
url: https://github.com/zhangyu1818/appicon-forge
---

# AppIcon Forge

Language: [简体中文](./README_zh-CN.md)

A simple tool that allows you to generate usable app icons without any design expertise.

## Example

![example1](./screenshots/1-1.png)
![example2](./screenshots/1-2.png)
![example3](./screenshots/1-3.png)
![example4](./screenshots/1-4.png)
![example5](./screenshots/1-5.png)

## Features

- Customize icon size, position, color, background color, border, gradient, and shadow.
- Customize text content, text gradient, and fonts.
- Customize local SVG files or images.
- Generate icons using [Iconify Icons](https://iconify.design/) with over 200,000 available icons.
- Real-time preview of your icon changes.
- Easy export of icons for apps.

> [!IMPORTANT]
> The text icons use the system's default fonts, and copyright compliance cannot be guaranteed. Please proceed with caution when making your selection.
>
> You can use custom Google fonts to avoid this.

## Usage

You can use AppIcon Forge directly from GitHub Pages without any installation. Simply visit the following URL:

[AppIcon Forge on GitHub Pages](https://zhangyu1818.github.io/appicon-forge/)

If you want to run it locally:

Clone the repository and install dependencies:

```sh
# Clone the repository
git clone https://github.com/zhangyu1818/appicon-forge.git

# Navigate to the directory
cd appicon-forge

# Install dependencies
pnpm install
```

Start the development server:

```sh
pnpm dev
```

Visit `http://localhost:5173/appicon-forge/` in your browser to start using AppIcon Forge.

## Deployment

### Manual

To build the project for production:

```sh
pnpm build
```

Deploy the contents of the `out` folder to your web server or GitHub Pages.

### Docker

```console
# Clone the repository
git clone https://github.com/zhangyu1818/appicon-forge.git

# Navigate to the directory
cd appicon-forge

# Build the image
docker build -t appicon-forge .


# Renive the image
docker rmi appicon-forge
```

#### Docker run

```console
# Build and start the container
docker run -d --name=appicon-forge --restart=always -p 5173:80 appicon-forge

# Stop and remove the container
docker stop appicon-forge
docker rm appicon-forge
```

#### Docker compose

```console
# Build and start the container
docker-compose up -d

# Stop and remove the container
docker-compose down
```

## License

This project is licensed under the MIT License.

