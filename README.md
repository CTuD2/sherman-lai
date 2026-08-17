# Sherman Lai — bio site

Static HTML/CSS. No build step, no framework, no monthly hosting cost.
Deployed via GitHub Pages using GitHub Actions (see `.github/workflows/deploy.yml`).
Live domain: shermanlai.com (custom domain, configured via the `CNAME` file + DNS A records).

## What's here

```
index.html                                   Home / bio
research/index.html                          Practice philosophy + research bibliography
press/index.html                             Press archive timeline
articles/index.html                          Article listing
articles/ontario-tcm-regulation/index.html   Starter article (template for new posts)
css/style.css                                All styling
img/                                          Archival press photos
robots.txt / sitemap.xml                     SEO plumbing
CNAME                                         Custom domain config for GitHub Pages
.github/workflows/deploy.yml                 Auto-deploy on every push to main
```

## URL structure

Every page lives in its own folder as `index.html`, so URLs are clean —
`/research/` instead of `/research.html`, `/press/` instead of `/press.html`,
etc. This is why pages are nested in folders rather than sitting as flat
`.html` files at the root. All internal links use root-relative paths
(e.g. `href="/research/"`), so they work correctly on the custom domain.

## Analytics

- **GA4**: tag is already installed on every page (Measurement ID
  `G-693K942H4E`). Check Realtime reports in Google Analytics to confirm
  it's firing on the live site.
- **Search Console**: verified via DNS, so no HTML meta tag is needed.
  Sitemap (`sitemap.xml`) should be submitted under Search Console →
  Sitemaps.

## Publishing a new article

1. Create a new folder under `articles/`, e.g. `articles/acupuncture-for-chronic-pain/`,
   and put an `index.html` in it — easiest is to duplicate
   `articles/ontario-tcm-regulation/index.html` and adjust.
2. Update: `<title>`, meta description, canonical URL (`https://shermanlai.com/articles/your-new-slug/`),
   JSON-LD headline/date, the `<h1>`, and the body copy. Keep all internal
   links root-relative (starting with `/`).
3. Add a new entry at the top of `articles/index.html` (copy the
   `<a class="article-row">` block, point `href` at `your-new-slug/`,
   update title/excerpt/date).
4. Add the new URL to `sitemap.xml`.
5. Commit and push — the GitHub Action redeploys automatically within a
   minute or two.

## Content guardrails

Sherman Lai is retired (as of 2023) and the Centre of Integrative Natural
Medicine is no longer operating — the site is a historical/biographical
record, not an active practice or offer of treatment. Keep that framing
consistent in any new content: past tense, no implication he is currently
seeing patients, and a "not medical advice" disclaimer stays visible
(already in the footer of every page).

Cancer and other disease references are acceptable in this historical,
non-commercial context, but should stay factual and past-tense (what was
presented, studied, or observed) rather than framed as claims that any
formula currently treats or cures disease. Avoid featuring specific
products with a documented public controversy (e.g. PC-SPES, which was
subject to an FDA recall) without addressing that context directly, since
it can create a negative association rather than avoid one.
