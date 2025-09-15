# MinDocMini - Single Page Setup
MinDocMini is a minimal computing platform for creating your own digital documentary editions. It makes it easy to quickly deploy a simple web page where you can display images of and text about your documentary material.

This ReadMe is meant to walk you through setting up your own digitial edition in a step by step fashion.
This ReadMe assumes that you do not have experience with github. If you are already familiar with GitHub you might skip some steps.

## MinDocMini Setup

1. <AM CURRENTLY EDITING>

## Files to Edit

### Main Content
**Edit:** `index.markdown`
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
