# Ann Safo - Personal Website & CV

[![Deploy Status](https://github.com/annyaa/cv-repo/actions/workflows/publish.yml/badge.svg)](https://github.com/annyaa/cv-repo/actions/workflows/publish.yml)
[![Quarto](https://img.shields.io/badge/Made%20with-Quarto-blue.svg)](https://quarto.org/)
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red.svg)](LICENSE)

> A modern, automated personal website showcasing my academic CV and research blog, built with Quarto and deployed via GitHub Actions.

**Live Site:** [https://annyaa.github.io/cv-repo/](https://annyaa.github.io/cv-repo/)

---

## Table of Contents

- [About](#about)
- [Features](#features)
- [Quick Start](#quick-start)
- [Installation](#installation)
- [Local Development](#local-development)
- [Project Structure](#project-structure)
- [Adding Content](#adding-content)
- [Customization](#customization)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Technologies](#technologies)
- [License](#license)

---

## About

This repository contains the source code for my personal academic website. The site features my curriculum vitae (CV) on the homepage and a blog where I share insights about my PhD research in Molecular, Cellular and Integrative Biosciences, computational biology methods, and graduate school experiences.

**Key Highlights:**
- PhD student at Pennsylvania State University
- Research focus: Aedes mosquito invasion dynamics
- Computational skills: R, Python, SAS, bioinformatics
- Former research intern at MIT and Johns Hopkins

---

## Features

### Professional CV
- Comprehensive overview of education, research experience, and skills
- Clean, academic-focused design
- Mobile-responsive layout
- Printable format

### Research Blog
- Markdown-based blog posts with scientific content support
- Category-based organization
- Recent posts section on homepage
- Full blog archive with search
- RSS/Atom feed for subscribers

### Automatic Deployment
- GitHub Actions CI/CD pipeline
- Automatic builds on every push to main
- Zero-downtime deployments
- Build status monitoring

### Enhanced User Experience
- Full-text search across all content
- Dark/light theme support (Cosmo theme)
- Responsive navigation
- Fast page loads (static site generation)

### Scientific Writing Support
- Code syntax highlighting
- LaTeX equation support
- Citation management
- Figure and table captioning
- Cross-referencing

---

## Quick Start

```bash
# Clone the repository
git clone https://github.com/annyaa/cv-repo.git
cd cv-repo

# Install Quarto (if not already installed)
# Visit: https://quarto.org/docs/get-started/

# Preview the site locally
quarto preview

# Build the site
quarto render
```

The site will be available at `http://localhost:4200` with live reload enabled.

---

## Installation

### Prerequisites

1. **Quarto** (version 1.3 or later)
   - **macOS:** `brew install quarto`
   - **Windows:** Download from [quarto.org](https://quarto.org/docs/get-started/)
   - **Linux:**
     ```bash
     wget https://github.com/quarto-dev/quarto-cli/releases/download/v1.4.550/quarto-1.4.550-linux-amd64.deb
     sudo dpkg -i quarto-1.4.550-linux-amd64.deb
     ```

2. **Git** (for version control)
   ```bash
   git --version  # Should be 2.0 or later
   ```

3. **Text Editor** (recommended)
   - VS Code with Quarto extension
   - RStudio (built-in Quarto support)
   - Any text editor of your choice

### Verify Installation

```bash
quarto check
```

This command verifies that Quarto is properly installed and shows available features.

---

## Local Development

### Basic Commands

```bash
# Preview site with live reload (recommended for development)
quarto preview

# Build site to _site/ directory
quarto render

# Clean build artifacts
quarto clean

# Check Quarto version
quarto --version

# Get help
quarto --help
```

### Development Workflow

1. **Start preview server:**
   ```bash
   quarto preview
   ```

2. **Edit content:**
   - Modify `.qmd` files in your editor
   - Changes automatically refresh in browser
   - No need to stop/restart server

3. **Test locally:**
   - Navigate to `http://localhost:4200`
   - Test all pages and links
   - Verify mobile responsiveness

4. **Commit changes:**
   ```bash
   git add .
   git commit -m "Description of changes"
   git push origin main
   ```

5. **Automatic deployment:**
   - GitHub Actions automatically builds and deploys
   - Check Actions tab for deployment status
   - Site updates in 2-3 minutes

### Preview Port Configuration

If port 4200 is in use, specify a different port:

```bash
quarto preview --port 8080
```

---

## Project Structure

```
cv-repo/
├── _quarto.yml                 # Main site configuration
├── _site/                      # Generated site (git-ignored)
├── .quarto/                    # Quarto cache (git-ignored)
│
├── index.qmd                   # Homepage (CV)
├── blog.qmd                    # Blog listing page
├── styles.css                  # Custom CSS styles
│
├── posts/                      # Blog posts directory
│   ├── _metadata.yml           # Shared post configuration
│   └── 2026-02-17-creating-this-website/
│       └── index.qmd           # Individual post
│
├── .github/
│   └── workflows/
│       └── publish.yml         # GitHub Actions deployment
│
├── .gitignore                  # Git ignore rules
└── README.md                   # This file
```

### Key Files Explained

- **`_quarto.yml`**: Main configuration file defining site structure, theme, navigation, and output settings
- **`index.qmd`**: CV homepage with personal information, education, research experience, and skills
- **`blog.qmd`**: Automated blog listing page that aggregates all posts
- **`posts/_metadata.yml`**: Default settings applied to all blog posts (author, freeze, etc.)
- **`styles.css`**: Custom CSS for additional styling beyond the theme
- **`.github/workflows/publish.yml`**: CI/CD pipeline for automated deployment

---

## Adding Content

### Creating a New Blog Post

1. **Create post directory:**
   ```bash
   mkdir -p posts/2026-02-20-my-new-post
   cd posts/2026-02-20-my-new-post
   ```

2. **Create `index.qmd` file:**
   ```yaml
   ---
   title: "My New Post Title"
   author: "Ann Safo"
   date: "2026-02-20"
   categories: [research, bioinformatics, R]
   description: "A brief description of what this post covers"
   image: "thumbnail.jpg"  # Optional preview image
   draft: false            # Set to true to hide from listings
   ---

   ## Introduction

   Your content here...

   ```{r}
   # R code blocks are supported
   library(ggplot2)
   ggplot(data, aes(x, y)) + geom_point()
   ```

   ## Conclusion

   More content...
   ```

3. **Add images (optional):**
   ```bash
   # Place images in the same directory
   cp ~/path/to/image.png posts/2026-02-20-my-new-post/
   ```

4. **Preview locally:**
   ```bash
   quarto preview
   ```

5. **Publish:**
   ```bash
   git add posts/2026-02-20-my-new-post
   git commit -m "Add new blog post: My New Post"
   git push origin main
   ```

### Updating Your CV

Edit `index.qmd` to update:
- Contact information
- Education history
- Research experience
- Skills and expertise
- Publications and presentations

```bash
# After editing
git add index.qmd
git commit -m "Update CV with new research position"
git push origin main
```

### Advanced Content Features

#### Adding Code Blocks

````markdown
```python
# Python code with syntax highlighting
import pandas as pd
df = pd.read_csv('data.csv')
```
````

#### Adding Equations

```markdown
Inline equation: $E = mc^2$

Display equation:
$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$
```

#### Adding Citations

1. Create `references.bib` file
2. Add to post front matter: `bibliography: references.bib`
3. Cite: `[@smith2023]`

#### Adding Figures

```markdown
![Caption for the figure](path/to/image.png){#fig-id}

See @fig-id for details.
```

---

## Customization

### Changing the Theme

Edit `_quarto.yml`:

```yaml
format:
  html:
    theme:
      - cosmo          # Try: flatly, journal, litera, lumen, minty, pulse, etc.
    css: styles.css
```

[Browse available themes](https://quarto.org/docs/output-formats/html-themes.html)

### Customizing Colors and Fonts

Edit `styles.css`:

```css
/* Change primary color */
h2 {
  color: #your-color-hex;
}

/* Change font */
body {
  font-family: 'Your Font', sans-serif;
}
```

### Modifying Navigation

Edit `_quarto.yml`:

```yaml
website:
  navbar:
    left:
      - text: "Home"
        href: index.qmd
      - text: "Blog"
        href: blog.qmd
      - text: "Publications"      # Add new page
        href: publications.qmd
      - text: "Contact"
        href: contact.qmd
```

### Adding Google Analytics

Edit `_quarto.yml`:

```yaml
website:
  google-analytics: "G-XXXXXXXXXX"
```

### Custom Domain

1. Add `CNAME` file to repository root:
   ```
   www.yourname.com
   ```

2. Configure DNS with your provider:
   - Add CNAME record pointing to `annyaa.github.io`

3. Enable custom domain in GitHub Settings → Pages

---

## Deployment

### Automatic Deployment (Recommended)

The site automatically deploys to GitHub Pages when you push to the `main` branch.

**Workflow:**
1. Push changes to GitHub
2. GitHub Actions triggers build
3. Quarto renders site to `_site/`
4. Artifact uploaded to GitHub Pages
5. Site goes live in 2-3 minutes

**Monitor Deployment:**
- Visit: https://github.com/annyaa/cv-repo/actions
- Check workflow status
- View deployment logs

### Manual Deployment

If you need to deploy manually:

```bash
# Render the site
quarto render

# The _site/ directory contains the complete website
# You can deploy it to any static hosting service
```

### GitHub Pages Configuration

**Required Settings:**

1. **Repository Settings → Pages:**
   - Source: **GitHub Actions** (not "Deploy from a branch")
   - Branch: Should show as deployed from `main`

2. **Repository Settings → Actions → General:**
   - Workflow permissions: **Read and write permissions**
   - Allow Actions to create and approve pull requests: **Checked**

### Deployment to Other Platforms

#### Netlify

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
quarto render
netlify deploy --dir=_site --prod
```

#### Vercel

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
quarto render
vercel --prod
```

---

## Troubleshooting

### Common Issues

#### Issue: Site not updating after push

**Solution:**
1. Check GitHub Actions tab for errors
2. Verify Pages source is set to "GitHub Actions"
3. Check workflow permissions
4. Try re-running the workflow

#### Issue: Quarto command not found

**Solution:**
```bash
# Verify installation
which quarto

# Reinstall if needed
# macOS: brew install quarto
# Or download from https://quarto.org
```

#### Issue: Port 4200 already in use

**Solution:**
```bash
# Use different port
quarto preview --port 8080

# Or kill existing process
lsof -ti:4200 | xargs kill -9
```

#### Issue: Blog posts not showing up

**Solution:**
1. Check file is named `index.qmd`
2. Verify directory structure: `posts/YYYY-MM-DD-title/index.qmd`
3. Ensure `draft: false` in front matter
4. Check date format: `YYYY-MM-DD`
5. Run `quarto render` and check for errors

#### Issue: Images not loading

**Solution:**
1. Use relative paths: `![](image.png)` not `![](/image.png)`
2. Place images in same directory as post
3. Check file names (case-sensitive on Linux)
4. Verify image formats (jpg, png, gif, svg)

#### Issue: Styles not applying

**Solution:**
1. Clear browser cache (Cmd/Ctrl + Shift + R)
2. Verify `styles.css` listed in `_quarto.yml`
3. Check CSS syntax for errors
4. Run `quarto clean` then `quarto render`

### Getting Help

- **Quarto Documentation:** https://quarto.org/docs/guide/
- **GitHub Discussions:** https://github.com/quarto-dev/quarto-cli/discussions
- **Stack Overflow:** Tag questions with `quarto`

### Debug Mode

Run Quarto in debug mode for detailed error messages:

```bash
quarto render --debug
```

---

## Technologies

### Core Technologies

| Technology | Purpose | Version |
|------------|---------|---------|
| [Quarto](https://quarto.org/) | Static site generator & scientific publishing | 1.3+ |
| [GitHub Actions](https://github.com/features/actions) | CI/CD & automated deployment | - |
| [GitHub Pages](https://pages.github.com/) | Static site hosting | - |

### Frameworks & Libraries

- **Bootstrap 5**: Responsive CSS framework (via Cosmo theme)
- **Pandoc**: Document conversion engine (bundled with Quarto)
- **Lua**: Quarto filters and extensions
- **YAML**: Configuration and metadata

### Development Tools

- **Git**: Version control
- **VS Code**: Recommended editor (with Quarto extension)
- **GitHub CLI**: Repository management (`gh` commands)

### Theme

- **Cosmo**: A clean, professional Bootstrap theme
  - Based on Bootstrap 5
  - Mobile-responsive
  - Accessible (WCAG 2.1 compliant)
  - Customizable via CSS

---

## Future Enhancements

Planned features and improvements:

- [ ] Add publications page with BibTeX integration
- [ ] Integrate Google Scholar profile
- [ ] Add teaching and presentations sections
- [ ] Implement comment system for blog posts
- [ ] Add dark mode toggle
- [ ] Create CV PDF download button
- [ ] Add research projects gallery
- [ ] Integrate ORCID and ResearchGate profiles
- [ ] Add site analytics dashboard

---

## Contributing

Suggestions and bug reports are welcome.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -m 'Add improvement'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

---

## License

© 2026 Ann Safo. All rights reserved.

The content of this website (text, images, and blog posts) is proprietary. The code structure and configuration may be referenced for educational purposes, but please create your own original content.

---

## Author

**Ann Safo, B.S.**
- PhD Student in Molecular, Cellular and Integrative Biosciences
- Pennsylvania State University
- Email: ays6029@psu.edu
- [LinkedIn](https://linkedin.com/in/ann-safo-b17b03252)
- [GitHub](https://github.com/annsafo)
- [Website](https://annyaa.github.io/cv-repo/)

---

## Acknowledgments

- Built with [Quarto](https://quarto.org/) by Posit
- Hosted on [GitHub Pages](https://pages.github.com/)
- Deployed via [GitHub Actions](https://github.com/features/actions)
- Theme: [Cosmo](https://bootswatch.com/cosmo/) from Bootswatch

---

*Last updated: February 2026*
