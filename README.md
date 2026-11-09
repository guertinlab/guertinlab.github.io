# guertinlab.github.io

Guertin Lab website (genomics and gene regulation), built by Jekyll and served
by GitHub Pages at <https://guertinlab.github.io>.

GitHub runs the build automatically on every push — there is nothing to install
and nothing to run locally.

## Editing

### Change wording on a page

Each page is a markdown file. Edit it on GitHub (pencil icon) and commit; the
site updates in about a minute.

| File | Page |
| --- | --- |
| `index.md` | Home |
| `publications.md` | Publications (`/about/`) |
| `vignettes.md` | Analysis Vignettes |
| `lab-members.md` | Lab Members |
| `teaching.md` | Teaching |

The block at the top between `---` lines is *front matter* — it sets the page
title and URL. Leave it alone; edit the text below it.

### Add a publication

Edit `_data/publications.yml`. Copy an existing block to the top and change the
fields — newest first:

```yaml
- title: "Paper title without a trailing period"
  journal: "Nucleic Acids Research"
  citation: "Author A, Author B, Guertin MJ 53: gkae1182, 2025."
  image: "/wp-content/uploads/2025/02/figure.png"
  links:
    - text: "PDF"
      url: "/wp-content/uploads/2025/02/paper.pdf"
```

`image` and `links` are optional; omit the lines entirely if there is no figure
or no PDF. To host the PDF here, upload it into `wp-content/uploads/` and point
`url` at that path. To link out instead (bioRxiv, a journal), use the full URL.

### Add an analysis vignette

Same pattern in `_data/vignettes.yml`.

### Add a lab member or a photo

Edit `lab-members.md`. Upload the image via **Add file → Upload files** into
`wp-content/uploads/`, then reference it:

```html
<figure class="wp-block-image size-large">
  <img src="/wp-content/uploads/photo.jpg" alt="">
  <figcaption>Caption text</figcaption>
</figure>
```

### Change the navigation bar

Edit `_data/nav.yml` — once. Every page picks it up. This was the main reason
for moving off the flat HTML mirror, where the nav was duplicated in all five
files.

## Layout of this repository

| Path | What it is |
| --- | --- |
| `_config.yml` | Site title, tagline, build settings |
| `_data/nav.yml` | Navigation menu |
| `_data/publications.yml` | The 27 publications |
| `_data/vignettes.yml` | The 4 analysis vignettes |
| `_layouts/default.html` | Shared page shell: head, logo, nav, footer |
| `_layouts/page.html` | Prose pages |
| `_layouts/publications.html` | Renders `_data/publications.yml` |
| `_layouts/vignettes.html` | Renders `_data/vignettes.yml` |
| `*.md` | Page content |
| `wp-content/`, `wp-includes/` | Images, PDFs, and the Twenty Ten stylesheet |

The styling is the original WordPress Twenty Ten theme CSS, carried over
unchanged, so the site looks the same as it did before the migration. Image and
PDF URLs were also left at their original paths, so any external link to a
hosted PDF still resolves.

## If a build fails

GitHub emails you and the site keeps serving the last good version. The usual
causes are a stray tab or a missing quote in a `.yml` file. Check the Actions
tab in this repo for the error, or revert the commit.
