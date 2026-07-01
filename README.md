# Delta SIFY (Change in Scientific Importance for Youth)

Change in Scientific Importance for Youth, also known as "Delta SIFY," is a movement intended to provide immersive educational opportunities for students in underserved communities to explore the fields of STEM. We believe that access to a quality, fulfilling education should be a fundamental human right, not a privilege.

This repository houses the official website for Delta SIFY (deltasify.org). The website is a static site generated using [Hugo](https://gohugo.io/).

## Prerequisites & Installation

To run this project locally, you will need to install **Hugo Extended**.

### 1. Install Hugo Extended
The site relies on the extended version of Hugo to compile the styling properly. 
Navigate to the [official Hugo Installation page](https://gohugo.io/installation/) and follow the instructions to download the appropriate version of Hugo for your respective operating system.

You can verify your installation by running:
```bash
hugo version
```
*(Ensure the output includes `+extended`)*

### 2. Clone the Repository
Because the theme is tracked as a Git submodule, you must include the `--recurse-submodules` flag when cloning:
```bash
git clone --recurse-submodules https://github.com/deltasify/deltasify.git
cd deltasify
```

*(If you already cloned without the flag, you can fetch the theme by running `git submodule update --init --recursive`)*

### 3. Run Locally
To spin up a local development server with hot-reloading:
```bash
hugo server
```
Open your browser and navigate to `http://localhost:1313`.

---

## File Tree Structure

The project is structured according to Hugo's standard conventions, with a few custom directories tailored for our initiatives:

```
deltasify/
├── content/              # The actual markdown files that contain the text/data for the site
│   ├── initiatives/      # Markdown files for Science Olympiad and Math Mentoring
│   ├── archive/          # Markdown files for past Invitationals and events
│   └── _index.md         # The homepage content
├── layouts/              # HTML templates that define the layout and UI of the pages
│   ├── initiatives/      # Custom Bento Box templates (e.g. initiative-page.html, faq-page.html)
│   ├── archive/          # Custom templates for archive pages
│   └── _default/         # Default fallback templates
├── static/               # Static assets (images, logos, PDFs) that are served directly
├── themes/               # Contains the 'tailbliss' theme that the site builds upon
├── hugo.yaml             # Main configuration file for the site
└── README.md             # This file
```

---

## How to Update Page Content

We have specifically designed the codebase using a **Separation of Concerns** model. This means that maintainers **do not** need to edit HTML code to update the website! 

All content (text, links, accordion questions, and stats) is fully decoupled and lives in the Markdown (`.md`) files located in the `content/` folder.

### 1. The Front Matter (YAML)

At the very top of each `.md` file, you will see a section bounded by `---`. This is called the "front matter". 
We use custom YAML structures (like `initiative_details` or `archive_details`) to feed data directly into the UI components.

### 2. Updating a Page

The layout and visual display of a page are determined by its `layout` field in the front matter. To update any of these pages, simply open the Markdown file and follow the highly descriptive comments above each field in the YAML list. We support several specialized, extensible templates:

#### Initiative Pages (`layout: initiative-page`)
*Used by: `content/initiatives/scioly-coaching/_index.md`, `content/initiatives/math-mentoring.md`*
These pages feature a rich "Bento Box" UI. Inside the `initiative_details` block, you can configure `quick_links` (buttons), `main_intro` (title and main text), `stats` (large numbers), `content_blocks` (half-width text cards), and an optional `accordion` (for FAQs).

```yaml
initiative_details:
  main_intro:
    title: "Make a Real Impact"
  stats:
    - value: "Sept '26"
      label: "Start Date"
  content_blocks:
    - title: "Why Coach?"
      content: "This is your chance to make a real impact."
```

#### FAQ Pages (`layout: faq-page`)
*Used by: `content/initiatives/scioly-coaching/in-person.md`, `content/initiatives/scioly-coaching/resources.md`*
These pages are tailored for simple FAQ or Resources lists. Inside the `faq_details` block, you can configure an array of `items`, each requiring a `question` and `answer`. 

```yaml
faq_details:
  items:
    - question: "What is Science Olympiad?"
      answer: "Science Olympiad is a track-meet style academic competition."
    - question: "How will coaching work?"
      answer: "Coaches will be given a Google Meet link..."
```

#### Invitational Pages (`layout: invitational`)
*Used by: `content/initiatives/invitational.md`, `content/archive/invitational-*.md`*
These pages display event-specific data. Inside the `invitational_details` block, you can configure `quick_links`, `resources`, an embedded YouTube `video_url`, top `winners` for each division, and event `stats`.

```yaml
invitational_details:
  video_url: "https://www.youtube.com/embed/edDrQTAYTXc"
  winners:
    division_b:
      - "Sierra Vista Middle School"
      - "Kennedy Middle School"
```

#### Archive Pages (`layout: archive`)
*Used by: `content/archive/_index.md`*
This page displays lists of past events. Inside the `archive_details` block, you can configure multiple `sections`, where each section has a `title` and a list of `links`.

```yaml
archive_details:
  sections:
    - title: "UCR Highlander Invitational"
      links:
        - text: "2026 UCR Highlander Invitational"
          url: "/archive/invitational-26/"
```

### 3. Adding New Sections or Hiding Existing Ones

**Hiding Existing Sections:**
To hide any section across any template, simply delete it from the YAML front matter or comment it out (using `#`). The layout will intelligently adapt and resize the remaining components (using dynamic CSS variables) to perfectly fill the gap!

**Adding New Pages:**
- **Initiative Pages:** Create a new markdown file in `content/initiatives/`, copy the front matter from an existing file (like `math-mentoring.md`), and ensure `layout: initiative-page` is set. 
- **FAQ Pages:** Create a new markdown file in `content/initiatives/scioly-coaching/`, copy the front matter from an existing file (like `resources.md`), and ensure `layout: faq-page` is set.
- **Invitational Archives:** To add a new past invitational event, create a markdown file in `content/archive/` (e.g., `invitational-27.md`), copy the front matter from an existing archive (like `invitational-26.md`), and ensure `layout: invitational` is set. Be sure to also update the `archive_details` links in `content/archive/_index.md` to point to the new page!

**Adding Standard Formatting:**
You can use standard Markdown syntax (like `**bolding**`, `*italics*`, and `[links](url)`) inside most of the content bodies and accordion answers across all page types!

---

## Creating a Generic Blog Post

If you need to create a simple, generic text page (such as a blog post, announcement, or basic informational page), you can use the default `single.html` template. 

To create a new post:
1. Create a new markdown file in the `content/` folder (or a subfolder like `content/posts/`).
2. You do not need to specify a `layout` field—Hugo will automatically fall back to the generic `layouts/_default/single.html` for standard markdown pages!
3. Use the following front matter format:

```yaml
---
title: "Your Post Title Here"
featured_image: "images/your-banner-image.jpg"
---

Your markdown content goes here!
```

### Front Matter Fields for Generic Posts:
- `title`: The main headline of the post. This is rendered in a large, colored header block at the very top of the page.
- `featured_image`: *(Optional)* The path to an image file (e.g., inside the `assets/` or `static/` folder). The template will automatically optimize and resize this image into multiple resolutions (small, medium, large) and display it beautifully beneath the title.
- **Content Body:** Unlike the specialized templates that rely heavily on YAML fields, the `single.html` template simply takes whatever markdown text you write *below* the `---` block and renders it as the main article content!
