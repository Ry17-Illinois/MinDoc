# MinDocMini - Single Page Setup

## Files to Edit

### Main Content
**Edit:** `index.md`
- Contains all page content in one file
- Use `# Header` for main sections
- Write content in standard markdown

### Site Settings
**Edit:** `_config.yml`
```yaml
title: Your Document Title
description: by Your Name
```

## Adding Images

### 1. Add Image Files
Place images in: `assets/img/your-image.jpg`

### 2. Create Image Description
Create file: `_mindoc_media/your-image.md`
```yaml
---
page: "section-name"
media_type: "image"
order: 1
---
![Description]({{ site.baseurl }}/assets/img/your-image.jpg)
```

### 3. Reference in Content
Add to `index.md` where you want the image:
```liquid
{% assign media = site.mindoc_media | where: "page", "section-name" %}
{% include media.html pages=media %}
```

## Build
`bundle exec jekyll serve` - Preview locally
`bundle exec jekyll build` - Generate site