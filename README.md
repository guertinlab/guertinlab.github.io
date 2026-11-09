# guertinlab.github.io

Static mirror of the Guertin Lab website (genomics and gene regulation),
served by GitHub Pages at <https://guertinlab.github.io>.

## What this is

A crawl of the previous WordPress 5.7 site (Twenty Ten theme) captured as plain
HTML/CSS/images, with all absolute `guertinlab.org` URLs rewritten to site-root
paths and WordPress-only endpoints (`xmlrpc.php`, `wp-json`, RSS feeds, oEmbed,
the emoji loader) removed. No database, no PHP, no hosting cost.

## Layout

| Path | Page |
| --- | --- |
| `index.html` | Home |
| `about/index.html` | Publications |
| `vignettes/index.html` | Analysis Vignettes |
| `lab-members/index.html` | Lab Members |
| `teaching/index.html` | Teaching |
| `wp-content/uploads/` | Images and PDF reprints |
| `wp-content/themes/twentyten/` | Theme stylesheets |
| `wp-includes/`, `wp-content/plugins/` | Supporting CSS/JS kept by the theme |

`.nojekyll` tells GitHub Pages to serve these files as-is rather than running
them through Jekyll.

## Editing

Each page is self-contained HTML, so the header and navigation bar are repeated
in all five files — a nav change has to be made in each. To edit:

- **In the browser** — open the file on GitHub, click the pencil, commit. The
  site rebuilds in under a minute.
- **Locally** — `git clone`, edit, `git push`.

Page text lives inside `<div class="entry-content">`; everything above it is
theme scaffolding.
