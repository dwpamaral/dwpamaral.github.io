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
venue: 'Journal or Conference Name'          # once published, set to the Inspire-style ref, e.g. 'JCAP 06 (2026) 035'
paperurl: 'https://arxiv.org/abs/xxxx.xxxxx'
arxiv: 'xxxx.xxxxx'
doi: ''                                      # only once published — e.g. '10.1088/1475-7516/2026/06/035'
citation: 'Amaral, D. W. P. et al. (2026). "Paper Title." <i>Journal Name</i>.'
image: publications/xxxx.xxxxx.png
---
```

3. Name the figure PNG after the arXiv number (e.g. `xxxx.xxxxx.png`) and drop it in `images/publications/`, matching the `image:` field above. The Publications page shows a two-column grid of cards — figure on top, title, then a link (arXiv or DOI, see below) — so no blurb is shown there.
4. `excerpt` and the file body only appear on the publication's own detail page (linked from the card title), not on the listing grid — write them for that page, or leave them minimal.
5. **`arxiv` always drives the sort order**, published or not. The grid is sorted by `arxiv` descending (larger/newer arXiv numbers first), regardless of `date`. Set it to the paper's arXiv identifier (e.g. `'2608.20464'`), as a quoted string so it sorts correctly. Always set it explicitly — if omitted, the card can still fall back to parsing an id out of `paperurl`, but the entry won't be included in the sort.
6. **Once a paper is formally published (journal accepted it, has a DOI), add `doi` and set `venue` to the journal reference as it appears on Inspire** (e.g. `venue: 'JCAP 06 (2026) 035'`, `doi: '10.1088/1475-7516/2026/06/035'`). When `doi` is present, the card's link switches from the arXiv badge to `venue`, linking to `https://doi.org/<doi>` — i.e. published papers show their journal reference instead of the arXiv id. Keep `arxiv` set too, even after publication, since it still drives sort order and `paperurl` typically still points at the arXiv page. **Double check the journal reference/DOI against Inspire directly (or ask the user) rather than trusting a single automated lookup** — Inspire records for very recent papers can be inconsistent between fetches.
7. If there's no `arxiv` id at all (e.g. a journal-only entry with no preprint), the card falls back to linking `paperurl` with the `venue` name, or just showing `venue` as text — but it will sort as if its arXiv number were blank/lowest, so place it manually if needed.
7a. **Non-arXiv entries (e.g. a thesis) that still need a specific position in the grid**: set `arxiv` to a synthetic arXiv-shaped value chosen only to land it in the right sort position between two real entries (e.g. `'2200.00000'` to sit between `2104.03297` and `2302.12846`) — string comparison, so match the digit layout. Then set `link_text` (e.g. `'PhD Thesis'`) to override the card's link label/target entirely: it takes top priority over `doi`/`arxiv`/`venue`, links to `paperurl`, and shows that exact text instead of an arXiv badge.
8. `image` and `image_alt` (optional alt text) are the only fields specific to this figure layout; everything else (`citation`, `paperurl`, `slidesurl`, `bibtexurl`) works as in the standard academicpages template.
9. `category` is optional and currently unused — the Publications page renders a single flat grid with no subheadings. If you want papers grouped under headings again (e.g. "Journal Articles" vs "Conference Papers"), add a `publication_category` block back to `_config.yml` (see git history for the old one) and set `category: manuscripts` / `conferences` / `books` on each entry — but note that with that block present, any entry missing a matching `category` is silently dropped from the page.
