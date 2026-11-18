# guertinlab.github.io

Guertin Lab website (genomics and gene regulation), at <https://guertinlab.github.io>.

## Editing

### pages


| File | Page |
| --- | --- |
| `index.md` | Home |
| `publications.md` | Publications (`/about/`) |
| `vignettes.md` | Analysis Vignettes |
| `lab-members.md` | Lab Members |
| `teaching.md` | Teaching |


### Add a publication

Edit `_data/publications.yml`:

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

Edit `lab-members.md`:

```html
<figure class="wp-block-image size-large">
  <img src="/wp-content/uploads/photo.jpg" alt="">
  <figcaption>Caption text</figcaption>
</figure>
```

### Change the navigation bar

Edit `_data/nav.yml` — once. 

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


