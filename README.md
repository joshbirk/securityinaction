# Salesforce Security Workshop — site

A Jekyll site built with the [Just the Docs](https://just-the-docs.com) theme, styled with a Salesforce-adjacent palette (Lightning blue, deep navy headings).

---

## Deploy to GitHub Pages — the reliable path

**Use GitHub Actions, not "Deploy from a branch".** The classic Pages builder has restrictions that often cause silent failures (missing styles, broken links). The included GitHub Actions workflow handles `baseurl` automatically and surfaces build errors so you can see what's wrong.

### Steps

1. Create a new GitHub repo and push this folder to the `main` branch:
   ```bash
   cd path/to/this/folder
   git init
   git add .
   git commit -m "Initial workshop site"
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
   git branch -M main
   git push -u origin main
   ```

2. On GitHub: **Settings → Pages**
   - **Source: GitHub Actions** ← critical, not "Deploy from a branch"

3. The workflow at `.github/workflows/pages.yml` runs automatically on push. Check the **Actions** tab to watch it build. The first run takes ~2 minutes.

4. When it succeeds, the deployment URL shows up in the Actions tab and under Settings → Pages.

### Why this works when the classic builder doesn't

The workflow line that fixes everything:

```yaml
- name: Build with Jekyll
  run: bundle exec jekyll build --baseurl "${{ steps.pages.outputs.base_path }}"
```

It auto-detects whether you're deploying to a user site (`username.github.io/`) or a project site (`username.github.io/repo-name/`) and sets `baseurl` accordingly. The classic builder doesn't do this, which is why CSS and links break.

---

## If something's broken, check these in order

**No CSS + every link 404s** → `baseurl` is wrong. The Actions workflow handles this; if you're using "Deploy from a branch" instead, you must manually set `baseurl: "/your-repo-name"` in `_config.yml`.

**Build fails in Actions tab** → click the failed run, expand "Build with Jekyll", read the error. Most common: a YAML front matter typo (an unquoted colon in a title, usually).

**Site builds but `View on GitHub` link is wrong** → edit `aux_links` in `_config.yml` to point to your actual repo.

**404 on a specific page** → check that page's front matter `parent:` matches the actual `title:` of its parent landing page exactly, including capitalization.

---

## What's here

```
.
├── _config.yml                          # Jekyll + just-the-docs config
├── Gemfile                              # Ruby deps for build
├── .github/workflows/pages.yml          # GitHub Actions deploy
├── _sass/custom/custom.scss             # Salesforce-blue palette + visual tweaks
├── index.md                             # Landing page (Getting Started)
├── overview.md                          # Data & Access overview
├── exercises/
│   ├── index.md                         # Exercises parent page
│   ├── 01-health-check.md
│   ├── 02-session-security.md
│   ├── 03-user-security.md
│   ├── 04-configure-health-check.md
│   ├── 05-fix-remaining-risks.md
│   └── 06-shield.md
├── appendix/
│   ├── index.md
│   └── baseline-xml.md
├── further-reading/
│   ├── index.md
│   ├── audit-trail.md
│   ├── security-hierarchy.md
│   ├── problem-users.md
│   └── experience-cloud.md
└── resources.md
```

Images live inline as base64 data URIs in each markdown file (single-file portability). Each section only carries the image refs it actually uses, so files range from 1.6 KB to 336 KB instead of every file being 1 MB.

---

## Run locally

```bash
bundle install
bundle exec jekyll serve --livereload
```

Then open <http://localhost:4000>. If you have Ruby version issues, the simplest path is `rbenv` or `mise`.

---

## Customizing

**Colors and visual tweaks:** edit `_sass/custom/custom.scss`. The variables at the top (`$sf-blue`, `$sf-navy`, etc.) drive everything.

**Adding a page:** create a new `.md` file with this front matter and you're done:

```yaml
---
title: My New Page
layout: default
parent: Exercises          # optional, omit for top-level
nav_order: 7
---
```

No need to register the page anywhere — just-the-docs picks it up from the front matter.

**Moving things around:** change `nav_order` and `parent` values. The sidebar rebuilds automatically.

**Internal links:** use `{% link path/to/file.md %}` instead of hardcoded URLs. The `link` tag always resolves to the correct path regardless of `baseurl`, so links never break when you change deploy targets.

```markdown
See [Exercise 3]({% link exercises/03-user-security.md %}) for details.
```
