---
project: AnimatedGallery
stars: 163
description: |-
    A beautiful and modern photo gallery application
url: https://github.com/SimonAKing/AnimatedGallery
---

# SimonAKing-Gallery

[中文版说明](README.zh_CN.md)

## Introduction

> A beautiful and modern photo gallery project.

![preview](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExemVnOXBjZ2ZlNzJvY3dubGMxczdid2ZsNDh5bzR1eWszemxnd3Q3cCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/MCKs2Xv3BZOW0e6AzC/giphy.gif)

[Online browsing](http://simonaking.com/gallery)

Do you want to install such a cool gallery for your website?

Let's start now!

## Features

- Automatic image compression with quality preservation
- BlurHash-powered elegant image loading
- Responsive masonry layout with zoom support
- Mobile-friendly design with smooth animations
- Simple photo management via `/photos` directory

## Installation

```sh
git clone https://github.com/SimonAKing/Gallery.git
cd Gallery
npm install
npm run dev
```

## How to Update Photos

### Local Photo Updates

1. **Add Your Photos**
   - Place your photos in the `photos` directory at the project root
   - Images will be automatically compressed during build
   - Original folder structure will be maintained

2. **Preview and Build**
   - For local preview: `npm run dev`
   - Check the layout and loading effects
   - To build for production: `npm run build`
   - Compressed photos will be in `public/photos`

### Update Hosted Photos

1. **Build the Project**
   - Run `npm run build` in the root directory
   - This will generate optimized photos in the `dist` directory

2. **Deploy to GitHub Pages**
   - Option 1: Deploy to username.github.io
     ```sh
     cd dist
     git init
     git add -A
     git commit -m "deploy gallery"
     git remote add origin https://github.com/[username]/[username].github.io.git
     git push -f origin main
     ```
     - Visit `username.github.io` to view your gallery

   - Option 2: Deploy as a subdirectory
     - If your username.github.io is occupied, create a new repo (e.g., `gallery`)
     - Deploy to this repo and it will be available at `username.github.io/gallery`
     - Update your CDN configuration in `package.json`:
     ```json
     {
       "config": {
         "cdn": "https://cdn.jsdelivr.net/gh/[username]/gallery/photos/"
       }
     }
     ```

### Custom Storage Options

The `scripts/update.js` script reads images and generates `photos.js` content during each preview generation. This file represents all photos in your gallery. If you're using OSS, an existing image hosting service, or other storage solutions, you can modify the image reading logic in this script.

To use custom storage:
1. Modify the `processPhotoWithWorker` function in `scripts/update.js`
2. Update the photo source path generation logic
3. Adjust the CDN configuration in `package.json` if needed

Example for custom storage:
```js
// Modify the src generation in processPhotoWithWorker
const src = YOUR_CUSTOM_STORAGE_URL + photo;
```

## Sponsor
I spent a lot of time and energy to develop this project.

If this project has brought you help, welcome to sponsor, `star`.

Thank you!
