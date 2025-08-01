---
project: hugo-shortcode-gallery
stars: 396
description: |-
    A theme component with a gallery shortcode for the static site generator hugo.
url: https://github.com/mfg92/hugo-shortcode-gallery
---

# hugo-shortcode-gallery

This is a theme component for Hugo.

This component contains a shortcode to include a gallery in your .md files.

The gallery is rendered using autogenerated thumbnails arranged in a
[grid](http://miromannino.github.io/Justified-Gallery/). With a click on the images
a [lightbox](http://brutaldesign.github.io/swipebox/) is opened and all images can be
viewed full screen.

# Demo

You can see this shortcode-gallery in action on [my website](https://matze.rocks/images/).

## Installation

### Method A - Install as hugo module

First make sure that your project itself is a [Hugo module](https://gohugo.io/hugo-modules/use-modules/#initialize-a-new-module).

Then add these two lines to your hugo.toml (or [config.toml](https://github.com/gohugoio/hugo/issues/8979)) configuration file:
```
[[module.imports]]
path = "github.com/mfg92/hugo-shortcode-gallery"
```

On the first start of Hugo it will download the required files.

To update to the latest version of the module run:
```
hugo mod get -u
```

### Method B - Install via git
Clone this git repository into your *themes* folder.

```
git clone https://github.com/mfg92/hugo-shortcode-gallery.git
```

Next edit your projects
*config.toml* and add this theme component to your themes:

```
theme = ["YOUR_MAIN_THEME", "hugo-shortcode-gallery"]
```

To read about Hugo's theme components and how to use them have a look at
https://gohugo.io/hugo-modules/theme-components/.

To update to the latest version run inside *themes/hugo-shortcode-gallery*:
```
git pull
```
Tip: If your project itself is version controlled using git, you may want to have hugo-shortcode-gallery as a [git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

## Usage Example

Here is an usage example:

```
{{< gallery match="images/*" sortOrder="desc" rowHeight="150" margins="5" thumbnailResizeOptions="600x600 q90 Lanczos" showExif=true previewType="blur" embedPreview=true loadJQuery=true >}}
```

This shortcode will generate a gallery containing all images of the folder *images*.
The folder must be located next to the .md file where this gallery is used in. This uses [page bundles](https://gohugo.io/content-management/page-bundles/)
so the directory layout should look like this:

```
new-post-name/
    index.md
    images/
        DSC_0001.jpg
        DSC_0002.jpg
```

The parameter `sortOrder` decides whether the images are sorted ascending (`asc`) or descending (`desc`). The `randomize` parameter can be used (as `randomize=true`) to have a random order.

The `rowHeight` parameter determines the height of the rows that are displayed while the
`margin` parameter defines the gap between the images.

A thumbnail is generated using the `thumbnailResizeOptions` parameter, they are handed over
to *Hugo's* [image processing](https://gohugo.io/content-management/image-processing/)
function using the fit method. In the example above, the generated thumbnails have a width of max 600 pixel and
a height of max 600, the actual width and height depend on the original aspect ratio. The JPEG image quality is 90% and the
scaling uses the high quality *Lanczos* filter.

If `previewType` is set to "blur" (or "color"), a very low resolution image (or a single pixel image) will be loaded for every image in the gallery first.
The high resolution thumbnail images (see `thumbnailResizeOptions`) will only be loaded if they are on the currently visible part of the page (or close to it).
This leads to a faster loading page. You can set `previewType` to "none" to disable this feature and all thumbnails will be directly loaded.

Enable `embedPreview` to let Hugo embed the tiny preview image directly in the page HTML as a base64 strings. This reduces the amount of required network round trip times.

The setting `thumbnailHoverEffect` configures what should happen when the mouse hovers above a thumbnail in the gallery.
It defaults to "none", but it can be set to "enlarge", in that case the image is scaled up (x1.1) in a short smooth animation.

The size of the image as shown in the gallery can be customized using the (optional) `imageResizeOptions` parameter. The syntax is the same as for `thumbnailResizeOptions`. If omitted, the image will be displayed in its original size.

The setting `lastRow` configures the justification of the last row of the grid. When set to "justify", the entire grid including the last row will be fully-justified, right and left. This parameter respects all of the `lastRow` options of Justified Gallery, including "nojustify" and "hide".

When the users clicks on an image, a lightbox shows up displaying the clicked image in large using the whole available space.
If the image contains a title/description in the EXIF metadata field _ImageDescription_ or a title is defined in the image's sidecar file (see section below) there will be a top bar displaying that.
If the `showExif` option is set to `true` (without quotes), some parts of the image's EXIF data will be shown on the bottom bar e.g.: "Canon EOS 80D + EF100-400mm f/4.5-5.6L IS II USM 400mm f/8 1/400sec ISO 2500".
The EXIF display will only work if you add following lines to your *config.toml*:
```TOML
[imaging.exif]
    includeFields = ".*"
```

An advanced setting is `filterOptions`: It allows the user to filter the displayed images by using buttons.
The text of the buttons and the regex used to filter has to be specified in a JSON array of objects. Currently it is only supported to filter by EXIF tags, image description, start rating or color labels. In the future it will be possible to filter by image name or other EXIF fields (pull requests are welcome). In addition to the metadata of the EXIF embedded in the image, a metadata sidecar file (see section below) can be used to add metadata for filtering.

Additionally to the filter buttons, a button to activate full screen mode of the gallery is added.

An example of the `filterOptions` JSON:
```
filterOptions="[{label: 'All', tags: '.*'}, {label: 'Birds', tags: 'bird'}, {label: 'Macro', tags: 'macro'}, {label: 'Insects', tags: 'insect'}]"
```

When `filterOptions` is used, the switch `storeSelectedFilterInUrl` can be set to `true`. This will instruct the gallery to append the name of the filter to the url displayed in the browser when a filter button is clicked. This has two purposes: The user can share this link and recipients will see the gallery with the same filter as the original user. Furthermore the selected filter is stored in the browsers history.

As many websites/themes already include *jQuery*, this theme component will use the available *jQuery* lib.
If the page does not already use *jQuery* the parameter `loadJQuery=true` must be used to
instruct the theme component to load the provided *jQuery* lib.

All settings can be done globally in the site's *config.toml*, for that the prefix `gallery` has to be used. E.g. `galleryLoadJQuery` instead of `loadJQuery`.

### Using repeating images across pages

If you need to use the same images across pages/sections of the website, you can
place the repeating images under `/assets` and use the `globalMatch` instead
of the `match` parameter. The `match` parameter will only look locally to the
page to find resources, while `globalMatch` will look for global resources,
as detailed below.

For example, if your Hugo project looks like this:

```
.
├── archetypes
├── assets
│   ├── css
│   └── images
│       └── something
│           ├── test1.png
│           ├── test1.png.meta
├── config.toml
├── content
│   ├── gallery
│   │   └── index.md
│   ├── news
│   │   ├── some_news
│   │   │   └── index.md
├── static
└── themes
```

In both `content/gallery/index.md` and `content/news/some_news/index.md` you can then include the following:

```
{{<gallery
    globalMatch="images/something/*"
    sortOrder="asc"
    rowHeight="150"
    margins="5"
    thumbnailResizeOptions="600x600 q90 Lanczos"
    showExif=true
    previewType="blur"
    embedPreview=true
    loadJQuery=true
>}}
```

Note the `globalMatch` parameter, and the path `images/something/*` relative
to `/assets`.
Both pages will then render the same images. It's important that your repeating
images are placed under `/assets`, as this is what is considered as "global"
resources for Hugo. If both `match` and `globalMatch` parameters are present in
your shortcode, the priority is given to the local `match`.

## Sidecar files

The metadata embedded in a image can be extended/overshadowed by a metadata sidecar file. The file must have the same name as the image plus ".meta" (e.g. "image.jpg.meta"). The content has to be a *JSON* like:

```JSON
{
"Tags": ["macro","insect"],
"Title": "Maya the Bee",
"ColorLabels": "RG",
"Rating": 3
}
 ```

## Requirements

This component requires a Hugo **extended** version ≥ 0.132.0.

## Dependencies

The component uses (and includes) [*Justified Gallery*](http://miromannino.github.io/Justified-Gallery/)
to render the images between the text and [*Swipebox*](http://brutaldesign.github.io/swipebox/)
to show them full screen. These dependencies are included in this repository.

## Troubleshooting

When bigger galleries are processed it can be required to set Hugo's timeout property in the *config.toml* to a higher value:
```
timeout = 60000 # This is required for larger galleries to be build (60 sec)
```

