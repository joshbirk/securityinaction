# Salesforce Security Workshop — site

A Jekyll site built with the [Just the Docs](https://just-the-docs.com) theme, styled with a clean Salesforce-adjacent palette.

## What's here

```
.
├── _config.yml                      # Jekyll + just-the-docs config
├── Gemfile                          # for local dev
├── _sass/
│   └── color_schemes/
│       └── salesforce.scss          # custom blue/navy color palette
├── index.md                         # landing page (Getting Started)
├── overview.md                      # Data & Access overview
├── exercises/
│   ├── index.md                     # exercises parent page
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

Images live inline as base64 data URIs in each markdown file (kept that way so each file is portable on its own). Each section only carries the image refs it actually uses.

## Deploy to GitHub Pages (the simple path)

1. Create a new GitHub repo, e.g. `salesforce-security-workshop`.
2. Push the contents of this folder to the `main` branch.
3. In the repo on GitHub: **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: `main` / root
4. Open the `_config.yml` and replace `YOUR-USERNAME/YOUR-REPO` in the `aux_links` section with your actual repo path.
5. If your repo is at `username.github.io/repo-name`, set `baseurl: "/repo-name"` in `_config.yml`. If it's a root user/org site (`username.github.io`), leave `baseurl: ""`.
6. Wait ~1 minute. The site builds automatically — `https://username.github.io/repo-name/`.

That's it. The `remote_theme: just-the-docs/just-the-docs` line tells GitHub Pages to fetch the theme on build, so no extra setup needed.

## Run locally

```bash
# install ruby + bundler first (most macs already have ruby; install bundler with `gem install bundler`)
bundle install
bundle exec jekyll serve --livereload
```

Then open `http://localhost:4000`.

## Tweaking the look

The color palette and small visual flourishes are all in `_sass/color_schemes/salesforce.scss`. Edit those variables and the site rebuilds. Common moves:

- **Change the brand blue:** edit `$blue-300` and `$body-link-color`.
- **Different heading color:** edit `$body-heading-color`.
- **More breathing room:** in just-the-docs, you can adjust the content container in `_sass` — or just override `.main-content { max-width: ... }`.
- **Different font:** add a `<link>` to a Google Font in `_includes/head_custom.html` (create that file), then set `$body-font-family` in `_sass/custom/setup.scss`.

## Tweaking the structure

To add or move pages, edit the YAML front matter at the top of each `.md` file. The keys that matter:

- `title:` — what shows in the sidebar and page header.
- `nav_order:` — sort order within the level.
- `parent:` — name of the parent page (must match its `title` exactly).
- `has_children: true` — declares this page is a section landing page.

To add a new page, just create a new `.md` file with front matter and the rest is automatic. No need to register it anywhere.

## Notes

- Search is enabled out of the box (top-right corner). just-the-docs builds the index at compile time, so it's fast and works offline.
- The `last_edit_timestamp: true` config will show the last-modified date at the bottom of each page once you've made commits to the repo.
- If something doesn't render, run `bundle exec jekyll build` locally and check the console for YAML errors — usually it's a colon in a title that needs quoting.
