# Drift

Research from 2factor finance.

This repo publishes essays and analytical pieces via GitHub Pages. Articles
are markdown files in the repo root with YAML front matter; Jekyll renders
them through `_layouts/article.html` with full OG metadata.

## Adding a new essay

1. Create `<slug>.md` in the repo root.
2. Add front matter:

   ```yaml
   ---
   layout: article
   title: "Article title"
   tagline: "One-line subtitle shown under the title."
   description: "Used as the OG description (link preview unfurl text)."
   image: https://path/to/og-image.png
   date: 2026-05-30
   permalink: /<slug>/
   ---
   ```

3. Write the article in markdown below. GitHub-flavored markdown is supported:
   tables, footnotes, fenced code, `<picture>` for dark/light variants, etc.
4. Commit and push. GitHub Pages auto-deploys.
5. Optionally: link the new article from `2factor.finance/research/` so it's
   discoverable from the main research landing.

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Serves at `http://localhost:4000`.

## Hosting

GitHub Pages publishes from `main` to `https://<username>.github.io/drift/`
by default. For custom domain (`drift.2factor.finance`):

1. Add `drift.2factor.finance` in Settings → Pages → Custom domain
2. Add DNS CNAME: `drift` → `<username>.github.io`
3. Wait for SSL provisioning (~10 min)

See `_config.yml` for site metadata.
