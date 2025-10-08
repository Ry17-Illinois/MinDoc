# MinDocMini - Single Page Setup
MinDocMini is a minimal computing platform for creating your own digital documentary editions. It makes it easy to quickly deploy a simple web page where you can display images of and text about your documentary material.

This ReadMe is meant to walk you through setting up your own digitial edition in a step by step fashion.
This ReadMe assumes that you do not have experience with github. If you are already familiar with GitHub you might skip some steps.

## MinDocMini Setup

1. Sign up for GitHub. You can sign up on this page by selecting the Sign Up button at the top of the page.

2. Establish a Repository with your Copy of MinDocMini in it.
   Scroll to the top of the screen until you find the 'Use this template' button. It will look like this:
    <img width="209" height="59" alt="image" src="https://github.com/user-attachments/assets/5b3fd054-33c7-421f-899f-1083ce44a9e6" />
 This button will provide you with two options. Choose "Create a New Repository" and move on to the next step.

4. Choose a name for your repository. A simple name is best.

5. Click "Create Repository"
   You should now have a repository attached to your GitHub account.
<img width="356" height="336" alt="image" src="https://github.com/user-attachments/assets/d8e095ca-4534-4730-82e2-0e467fc3ec93" />

**After this point you should work from your new repository**

6. Go to the Settings Tab and Choose 'Pages.' Set the site to Deploy from Main Branch.


7. Return to this page 

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
{% include media_next.html pages=media %}
```

## Build
`bundle exec jekyll serve` - Preview locally
`bundle exec jekyll build` - Generate site
