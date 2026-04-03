# AI Tool Radar

AI Tool Radar is a lightweight, static authority-style website for discovering, comparing, and understanding practical AI tools. It is built for GitHub Pages with plain HTML and CSS so it stays fast, easy to maintain, and simple to expand over time.

## Project goals

- Keep the site fast and static-first
- Make content easy to browse and easy to scale
- Support SEO with clean page structure, metadata, internal links, `robots.txt`, and `sitemap.xml`
- Use a reusable layout system without introducing frameworks or build tooling

## Folder structure

```text
/
|-- index.html
|-- README.md
|-- robots.txt
|-- sitemap.xml
|-- assets/
|   |-- css/
|   |   `-- style.css
|   |-- js/
|   |   `-- .gitkeep
|   `-- images/
|       `-- .gitkeep
|-- tools/
|   `-- chatgpt.html
|-- categories/
|   `-- ai-writing-tools.html
|-- compare/
|   `-- chatgpt-vs-claude.html
|-- best/
|   `-- best-ai-tools-for-students.html
`-- blog/
    `-- best-free-ai-tools-2026.html
```

## How the site is organised

- `index.html` is the homepage and main discovery hub.
- `tools/` contains individual tool reviews or profile pages.
- `categories/` groups tools by workflow or use case.
- `compare/` contains side-by-side comparison pages.
- `best/` contains roundup pages for a specific audience or scenario.
- `blog/` contains editorial and SEO-focused informational content.
- `assets/css/style.css` stores the shared design system and reusable layout styles.

## How to add a new tool page

1. Copy the structure used in [`tools/chatgpt.html`](tools/chatgpt.html).
2. Save the new file inside `/tools/` using a clear, lowercase filename such as `claude.html`.
3. Add a unique `<title>` and meta description.
4. Keep the same content pattern:
   - Intro
   - Quick summary box
   - Best for
   - Pros
   - Limitations
   - Pricing
   - Alternatives
   - CTA and internal links
5. Link to the new page from relevant category, comparison, best, blog, or homepage sections.
6. Add the new page URL to `sitemap.xml`.

## How to add a category page

1. Copy the structure used in [`categories/ai-writing-tools.html`](categories/ai-writing-tools.html).
2. Save the new file inside `/categories/` with a descriptive name such as `ai-research-tools.html`.
3. Include:
   - Intro
   - What the category includes
   - Featured tools
   - Who the category is for
   - Internal links to related tool and blog pages
4. Add links from the homepage or any relevant content hubs.
5. Add the new page URL to `sitemap.xml`.

## How to update the sitemap

1. Open [`sitemap.xml`](sitemap.xml).
2. Add a new `<url>` block for each new page.
3. Update the `<loc>` value to the full deployed page URL.
4. Update `<lastmod>` when the page meaningfully changes.
5. If your final GitHub Pages URL differs from the placeholder domain, replace every base URL in the sitemap.

## GitHub Pages deployment

1. Push the repository to GitHub.
2. In the repository, open `Settings` -> `Pages`.
3. Under `Build and deployment`, choose `Deploy from a branch`.
4. Select your main branch and the `/ (root)` folder.
5. Save the settings and wait for GitHub Pages to publish the site.
6. After the site is live, replace the placeholder domain in:
   - `sitemap.xml`
   - `robots.txt`
   - Any future canonical tags you decide to add

## Notes for future expansion

- Keep internal links relative so the site works reliably on GitHub Pages project URLs.
- Reuse the existing section and card classes in `assets/css/style.css` before creating new patterns.
- If you later add JavaScript, keep it optional and progressive so the site remains usable as plain static HTML.
