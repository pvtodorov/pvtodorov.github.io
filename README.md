# pvtodorov.github.io

Personal site. Built with [Hugo](https://gohugo.io), hosted on GitHub Pages,
rebuilt by GitHub Actions on every push to `main`.

Live at <https://pvtodorov.github.io>.

## Writing

Add a Markdown file under `content/notes/` and push. That's the whole workflow.

```bash
hugo new content notes/something-i-noticed.md
```

Front matter:

```yaml
---
title: "Title of the Note"
date: 2026-09-07
description: "One sentence, shown on the homepage and in search previews."
draft: false
---
```

- The URL comes from the filename — `content/notes/foo.md` becomes `/notes/foo/`
  — so it only changes if you rename the file. Add `slug: "some-url"` to the
  front matter to override it.
- `draft: true` keeps a note off the built site. `hugo server -D` shows drafts.
- The homepage is the reverse-chronological list of notes.

You can also write in the browser: add a `.md` file under `content/notes/` on
github.com and commit to `main`.

## Previewing locally

```bash
hugo server -D
```

Then open <http://localhost:1313>. Hugo rebuilds on save.

## Layout

```
content/                     your writing — everything else is machinery
assets/css/main.css          the entire design, ~230 lines
layouts/                     baseof, home, list, page, 404
hugo.toml                    config
.github/workflows/hugo.yaml  build + deploy
```

## Installing Hugo

Extended edition. The version is pinned in `.github/workflows/hugo.yaml`, so
keep the local one close to it.

```bash
brew install hugo            # macOS
sudo apt install hugo        # Debian/Ubuntu
```

## Privacy

No analytics, comments, forms, or third-party embeds — the site sets no cookies
and collects no visitor data, so there is nothing to disclose and no consent
banner to show. Adding analytics, a newsletter signup, or comments would change
that and would call for a privacy page.

## Custom domain

Put the bare domain in `static/CNAME`, point DNS at GitHub Pages, set the domain
under **Settings → Pages**, and update `baseURL` in `hugo.toml`.
