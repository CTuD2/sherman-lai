# Sherman Lai — bio site

Static HTML/CSS. No build step, no framework, no monthly hosting cost.

## What's here

```
index.html                          Home / bio
research.html                       Practice philosophy + conference history
press.html                          Press archive timeline
articles/index.html                 Article listing
articles/ontario-tcm-regulation.html  Starter article (template for new posts)
css/style.css                       All styling
robots.txt / sitemap.xml            SEO plumbing
```

## Before you deploy

Every file has `https://shermanlai.com/...` as a placeholder domain in the
`<link rel="canonical">` tags, the JSON-LD, and `sitemap.xml`. Once you buy
the real domain, find-and-replace `shermanlai.com` across all files.

## Deploying (free, no monthly cost)

1. Buy the domain (Namecheap, Squarespace Domains, etc. — this is the only
   ongoing cost, typically renewed yearly).
2. Create a free [Cloudflare Pages](https://pages.cloudflare.com) account
   (GitHub Pages or Netlify work the same way).
3. Push this folder to a GitHub repo, or drag-and-drop the folder directly
   into Cloudflare Pages' deploy UI — no build command needed, since this is
   plain HTML.
4. In Cloudflare Pages, add your custom domain under the project's
   **Custom domains** tab. Cloudflare issues an SSL certificate automatically.
5. Done. Updates from here on are just pushing new/edited HTML files —
   each push republishes instantly, for free.

## Publishing a new weekly article

1. Duplicate `articles/ontario-tcm-regulation.html` and rename it, e.g.
   `articles/acupuncture-for-chronic-pain.html`.
2. Update: `<title>`, meta description, canonical URL, JSON-LD headline/date,
   the `<h1>`, and the body copy.
3. Add a new entry at the top of `articles/index.html` (copy the `<a
   class="article-row">` block, point the `href` at your new file, update
   title/excerpt/date).
4. Add the new URL to `sitemap.xml`.
5. Push. That's the whole workflow — no CMS, no login, no plugin updates.

## Content guardrails

Keep new articles anchored to what's verifiable: Sherman Lai's practice history,
credentials, community work, TCM/acupuncture education, and general health
information. Avoid restating specific disease-cure or outcome claims from
the internal clinical-observation documents (e.g. cancer, PSA, tumour
reduction) without legal review first — advertising a treatment as curing or
treating cancer directly to the public carries real regulatory risk in
Canada under the Food and Drugs Act, independent of how the underlying
practice is regarded. When referencing them, describe them as "clinical
observation reports" or "case series" rather than as clinical trials or
proof of efficacy.
