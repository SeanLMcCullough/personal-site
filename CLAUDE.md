# Task

Refactor and overhaul the personal website of Senior Software Engineer Sean McCullough.

Develop a custom Jekyll theme to support the website, and create templates for different post types.

The website will have the following key areas:

- The home page, with the title, subtitle, and headings linking to other sections of the site
- About
- Career information / Curriculum Vitae outlining professional and personal experience
- Software and web development projects portfolio
- Blog posts and videos
- Talks and presentations

# Rules

- Develop using Jekyll for GitHub pages
- For any Javascript, use the Standard.JS linting standard
- Check if existing styles can be used before writing new styles. Refactor classes as neeeded for reuse.
- Write reusable templates and fragments to avoid code duplication
- Use consistent naming conventions
- Strictly use the provided styling rules in this file
- Use relative links and URLs to make hosting simple
- Do not expose contact information
- Written language: use formal Australian English. Avoid writing like an LLM. Avoid emdashes, avoid "it's not x, it's y" phrasing, and avoid fragmented paragraphing (Broetry / Staccato writing).
- Do not delete any existing written content without asking/checking. Relocate this content for later reuse if required.
- Write only placeholder content, real content will be written by humans.
- For different article/page types, create a sample article.

# Jekyll Development Standards: Custom Theme Architecture

This section defines the technical standards for maintaining and extending the custom Jekyll theme. Adhere to these conventions to ensure site performance, modularity, and data-driven content management.

## 1. Directory Structure & Convention
Follow standard Jekyll directory patterns to maintain compatibility and portability.
* **`_layouts/`**: High-level page structures. Use `default.html` for global `<head>` and script tags; use specific layouts (`landing.html`, `post.html`) for structural variations.
* **`_includes/`**: Atomic UI components (e.g., signage, navigation, footer, SVG icons). Pass data to includes via Liquid parameters: `{% include component.html param="value" %}`.
* **`_sass/`**: Modularized styling. Separate logic into `_palette.scss`, `_typography.scss`, `_grid.scss`, and `_components.scss`.
* **`_data/`**: Global configuration and content lists. Store non-post content (e.g., departmental categories, site navigation) in YAML files to avoid hardcoding in HTML.

## 2. Asset & Style Management
* **Sass Pipeline**: Utilize the built-in Jekyll Sass processor. Define variables in `_palette.scss` and import them into the primary `assets/css/main.scss`.
* **Vector Assets**: Prioritize SVGs for all icons, logos, and structural dividers. Embed SVGs or use `_includes` to allow for CSS-driven color manipulation.
* **Hard Geometry**: Enforce `border-radius: 0` globally. Use 1px solid borders for all containers and rules to maintain the clinical aesthetic.

## 3. Liquid Logic & Optimization
* **Data-Driven Loops**: Use Liquid to iterate through `_data` files for generating navigation and category sections.
* **Filtering**: Use `where` or `where_exp` filters to refine data sets before looping to minimize build times.
* **Front Matter Defaults**: Define global defaults in `_config.yml` (e.g., default layouts and authors) to keep Markdown files focused strictly on content data.

## 4. Development Workflow
* **Environment Variables**: Use `{% if jekyll.environment == "production" %}` to gate heavy assets, analytics, or experimental textures.
* **Local Serving**: Always execute with `--livereload` to monitor the precision of 1px alignments and gutter ratios in real-time.
* **DRY Principles**: If a UI pattern repeats, move it to an `_include`. If a string repeats, move it to `_config.yml` or `_data`.

# Design Language Brief: Clinical Mid-Century Bureaucracy

This document defines the visual constraints for the website redesign. The aesthetic is inspired by the television show *Severance*, characterized by a sterile, authoritative, and retro-dystopian corporate environment.

## Visual Philosophy
The design should evoke a sense of 1970s institutional precision. It is clinical, functional, and monolithic, utilizing aggressive minimalism to create a space that feels both expansive and highly controlled.

### Key Adjectives
* **Sterile & Clinical:** Use of cool, desaturated tones and vast, unoccupied space.
* **Authoritative:** Bold, geometric typography and rigid, unyielding layouts.
* **Bureaucratic:** Heavily structured information hierarchy, mimicking formal documentation and institutional signage.
* **High-Contrast:** Strategic use of deep, saturated accents against a desaturated base to signify hierarchy and urgency.
* **Analog-Digital Hybrid:** A flat UI that feels as though it is rendered on high-end legacy hardware—think cathode-ray tubes (CRT) and IBM terminals.
* **Texture** Surfaces such as the content areas and gutters will have subtle (almost indistinguisable) texture. For example paper or painted plasterboard for content, and a sublte texture of a leatherette desktop, felt pinboard, or office carpet. Use native CSS functionality to achieve this and make the pattern appear random and not repeated.

## Typography Matrix
Authority is established through varying widths and aggressive tracking (letter-spacing).

* **Headlines & Primary Titles:** Archivo Expanded (Medium). Set in uppercase with wide tracking (0.2em - 0.3em).
* **Subtitles & Categories:** Archivo SemiExpanded (Regular). Precise, geometric, and formal.
* **Body Content:** Figtree (Light/300). High line-height (1.6 - 1.8) to maintain a sparse, legible feel.
* **Code Blocks:** IBM Plex Mono. Unapologetically mechanical and industrial.

## Color Palette

| Role | Name | Hex | Usage |
| :--- | :--- | :--- | :--- |
| **Base** | Lumon White | `#F4F7F6` | Primary background. A cold, medicinal off-white. |
| **Base** | Deep Navy | `#1A232E` | Primary text and dark-surface backgrounds. |
| **Base** | Mid-Steel | `#5E6C77` | borders, rules, and secondary meta-text. |
| **Pop** | Data Blue | `#005CB9` | Technical elements, links, and system-level indicators. |
| **Pop** | Alarm Red | `#B22222` | High-urgency alerts and hover states for critical actions. |
| **Pop** | Handbook Green | `#004F32` | Structural gutters and compliance-related highlights. |
| **Pop** | Protocol Yellow | `#EAC435` | Primary Call-to-Action (CTA) elements. |

## Layout Constraints
* **Asymmetric Gutters:** The layout is framed by vertical gutters of Handbook Green (`#004F32`). The right gutter is thick; the left gutter is thin.
* **Centered Content Column:** All main content is center-justified within the white field between the gutters.
* **The Horizontal Rule:** Every category subheading must be followed by a solid horizontal rule in black. The thickness of this will match the type of the text.
* **Hard Geometry:** Strictly 90-degree angles. No rounded corners, soft shadows, or fluid gradients.
* **Vertical Dividers:** Use vertical left-side bars for primary titles to mimic institutional door signage.

## Section-Specific Accents
Apply accent colors to categories to maintain departmental distinction:

* **Tenure and Standing (CV/Experience):** Utilize Mid-Steel (`#5E6C77`) for a desaturated, archival look.
* **Logic and Implementation (Projects):** Utilize Data Blue (`#005CB9`) for technical and architectural focus.
* **Insight and Transmission (Blog/Video):** Primarily Deep Navy (`#1A232E`) and Mid-Steel (`#5E6C77`).
* **Seminar and Assembly (Talks/Presentations):** Utilize Data Blue (`#005CB9`) to imply instructional data transfer.
* **Global CTAs:** Use Data Blue (`#005CB9`) for all primary buttons, mimicking the high-visibility of an employee credential.

## Page layout

The homepage/landing page will be verticlly centered within the viewport. The headline "Sean McCullough" will be large. Directly below, the subtitle will read "Software Engineer". To the left of the heading and suheading will be a vertical black border of the same weight as the headline type. This is to represent the departmental badge style in Severance. All other page headlines / titles will have this same visual element of the left border / divider. The homepage will not have coloured gutters like other sections of the site.

All other pages will have a consistent document-like layout to match the visual style. These will feel like a typical beurecratic document in the Severance style.

The site will have left and right gutters. These gutters will be of the "accent colour" for the relevant section of the site. The left gutter will be narrow, and the right gutter will be wide. There will be sufficient whitespace between these gutters and the content such that the main content section is centered within the viewport. On small displays, the gutters will be the same size and narrow to not use too much space.

The main page content will have a maximum width for easy readability, and scale appropriately for small displays.