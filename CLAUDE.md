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
robots.txt              Allows all crawlers; points to the sitemap.
sitemap.xml             Hand-maintained list of published URLs (add new posts).
_config.yml             Jekyll config; `exclude:` keeps repo-only files (CLAUDE.md)
                        out of the *published* site (they stay in the repo).
Anatoliy_Babushka.webp  Profile/OG image.
fonts/
  inter-latin-var.woff2    Self-hosted Inter (variable, Latin subset, weights 100–900).
  inter-cyrillic-var.woff2 Self-hosted Inter (variable, Cyrillic subset, weights 100–900).
                           Used by /blog/ua/ pages; split from the Latin file via
                           unicode-range so Latin-only pages never fetch it.
blog/
  blog.css              Shared stylesheet for ALL blog pages, all languages (the only blog CSS).
  index.html            Blog landing page / post list (English).
  _template.html        Post template for ALL languages (see "Create a new blog post").
                        Not published. Do not duplicate this per language — see the
                        substitution table in that section instead.
  it/                   Italian posts + index.html. Same slugs as the English originals.
  ua/                   Ukrainian posts + index.html. Folder is named "ua", but pages use
                        lang="uk" (the correct ISO code — "ua" is only the folder name).
```

## Conventions & constraints

- **GitHub Pages + Jekyll (default).** There is no `.nojekyll`, so Jekyll
  processes the site and **ignores files/dirs beginning with `_`** (that's why
  `blog/_template.html` is not published). Plain HTML files are served verbatim.
- **Self-hosted Inter.** The font is served from `/fonts/inter-latin-var.woff2`
  and (for `/blog/ua/` pages) `/fonts/inter-cyrillic-var.woff2`, each declared
  as its own `@font-face` in `blog/blog.css` with a `unicode-range` scoping it
  to the scripts it covers, plus a matching `<link rel="preload" ...
  crossorigin>` in the `<head>` of pages that actually use that script — a
  Latin-only page must not preload the Cyrillic file, and vice versa. Both
  files are permanent self-hosted copies (originally sourced from Google
  Fonts' own per-script subsetting, then downloaded once and committed here);
  the site never makes a request to Google Fonts at runtime. Do **not**
  re-introduce Google Fonts `<link>`s — that was removed to kill a
  render-blocking request and the third-party request chain. If a future post
  needs another script (e.g. Greek), fetch that subset the same way: request
  `https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap`
  with a modern-browser `User-Agent`, take the woff2 URL and `unicode-range`
  for that script's `@font-face` block, download the file once, and add a new
  `@font-face` + preload pair — don't touch the existing Latin/Cyrillic files.
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
- **Keeping files off the published site.** Jekyll skips anything starting with
  `_` (e.g. `blog/_template.html`) or `.`, so
  those are never served. `CLAUDE.md` does **not** start with `_`, so it is kept
  out of the build via `_config.yml`'s `exclude:` list — add any other repo-only
  file there. This controls anatoliybabushka.com only; the GitHub repo is public,
  so these files stay visible at github.com (GitHub's own robots.txt keeps them
  out of search engines). Do **not** use `robots.txt` `Disallow` to hide files:
  it doesn't block access and only advertises the paths.

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
6. **Add the post to `sitemap.xml`:** copy a `<url>` block, set `<loc>` to the
   post URL and `<lastmod>` to the date.
7. **Commit and push.** GitHub Pages serves it at
   `https://anatoliybabushka.com/blog/<slug>.html`.

> The steps above are the mechanical scaffolding only. The writing itself follows
> the next section — and every lived specific in it comes from Anatoliy.

### Publishing the same post in Italian or Ukrainian

Same flow, same starting template (`blog/_template.html`) — there is no separate
`_template.html` per language; that duplication was tried and dropped because a
generic template can't hold real per-post values (canonical URL, date, hreflang)
anyway, so three copies just meant three places to forget to update. Output goes
to `blog/it/<slug>.html` or `blog/ua/<slug>.html` (same slug as the English
post, if one exists). Apply this substitution table on top of the normal steps:

| Field | English (template default) | Italian | Ukrainian |
|---|---|---|---|
| `<html lang="...">` | `en` | `it` | `uk` (not `ua` — that's only the folder name) |
| Back-link nav text / href | `← All posts` → `/blog/` | `← Tutti gli articoli` → `/blog/it/` | `← Усі статті` → `/blog/ua/` |
| Footer link text | `All posts` | `Tutti gli articoli` | `Усі статті` |
| Footer disclaimer | "The views here are my own, not those of any employer or client, past or present." | "Le opinioni espresse qui sono mie personali, non quelle di un datore di lavoro o cliente, passato o presente." | "Погляди, викладені тут, особисто мої, а не мого роботодавця чи клієнта, теперішнього чи колишнього." |
| `og:locale` | `en_US` | `it_IT` | `uk_UA` |
| Canonical / `og:url` base | `/blog/` | `/blog/it/` | `/blog/ua/` |
| Date example format | `January 1, 2026` | `1 gennaio 2026` | `1 січня 2026 р.` |
| Read-time label | `min read` | `min di lettura` | `хв читання` |
| Font preload | `inter-latin-var.woff2` only | `inter-latin-var.woff2` only | **both** `inter-latin-var.woff2` and `inter-cyrillic-var.woff2` (Ukrainian pages mix Cyrillic prose with Latin punctuation/the site name) |

**Translation quality** (learned the hard way on the first Italian/Ukrainian batch):

- **Translate intent, not words.** Rewrite each paragraph the way a native
  writer of that language would actually say it — restructure sentences, drop
  or add a clause, whatever natural phrasing needs. Never translate
  mechanically line-by-line; see the voice section below, same rule in any
  language.
- **Facts are locked, prose is free.** Every date, number, name, company, and
  external URL must match the source exactly. Only the surrounding sentences
  get rewritten — never invent or drop a detail to make one read better.
- **Keep loanwords a native speaker of that field would actually keep** (e.g.
  "rubber duck," "backlog," "PBI" stayed English in both translations) rather
  than forcing an awkward native coinage — but don't over-anglicize either.
  Judge each term on what that language's actual tech/leadership writers do.
- **Recompute read-time from the translated text**, not the English source's
  number — words ÷ 200, rounded up, min 1. Translated prose runs a different
  length than the original.
- **Always run a second, independent native-language review pass** in a fresh
  context (not the same agent/session that translated) before publishing. Its
  job: catch calques and translation-ese, and flag anything that breaks that
  language's own punctuation/register norms even where it's grammatically
  valid. Concretely: the first Ukrainian draft of these three posts used an
  em-dash every 25–35 words (32/24/23 per ~800-word post, versus 0–1 in the
  English source) — a habit English rhetorical style produces but native
  Ukrainian prose doesn't — and the review pass cut it roughly in half.
- **Don't use the `blog-post-reviewer` subagent on non-English drafts.** Its
  mechanical checkers and the skills behind them (`ai-tell-removal`'s banned
  word list, `prose-mechanics`' Flesch Reading Ease math) are English-only, and
  it can't fix what it finds anyway (no `Edit` tool). Use a general-purpose
  agent instead, briefed on that language's specific norms, with edit access
  to fix what it finds.

If the post exists in more than one language, add reciprocal
`<link rel="alternate" hreflang="en/it/uk/x-default">` tags (pointing at every
version's URL, including itself) and `og:locale:alternate` tags (the other two
locales) to **every** version's `<head>`, matching the pattern already on the
nine published posts. A post that only exists in one language needs neither.

## Writing a blog post (voice & site rules)

Draft with the `blog-post-author` subagent and review with `blog-post-reviewer`
(both user-level, in `~/.claude/agents/`). The generic writing craft lives in
user-level skills (`writing-substance`, `writing-structure`, `prose-mechanics`,
`writing-seo`, `ai-tell-removal`, `editing-passes`); those skills and agents are
site-agnostic and expect the site-specific facts below from this file.

- **Voice.** Write as Anatoliy: an engineering leader in Copenhagen who has led
  teams for more than a decade (Unity, Siteimprove, VML MAP) and still ships code
  (chartjs-php, 100k+ installs). Declarative and plain-spoken, concrete down to
  the example, confident without boasting. Show the work, never the title — a
  leader who still writes code is the main trust trigger, so ground points in
  real commits, code reviews, and maintenance burdens. Vary which proof appears;
  a credential or phrase repeated across posts becomes a tic.
- **Audience.** EMs, directors, senior+ engineers, and prospective clients sizing
  the author up — smart, short on time, skeptical of empty content on these
  topics.
- **Themes.** Three only: engineering leadership; moving AI from pilot to
  production; building software teams. Every post stays inside them and links at
  least two sibling posts.
- **Banned site phrases:** "let's connect," "create success together," stated
  client caps, urgency theatrics ("act now," "limited spots"), any
  self-promotional sign-off.
- **Provider-agnostic on AI tooling.** Lead with generic terms ("agent guide,"
  "agent-instructions file"). Name CLAUDE.md or AGENTS.md sparingly, as examples
  among others, never as the only option — in drafting, examples, and editing
  alike.
- **Locale:** US English throughout.
- **Readability lean:** Flesch Reading Ease 50–60 for deep technical posts,
  60–70 for broader leadership pieces.
- **Facts are Anatoliy's.** Every number, anecdote, and credential comes from
  him; agents never invent one — they leave a marked placeholder and ask.

## Deploy

Push to the default branch (`master`). GitHub Pages builds and serves
automatically; there is no separate deploy command.

## Verifying changes

There are no tests. Validate by checking against Lighthouse (Accessibility,
Performance, SEO, Best Practices) and confirming: contrast ≥ 4.5:1, valid heading
order, semantic landmarks, and no re-introduced render-blocking third-party
requests.
