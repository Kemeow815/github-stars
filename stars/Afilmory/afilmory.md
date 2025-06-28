---
project: afilmory
stars: 497
description: |-
    A personal photography website celebrating the art of capturing moments with a nostalgic, retro vibe. Blending aperture, film, and memory.
url: https://github.com/Afilmory/afilmory
---

<p align="center">
  <img src="https://github.com/Afilmory/assets/blob/main/afilmory-readme.webp?raw=true" alt="Afilmory" width="100%" />
</p>

# <p align="center">Afilmory</p>

Afilmory (/əˈfɪlməri/, "uh-FIL-muh-ree") is a term created for personal photography websites, blending Auto Focus (AF), aperture (light control), film (vintage medium), and memory (captured moments).

A modern photo gallery website built with React + TypeScript, supporting automatic photo synchronization from multiple storage sources (S3, GitHub), featuring high-performance WebGL rendering, masonry layout, EXIF information display, thumbnail generation, and more.

Live Photo Galleries:

- https://afilmory.innei.in
- https://gallery.mxte.cc
- https://photography.pseudoyu.com
- https://afilmory.magren.cc

## 🌟 Features

### Core Functionality

- 🖼️ **High-Performance WebGL Image Renderer** - Custom WebGL component with smooth zoom and pan operations
- 📱 **Responsive Masonry Layout** - Powered by Masonic, adapts to different screen sizes
- 🎨 **Modern UI Design** - Built with Tailwind CSS and Radix UI component library
- ⚡ **Incremental Sync** - Smart change detection, processes only new or modified photos
- 🌐 **i18n** - Multi-language support
- 🔗 **OpenGraph** - OpenGraph metadata for social media sharing

### Image Processing

- 🔄 **HEIC/HEIF Format Support** - Automatic conversion of Apple device HEIC format
- 🖼️ **Smart Thumbnail Generation** - Multi-size thumbnails for optimized loading performance
- 📊 **EXIF Information Display** - Complete shooting parameters including camera model, focal length, aperture, etc.
- 🌈 **Blurhash Placeholders** - Elegant image loading experience
- 📱 **Live Photo Support** - Detection and display of iPhone Live Photos

### Advanced Features

- 🎛️ **Fujifilm Simulation** - Read and display Fujifilm camera film simulation settings
- 🔍 **Fullscreen Viewer** - Image viewer with gesture support
- 🏷️ **File System Tags** - Auto-generated tags based on file system
- ⚡ **Concurrent Processing** - Multi-process/multi-thread concurrent processing support
- 🗂️ **Multi-Storage Support** - S3, GitHub, and other storage backends

## 🏗️ Technical Architecture

### Frontend Tech Stack

- **React 19** - Latest React version with Compiler
- **TypeScript** - Complete type safety
- **Vite** - Modern build tool
- **Tailwind CSS** - Atomic CSS framework
- **Radix UI** - Accessible component library
- **Jotai** - State management
- **TanStack Query** - Data fetching and caching
- **React Router 7** - Routing management
- **i18next** - Internationalization

### Build System

- **Node.js** - Server-side runtime
- **Sharp** - High-performance image processing
- **AWS SDK** - S3 storage operations
- **Worker Threads/Cluster** - Concurrent processing
- **EXIF-Reader** - EXIF data extraction

### Storage Architecture

Designed with adapter pattern, supporting multiple storage backends:

- **S3-Compatible Storage** - AWS S3, MinIO, Alibaba Cloud OSS, etc.
- **GitHub Storage** - Using GitHub repository as image storage

## 🚀 Quick Start

### Docker Deployment

[Docker Deployment](https://github.com/Afilmory/docker)

### Requirements

- Node.js 18+
- At least 4GB RAM (for image processing)

### 1. Clone the Project

```bash
git clone https://github.com/Afilmory/Afilmory.git
cd photo-gallery-site
```

### 2. Install Dependencies

```bash
pnpm install
```

### 3. Configuration

Create `.env` file:

```env
# S3 Storage Keys
S3_ACCESS_KEY_ID=your_access_key_id
S3_SECRET_ACCESS_KEY=your_secret_access_key
```

Create `builder.config.json` file for storage configuration and other options:

```json
{
  "storage": {
    "provider": "s3",
    "bucket": "my-photos",
    "region": "us-east-1",
    "prefix": "photos/",
    "customDomain": "https://cdn.example.com",
    "endpoint": "https://s3.amazonaws.com"
  }
}
```

### 4. Site Configuration

Copy and edit the configuration file:

```bash
cp config.example.json config.json
```

Edit `config.json`:

```json
{
  "name": "My Afilmory",
  "title": "My Afilmory",
  "description": "Capturing beautiful moments in life",
  "url": "https://afilmory.example.com",
  "accentColor": "#007bff", // Optional, set theme color
  "author": {
    "name": "Your Name", // Required, set author name
    "url": "https://example.com", // Required, set author homepage
    "avatar": "https://example.com/avatar.png" // Required, set author avatar
  },
  "social": {
    // Optional, set social accounts
    "twitter": "@yourusername"
  },
  "feed": {
    "folo": { // Optional, set Folo RSS claim
      "challenge": {
        "feedId": "155982289762921472",
        "userId": "41312624216137728"
      }
    }
  }
}
```

### 5. Build Photo Manifest

```bash
# Initial build
pnpm run build:manifest

# Incremental update
pnpm run build:manifest

# Force full update
pnpm run build:manifest -- --force
```

### 6. Start Development Server

```bash
pnpm dev
```

## ⚙️ Configuration Options

#### Remote Repository Configuration (`repo`)

To achieve incremental builds in CI, it is necessary to configure a cache repository, which will pull the cache before each build and upload the build results after the build.

```json
{
  "repo": {
    "enable": true,
    "url": "https://github.com/username/gallery-assets"
  }
}
```

This will automatically pull resources from the remote repository, avoiding rebuilds each time.

**In order to achieve uploading to the git repository, you need to provide a `GIT_TOKEN` and write it in the `.env` file.**

#### Storage Configuration (`storage`)

- `provider`: Storage provider (`s3` | `github`)
- `bucket`: S3 bucket name
- `region`: S3 region
- `endpoint`: S3 endpoint (optional)
- `prefix`: File prefix
- `customDomain`: Custom domain
- `excludeRegex`: Regular expression to exclude files (optional)

#### Build Options (`options`)

- `defaultConcurrency`: Default concurrency
- `enableLivePhotoDetection`: Enable Live Photo detection
- `showProgress`: Show build progress
- `showDetailedStats`: Show detailed statistics

#### Performance Configuration (`performance`)

- `worker.workerCount`: Number of worker processes
- `worker.timeout`: Worker timeout (milliseconds)
- `worker.useClusterMode`: Enable cluster mode

#### Logging Configuration (`logging`)

- `verbose`: Verbose logging
- `level`: Log level (`info` | `warn` | `error` | `debug`)
- `outputToFile`: Output to file


## 📋 CLI Commands

### Build Commands

```bash
# View help
pnpm run build:manifest -- --help

# Incremental update (default)
pnpm run build:manifest

# Force full update
pnpm run build:manifest -- --force

# Only regenerate thumbnails
pnpm run build:manifest -- --force-thumbnails

# Only regenerate manifest
pnpm run build:manifest -- --force-manifest
```

### Development Commands

```bash
# Start development server
pnpm dev

# Build production version
pnpm build
```

### Notes

- Ensure your S3 bucket already contains photo files
- If using remote repository, configure `builder.config.json` first

## 🔧 Advanced Usage

### Custom Storage Provider

Implement the `StorageProvider` interface to support new storage backends:

```typescript
import { StorageProvider } from './src/core/storage/interfaces'

class MyStorageProvider implements StorageProvider {
  async getFile(key: string): Promise<Buffer | null> {
    // Implement file retrieval logic
  }

  async listImages(): Promise<StorageObject[]> {
    // Implement image list retrieval logic
  }

  // ... other methods
}
```

### Custom Image Processing

Add custom processors in the `src/core/image/` directory:

```typescript
export async function customImageProcessor(buffer: Buffer) {
  // Custom image processing logic
  return processedBuffer
}
```

## 📄 License

MIT License © 2025 Innei

## 🔗 Related Links

- [Live Demo](https://gallery.innei.in)
- [Personal Website](https://innei.in)
- [GitHub](https://github.com/innei)

---

If this project helps you, please give it a ⭐️ Star for support!

