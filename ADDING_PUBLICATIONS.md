How to add a publication
=========================

1. Create a new file in `_publications/` named `YYYY-MM-DD-short-slug.md` (the date can be the publication date; it only affects sort order).
2. Use this front matter template:

```
---
title: "Paper Title Goes Here"
collection: publications
category: manuscripts
permalink: /publication/short-slug
excerpt: "This is the blurb — write a sentence or two about the paper here. Markdown is fine."
date: 2026-01-01
venue: 'Journal or Conference Name'
paperurl: 'https://arxiv.org/abs/xxxx.xxxxx'
citation: 'Amaral, D. W. P. et al. (2026). "Paper Title." <i>Journal Name</i>.'
image: publications/short-slug.png
---
```

3. Drop the figure PNG in `images/publications/` with the filename you used for `image:` above. It'll render beside the blurb automatically on the Publications page.
4. Leave the body of the file empty (below the `---`) — the `excerpt` field is what's shown; the body only matters if you want extra content on the publication's own detail page.
5. `image` and `image_alt` (optional alt text) are the only fields specific to this figure layout; everything else (`citation`, `paperurl`, `slidesurl`, `bibtexurl`) works as in the standard academicpages template.
6. **`category` is required** — `_config.yml` groups publications under headings (`books`, `manuscripts`, or `conferences`) and silently drops any entry without a matching `category`. Use `manuscripts` for journal articles/preprints, `conferences` for conference proceedings, `books` for book chapters. To turn this grouping off entirely (single flat list, no headings, `category` becomes optional), delete the `publication_category` block from `_config.yml`.
