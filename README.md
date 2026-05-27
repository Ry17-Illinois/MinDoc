# MinDoc: Create Your Own Digital Documentary Edition

## What is MinDoc?
MinDocMini is a minimal computing platform for creating your own digital documentary editions. It makes it easy to quickly deploy a simple static web page where you can display images and text about your project—no coding experience required. This template is designed for students, archivists, and researchers who want to publish digital editions online quickly and freely.


---

## Getting Started

This guide assumes you have **no prior GitHub experience**. If you're already familiar with GitHub, feel free to skip ahead. Typical technical information will be found below.

### Step 1: Create a GitHub Account
Sign up for a free GitHub account at [github.com](https://github.com) by selecting the **Sign Up** button at the top of the page.

### Step 2: Create Your Own Copy of MinDocMini
1. Scroll to the top of the MinDocMini template repository
2. Find the **"Use this template"** button (it looks like this):

<img width="209" height="59" alt="Use this template button" src="https://github.com/user-attachments/assets/5b3fd054-33c7-421f-899f-1083ce44a9e6" />

3. Click it and select **"Create a new repository"**

### Step 3: Name Your Repository
Choose a simple, descriptive name for your repository. The name you choose will become part of your website's URL so you might want to use a version of your publication's title. (e.g., `the-correspondance-of-george-washington-yyyy-yyyy`, `The-Epistolary-Presidency`, `scenes-from-mount-vernon`). A clear name helps others understand what your project contains. Repository names have some restrictions that might prevent you from using your publication's full title or using the exact title. It is possible to change the repository name later. 

### Step 4: Click "Create Repository"
You should now have your own copy of MinDoc attached to your GitHub account. You'll see a screen like this:

<img width="356" height="336" alt="Newly created repository" src="https://github.com/user-attachments/assets/d8e095ca-4534-4730-82e2-0e467fc3ec93" />

### Step 5: Enable GitHub Pages
1. Go to your new repository's **Settings** tab
2. Select **"Pages"** from the left menu
3. Under "Build and deployment," select **"Deploy from a branch"**
4. Choose **"Main"** as your branch

**Your site is now live!** GitHub will provide you with a URL (usually `yourname.github.io/repository-name`) where your digital edition will appear.

---

## How to Use MinDocMini

### Edit Your Site Title and Description
**File:** `_config.yml`

Open this file and update:
```yaml
title: Your Document Title
description: by Your Name
```
These yaml fields will modify the title and description fields on your web page.

### Add Your Main Content
**File:** `index.markdown`

This file contains all the text for your website. Use standard Markdown formatting:
- `# Heading` = Main section title
- `## Subheading` = Subsection
- `**Bold text**` for emphasis
- Write paragraphs normally

Example:
```markdown
# My Digital Edition

## Collection Overview
This collection includes photographs and documents from...

## First Section
Information about the first theme or time period.
```

### Add Images to Your Edition

#### 1. Upload Image Files
Place your image files in the `assets/img/` folder. Use clear filenames (e.g., `letter-1850.jpg`, `photograph-main.png`).

#### 2. Create an Image Description File
For each image, create a new file in the `_mindoc_media/` folder with the same name but ending in `.md`

**Example:** `_mindoc_media/letter-1850.md`

```yaml
---
page: source  ## DO NOT CHANGE THIS FIELD
title: "My Image's Name" 
media_type: image

_title: Apple tree
description: Main page photo
creator: Unknown
_date: Unknown
rights: CC BY
type: A photo
source: somewhere
identifier: 
contributor:
format:
credit_(IPTC):
date_created_(IPTC):

_path: /assets/img/main_page.jpg ##This field should point to the IMAGE you want to bring into your web page.
order: '03' ##This field determines the order that the image will appear on the page. Start at 01, 02, 03... etc.
layout: image_description ##DO NOT CHANGE THIS FIELD
---

---
```

**What each field means:**
- `page:` - The section where this image appears (must match a section in your content)
- `media_type:` - Type of content (usually "image")
- `order:` - Display order (1 = first, 2 = second, etc.)

#### 3. Display Images in Your Content
In your `index.markdown` file, add this code where you want images to appear:

```liquid
{% assign media = site.mindoc_media | where: "page", "source" %}
{% include media_next.html pages=media %}
```
---

## Troubleshooting (FAQ & Common Issues)

**Q: My site isn't showing up**
- Wait 2-3 minutes after enabling GitHub Pages for the site to deploy
- Check that you selected "Main" branch in Settings > Pages

**Q: Images aren't displaying**
- Check that image filenames match exactly in your `.md` files
- Verify images are in the `assets/img/` folder
- Make sure the `page:` name in your image metadata matches your section name

**Q: How do I make edits after publishing?**
- Edit files directly in GitHub by clicking the pencil icon
- Changes deploy automatically within a few minutes

---

## For Educators: README Best Practices Demonstrated Here

This README demonstrates key elements that should appear in any good README:

1. **Clear Title & Overview** (lines 1-5) - Explains what the project is and who it's for
2. **Getting Started Guide** (lines 7-30) - Step-by-step instructions for beginners
3. **Usage Examples** (lines 32-70) - Shows how to actually use the tool with code examples
4. **Technical Reference** (lines 72-81) - Command line instructions for advanced users
5. **Troubleshooting** (lines 83-95) - Answers common questions and problems
6. **Clear Organization** - Sections use headers to make scanning easy

**When writing your own READMEs, include these elements to help others understand and use your project.**

---

## Credits

MinDocMini is built on [Jekyll](https://jekyllrb.com/), a static site generator.

For more help with Markdown, visit [Markdown Guide](https://www.markdownguide.org/).
