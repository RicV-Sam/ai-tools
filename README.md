# AI Tool Radar

AI Tool Radar is a lightweight, static authority-style website for discovering, comparing, and understanding practical AI tools. It is built for GitHub Pages with plain HTML and CSS so it stays fast, easy to maintain, and easy to expand over time.

## Project goals

- Keep the site fast and static-first
- Make content easy to browse and easy to scale
- Support SEO with clean page structure, metadata, internal links, `robots.txt`, and `sitemap.xml`
- Use reusable layout patterns without introducing frameworks or build tooling

## Folder structure

```text
/
|-- 404.html
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
|-- blog/
|   `-- best-free-ai-tools-2026.html
`-- templates/
    `-- page-template.html
```

## How the site is organised

- `index.html` is the homepage and main discovery hub.
- `tools/` contains individual tool reviews or profile pages.
- `categories/` groups tools by workflow or use case.
- `compare/` contains side-by-side comparison pages.
- `best/` contains roundup pages for a specific audience or scenario.
- `blog/` contains editorial and SEO-focused informational content.
- `templates/page-template.html` is the starter pattern for future pages.
- `assets/css/style.css` stores the shared design system and reusable layout styles.

## Content workflow

1. Copy the closest existing page or start from [`templates/page-template.html`](templates/page-template.html).
2. Add a unique `<title>`, meta description, and H1.
3. Keep the same page shell:
   - Shared header and nav
   - Breadcrumb block
   - Intro panel with freshness signal
   - Main content sections using H2 headings
   - Related Pages block near the bottom
   - Shared footer
4. Add at least 3-4 relevant internal links so the page contributes to crawl depth.
5. Update `sitemap.xml` after publishing a new page.

## How to create a new tool page

1. Copy [`tools/chatgpt.html`](tools/chatgpt.html) or [`templates/page-template.html`](templates/page-template.html).
2. Save the new file inside `tools/` using a clear, lowercase filename such as `claude.html`.
3. Include the standard sections:
   - Intro
   - Quick summary
   - Best for
   - Pros
   - Limitations
   - Pricing
   - Alternatives or next options
   - CTA
   - Related Pages
4. Update the breadcrumb to `Home > Tools > Tool Name`.
5. Link to the new tool from a category page, a comparison page, the homepage, or a blog page.
6. Add the final URL to `sitemap.xml`.

## How to create a new category page

1. Copy [`categories/ai-writing-tools.html`](categories/ai-writing-tools.html) or the template file.
2. Save the new file inside `categories/` with a descriptive name such as `ai-research-tools.html`.
3. Include:
   - Intro
   - What the category includes
   - Featured tools
   - Who the category is for
   - Related Pages
4. Update the breadcrumb to `Home > Categories > Category Name`.
5. Link the category to at least one tool page, one comparison page, and one blog or best page.
6. Add the final URL to `sitemap.xml`.

## How to create a new blog page

1. Copy [`blog/best-free-ai-tools-2026.html`](blog/best-free-ai-tools-2026.html) or the template file.
2. Save the new file inside `blog/` with an SEO-friendly filename such as `best-ai-tools-for-freelancers.html`.
3. Include:
   - Intro
   - Clear H2-led article sections
   - Useful internal links inside the body copy
   - Related Pages at the bottom
4. Update the breadcrumb to `Home > Blog > Article Title`.
5. Link the article to a tool page, a category page, a comparison page, and a best page where relevant.
6. Add the final URL to `sitemap.xml`.

## How to update the sitemap

1. Open [`sitemap.xml`](sitemap.xml).
2. Add a new `<url>` block for each public page.
3. Keep URLs consistent with the GitHub Pages project path format:
- `https://ricv-sam.github.io/ai-tools/page-path`
4. Update `<lastmod>` when the page meaningfully changes.
5. Do not add utility pages such as `404.html` unless you have a specific indexing reason.

## How to keep internal linking clean

- Use relative links in HTML so the site works correctly on GitHub Pages project URLs.
- Make homepage sections point into deeper pages, not just broad hubs.
- Every internal page should link to a mix of:
  - A related tool or category page
  - A comparison page
  - A best page or blog page
- Keep anchor text clear and descriptive. Prefer `ChatGPT vs Claude` over generic wording like `click here`.
- When adding a new page, add at least one inbound link from an older page so the new URL is not isolated.

## How to update robots.txt when the GitHub Pages URL changes

1. Open [`robots.txt`](robots.txt).
2. Replace the placeholder sitemap URL with the final deployed GitHub Pages URL.
3. Make sure the sitemap path still ends in `/sitemap.xml`.
4. If the repo name changes, update both `robots.txt` and `sitemap.xml` together.

## GitHub Pages deployment

1. Push the repository to GitHub.
2. In the repository, open `Settings` -> `Pages`.
3. Under `Build and deployment`, choose `Deploy from a branch`.
4. Select your main branch and the `/ (root)` folder.
5. Save the settings and wait for GitHub Pages to publish the site.
6. After the site is live, replace the placeholder domain in:
   - `sitemap.xml`
   - `robots.txt`
   - Any future canonical tags you add later

## Notes for future expansion

- Keep internal links relative so the site works reliably on GitHub Pages project URLs.
- Reuse the existing section and card classes in `assets/css/style.css` before creating new patterns.
- Keep the freshness signal and Related Pages block on new public pages.
- If you later add JavaScript, keep it optional and progressive so the site remains usable as plain static HTML.
