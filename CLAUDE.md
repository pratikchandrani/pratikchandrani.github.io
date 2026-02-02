# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal website/blog built with Jekyll and Bootstrap for Pratik Chandrani, a Computational Biologist & Data Scientist. The site is hosted on GitHub Pages and includes research publications, blog posts, photography, music, and personal information.

## Development Commands

### Installation and Setup
```bash
make install  # Updates and installs Ruby dependencies via Bundler
make serve    # Runs local development server
```

Alternatively, you can use Jekyll commands directly:
```bash
bundle update
bundle install
bundle exec jekyll serve
```

The development server will be available at `http://localhost:4000` by default.

## Architecture

### Jekyll Configuration
- **Framework**: Jekyll 4.0.0 with kramdown markdown processor
- **Styling**: Bootstrap 4 (SCSS in `_sass/` directory)
- **Syntax Highlighting**: Rouge with GitHub Flavored Markdown
- **Site URL**: http://pratikchandrani.github.io

### Directory Structure

**Content Areas:**
- `_pages/`: Static pages (about, research, photography, index)
- `_posts/`: Blog posts directory (currently empty - add blog posts here)
- `_data/`: YAML data files for structured content
  - `publications.yml`: Research publications with authors, year, links
  - `pictures.yml`: Photography gallery data

**Templates:**
- `_layouts/`: Page templates (default, home, page, post)
- `_includes/`: Reusable HTML components
  - `sections/`: Major page sections (header, footer, head)
  - `components/`: Smaller reusable components (social, pagination, post_preview, etc.)

**Styling:**
- `_sass/`: SCSS stylesheets including Bootstrap components

### Key Features

**Blog System:**
- URL pattern: `/blog/YYYY/MM/DD/title/`
- Pagination enabled (5 posts per page)
- Disqus comments integration (shortname: pratikchandrani)
- Post excerpts enabled

**SEO & Analytics:**
- Google Analytics ID: G-Z7EKMZLYJ3
- Jekyll SEO tag plugin
- Sitemap generation
- Social media meta tags configured

**Plugins in Use:**
- jekyll-feed
- jekyll-sitemap
- jekyll-seo-tag
- jekyll-paginate
- jekyll-gist
- jekyll-redirect-from

### Content Management

**Adding Publications:**
Edit `_data/publications.yml` with the structure:
```yaml
- title: "Publication Title"
  authors: "Author Names"
  year: YYYY
  publication: https://link-to-paper
  code: https://github.com/repo (optional)
  url: https://project-website (optional)
```

**Adding Blog Posts:**
Create markdown files in `_posts/` with naming convention: `YYYY-MM-DD-title.md`

**Social Media Links:**
Configured in `_config.yml`:
- Twitter: @pratikchandrani
- GitHub: pratikchandrani
- LinkedIn: pratik-chandrani-phd-b550b5112
- YouTube: pratikchandrani
- Instagram: pratikchandrani
- Google Scholar: JALyxVsAAAAJ

## Important Notes

- The site uses a container with max-width of 900px for consistent layout
- All layouts inherit from `default.html` which includes header, content area, and footer
- Custom domain configured via CNAME file
- The website template was originally from Eric Daat (ericdaat.github.io) and has been adapted for Dr. Pratik Chandrani
