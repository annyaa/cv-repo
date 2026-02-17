# Ann Safo - Personal Website

This is my personal website built with [Quarto](https://quarto.org/), featuring my CV and blog. The site is automatically deployed to GitHub Pages via GitHub Actions whenever changes are pushed to the main branch.

## Features

- **CV Homepage**: Comprehensive overview of my education, research experience, and skills
- **Blog**: Posts about my research, computational biology, and graduate school experiences
- **Automatic Deployment**: GitHub Actions workflow builds and deploys the site automatically
- **Search**: Built-in search functionality to find content easily
- **RSS Feed**: Subscribe to blog updates via RSS

## Local Development

### Prerequisites

Install Quarto from [quarto.org](https://quarto.org/docs/get-started/)

### Commands

```bash
# Preview the site locally (with live reload)
quarto preview

# Build the site
quarto render

# Check the Quarto version
quarto --version
```

The preview command will start a local server (typically at http://localhost:4200) and automatically refresh when you make changes.

## Project Structure

```
.
├── _quarto.yml           # Main configuration
├── index.qmd             # Homepage (CV)
├── blog.qmd              # Blog listing page
├── posts/                # Blog posts
│   ├── _metadata.yml     # Shared post settings
│   └── YYYY-MM-DD-title/ # Individual post directories
│       └── index.qmd
└── .github/
    └── workflows/
        └── publish.yml    # GitHub Actions deployment
```

## Adding Blog Posts

1. Create a new directory under `posts/` with the format `YYYY-MM-DD-post-title/`
2. Add an `index.qmd` file in that directory with front matter:

```yaml
---
title: "Your Post Title"
author: "Ann Safo"
date: "YYYY-MM-DD"
categories: [category1, category2]
description: "Brief description of the post"
---
```

3. Write your content in Quarto Markdown
4. Commit and push - GitHub Actions will automatically deploy

## Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the `main` branch. The GitHub Actions workflow:

1. Checks out the repository
2. Sets up Quarto
3. Renders the site
4. Deploys to GitHub Pages

Make sure GitHub Pages is enabled in repository settings with source set to "GitHub Actions".

## Technologies

- **Quarto**: Modern scientific publishing system
- **GitHub Pages**: Free hosting for static sites
- **GitHub Actions**: Continuous deployment automation
- **Cosmo Theme**: Clean, professional Bootstrap-based theme

## License

© 2026 Ann Safo. All rights reserved.
