# Custom Jekyll Theme Usage & Extension Guide

This document describes how to use, maintain, and extend the custom Jekyll theme for Sean McCullough’s personal site.

## Directory Structure

- `_layouts/`: Page layouts (`default.html`, `landing.html`, `section.html`, `post.html`)
- `_includes/`: UI components (navigation, footer, section headers)
- `_sass/`: Modular Sass files for palette, typography, grid, and components
- `_data/`: YAML files for navigation and category metadata
- `assets/css/main.scss`: Main stylesheet importing all Sass modules
- `_posts/`: Blog, project, and talk posts (Markdown)

## Creating Content

- **Homepage:** Edit `index.md` (uses `landing` layout)
- **Section Pages:** Create or edit `about.md`, `cv.md`, `projects.md`, `blog.md`, `talks.md` (use `section` layout)
- **Posts:** Add Markdown files to `_posts/` with front matter specifying `layout: post` and a `categories` value (e.g., `blog`, `projects`, `talks`)

## Styling & Design

- All colours, fonts, and layout variables are in `_sass/_palette.scss` and `_sass/_typography.scss`
- Gutters and section accents are controlled by category in `_data/categories.yml`
- Underlines for headings and navigation are animated via CSS in `_sass/_components.scss`
- No SVGs are used for borders or dividers; all are CSS
- No border-radius, shadows, or gradients are permitted

## Navigation & Data

- Navigation links are defined in `_data/navigation.yml` and rendered via the `nav.html` include
- Section/category metadata (including accent colours) is in `_data/categories.yml`

## Extending the Theme

- To add a new section, create a new Markdown file with `layout: section` and add it to `navigation.yml` and `categories.yml`
- To add a new post type, update `categories.yml` and create a sample post in `_posts/`
- For new UI patterns, create a new include in `_includes/` and import it where needed
- For new styles, add to the appropriate Sass partial and import in `main.scss`

## Development Workflow

- Use `bundle exec jekyll serve --livereload` for local development
- All content and navigation should use relative URLs
- Do not expose contact information in any content
- Written language must be formal Australian English

## Placeholder Content

- All sample content is placeholder only; replace with real content as needed

---

For further customisation, follow the design and technical standards in `CLAUDE.md`.
