How to add a publication
=========================

1. Create a new file in `_publications/` named `YYYY-MM-DD-short-slug.md` (the date is just for reference — it doesn't affect sort order).
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
arxiv: 'xxxx.xxxxx'
citation: 'Amaral, D. W. P. et al. (2026). "Paper Title." <i>Journal Name</i>.'
image: publications/xxxx.xxxxx.png
---
```

3. Name the figure PNG after the arXiv number (e.g. `xxxx.xxxxx.png`) and drop it in `images/publications/`, matching the `image:` field above. The Publications page shows a two-column grid of cards — figure on top, title, then an arXiv link — so no blurb is shown there.
4. `excerpt` and the file body only appear on the publication's own detail page (linked from the card title), not on the listing grid — write them for that page, or leave them minimal.
5. **`arxiv` drives both the sort order and the card's link text.** The grid is sorted by `arxiv` descending (larger/newer arXiv numbers first), regardless of `date`. Set it to the paper's arXiv identifier (e.g. `'2608.20464'`), as a quoted string so it sorts correctly. If `arxiv` is omitted, the card falls back to parsing it out of `paperurl` (only works for `arxiv.org/abs/...` links) but won't be included in the sort — always set `arxiv` explicitly.
6. If there's no `arxiv` id at all (e.g. a journal-only entry), the card falls back to linking `paperurl` with the `venue` name, or just showing `venue` as text — but it will sort as if its arXiv number were blank/lowest, so place it manually if needed.
7. `image` and `image_alt` (optional alt text) are the only fields specific to this figure layout; everything else (`citation`, `paperurl`, `slidesurl`, `bibtexurl`) works as in the standard academicpages template.
8. `category` is optional and currently unused — the Publications page renders a single flat grid with no subheadings. If you want papers grouped under headings again (e.g. "Journal Articles" vs "Conference Papers"), add a `publication_category` block back to `_config.yml` (see git history for the old one) and set `category: manuscripts` / `conferences` / `books` on each entry — but note that with that block present, any entry missing a matching `category` is silently dropped from the page.
