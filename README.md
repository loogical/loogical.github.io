# Loogical

Official website for Loogical — an independent tech lab building tools and services for cybersecurity, AI, mobile, and cloud.

**Live site:** https://loogical.com

Built with plain HTML/CSS, hosted on GitHub Pages with a custom domain.

## Structure

```
/
├── index.html               # Landing page
├── privacy.html             # Privacy policy index (links to per-app pages)
├── style.css                # Shared styles
├── logo.png                 # Loogical logo (symlink → graphics/logo512_low.png)
├── privacy/
│   └── vulnscout.html       # Privacy policy for VulnScout (Android)
│
└── graphics/                # Full-resolution source assets
    ├── logo512.png          # App icon — 512×512 px
    ├── logo512_low.png      # App icon compressed — 512×512 px, ≤1 MB
    ├── header_image.png     # Header image original
    └── header_image_low.png # Header image compressed — 4096×2304 px, ≤2 MB
```

## Privacy Policies

Each app has its own dedicated page:

| App | URL |
|---|---|
| VulnScout (Android) | `https://loogical.github.io/privacy/vulnscout.html` |

To add a new app policy, create `privacy/<app-name>.html` and add a link card in `privacy.html`.

## Assets

Images are optimised for web use with ImageMagick:

```bash
# Compress logo (512×512, <1 MB)
magick source.png -resize 512x512 -strip -define png:compression-level=9 logo512_low.png

# Compress header (4096×2304, <2 MB)
magick source.png -resize 4096x2304! -strip -posterize 5 \
  -define png:compression-level=9 header_image_low.png
```