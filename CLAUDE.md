# CLAUDE.md

Guidance for working in this repository.

## What this is

Anatoliy Babushka's personal website — a static site hosted on **GitHub Pages**
at the custom domain **anatoliybabushka.com** (set via `CNAME`). It is a
positioning/SEO asset, so accessibility, performance, and clean semantic markup
matter.

**No build step, no frameworks, no JS bundlers.** Plain hand-written HTML + CSS.
You edit files and push; GitHub Pages serves them as-is.

## Layout

```
index.html              Homepage. Self-contained: inline styles + one <style> block.
CNAME                   Custom domain (anatoliybabushka.com).
Anatoliy_Babushka.webp  Profile/OG image.
fonts/
  inter-latin-var.woff2 Self-hosted Inter (variable, Latin subset, weights 100–900).
blog/
  blog.css              Shared stylesheet for ALL blog pages (the only blog CSS).
  index.html            Blog landing page / post list.
  _template.html        Post template (see "Create a new blog post"). Not published.
```

## Conventions & constraints

- **GitHub Pages + Jekyll (default).** There is no `.nojekyll`, so Jekyll
  processes the site and **ignores files/dirs beginning with `_`** (that's why
  `blog/_template.html` is not published). Plain HTML files are served verbatim.
- **Self-hosted Inter.** The font is served from `/fonts/inter-latin-var.woff2`
  via `@font-face` + a `<link rel="preload" ... crossorigin>`. Do **not**
  re-introduce Google Fonts `<link>`s — that was removed to kill a
  render-blocking request and the third-party request chain.
- **Homepage (`index.html`)** is styled with **inline styles** + a single
  `<style>` block holding `:root` CSS variables and `@font-face`. Keep its design
  byte-for-byte unless a change is explicitly requested.
- **Blog pages** use **one shared `blog/blog.css`** and **no inline styles** and
  no per-post CSS. Typography is research-backed: ~66ch measure, 1.125rem /
  1.65 line height, left-aligned (never justified).
- **Accessibility is non-negotiable (WCAG 2.1 AA).** Text contrast ≥ 4.5:1,
  headings in order (h1 → h2 → h3, no skipped levels), semantic elements
  (`header`, `main`, `nav`, `article`, `section`, `time`, `footer`), visible
  keyboard focus. The homepage `--faint` token is `#6b6b67` specifically so the
  small mono text passes 4.5:1 on the `#f6f6f4` background — don't lighten it.
- **Palette (shared):** `--bg #f6f6f4`, `--ink #101010`/`#1a1a1a`,
  `--muted #6e6e6c`/`#5a5a57`, `--line #dcdcd6`.
- **Analytics:** the same `gtag.js` snippet (property `G-WG97HS57JW`) loads
  `async` in the `<head>` of **every page** — the homepage and all blog pages
  (`blog/index.html`, each post, and `blog/_template.html` so new posts inherit
  it). Keep it identical across pages; leave it unless asked.
- **Email** in the homepage is assembled at runtime (`data-mail` + a small
  script) to keep it out of the page source — preserve that pattern.
- **Social/SEO meta.** Every page carries Open Graph + Twitter Card tags in
  `<head>` (homepage and all blog pages). Keep each post's `og:`/`twitter:`
  title and description in sync with its `<title>`/`<meta description>`.
  `og:image` is the shared `Anatoliy_Babushka.webp` (732×1000 portrait) until a
  per-post 1200×630 image exists.

## Create a new blog post

The publishing flow is "copy a file, write, push" — no generator, no front matter.

1. **Copy the template** to a slug-named file:
   `cp blog/_template.html blog/<slug>.html` (e.g. `blog/scaling-teams.html`).
2. **Update the `<head>`:** `<title>`, `<meta name="description">`, the
   `<link rel="canonical" href="https://anatoliybabushka.com/blog/<slug>.html">`,
   and the **Open Graph / Twitter tags** (`og:url`, `og:title`,
   `og:description`, `article:published_time`, `twitter:title`,
   `twitter:description`). **Remove** the `<meta name="robots" content="noindex">`
   line (it exists only to keep the template itself out of search).
3. **Update the post header:** the `<h1>` title, the `<time datetime="YYYY-MM-DD">`
   element (both the `datetime` attribute and the visible date text), and the
   **read-time estimate** that follows it (`· N min read`). Estimate it as
   **word count ÷ 200, rounded up** (min 1) — count the words inside `<article>`,
   ignoring HTML tags.
4. **Write the content** inside `<article>`, replacing the placeholder prose and
   **deleting the "Element reference" block**. Keep headings in order and use
   semantic elements; do not add inline styles or per-post CSS.
5. **Link it from the index:** in `blog/index.html`, copy the commented `<li>`
   template inside the post-list section, paste it at the **top** of
   `<ul class="post-list">` (newest first), and fill in the `href`, `datetime`,
   visible date, **read time** (same `· N min read` as the post header), title,
   and one-line summary. Remove the "No posts yet" `<li>` once there is a real
   post.
6. **Commit and push.** GitHub Pages serves it at
   `https://anatoliybabushka.com/blog/<slug>.html`.

> Content (the actual writing) is provided by Anatoliy — the steps above are the
> mechanical scaffolding only.

## Deploy

Push to the default branch (`master`). GitHub Pages builds and serves
automatically; there is no separate deploy command.

## Verifying changes

There are no tests. Validate by checking against Lighthouse (Accessibility,
Performance, SEO, Best Practices) and confirming: contrast ≥ 4.5:1, valid heading
order, semantic landmarks, and no re-introduced render-blocking third-party
requests.
