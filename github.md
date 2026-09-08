repo: ahmabboud/LebUniv_Course_Template
branch: main

## Last sync

date: 2026-09-07
status: **v1.1.0 committed locally, not pushed.** Run `git push origin main`.
direction: this project is the SOURCE. Seven defects were found downstream in
`ahmabboud/course_knowledge_representation` while building its Session 1 and
are now fixed here, where they belong.

### v1.1.0 — seven defects fixed in the shared assets

All were present in this repository from the initial commit, and all reproduced
in `lectures/kr-session-03.html`, this repo's own reference lecture.

| # | File | Defect |
|---|---|---|
| 1 | `lu.css` | `.lu-mcq__why{display:block}` beat the UA `[hidden]` rule, so unrevealed rationales kept their space |
| 2 | `lu.css` | `.lu-mcq__why` had no `grid-column`, landed in the 44px key column of `.lu-mcq__opt` and rendered one word per line at 44x462 instead of 691x54 |
| 3 | `lu.css` | `.lu-board` inside `.lu-walk__view` derived its height from `aspect-ratio` and covered the walkthrough caption bar |
| 4 | `lu.css` | `.lu-svg{height:auto}` outranked `.lu-board__edges{height:100%}` on source order, so diagram arrows drifted off the board |
| 5 | `lu.css` | Print: `.slide` stayed `height:900px; overflow:hidden`, and `.lu-print-notes` is a flex child inside it, so the handout cut ~237px off every slide with notes |
| 6 | `lu-deck.js` | On reload the poll marked whatever the student answered as `data-verdict="correct"`, ignoring `data-answer` |
| 7 | `sw.js` | Document fetches used the default cache mode, so "network first" was answered by the HTTP cache (`max-age=600`) and students were pinned to a stale lecture through reloads |

### Also in v1.1.0

- **`scripts/audit-deck.js`** — a console audit that measures what static checks
  cannot: overflow clean and revealed, `[hidden]` that does not hide, grid
  escapes, sub-20px text, node collisions, stray edge endpoints. Every defect
  above would have been caught by it.
- **`lu-deck.js` `auditOverflow()`** — warns in the console at load listing any
  slide whose content is being clipped, so it fails loudly for the author
  instead of silently for the student.
- **`AGENTS.md` §2b, "Seven traps this system has already shipped"** — the trap
  table, plus the two measurement rules (scaled vs unscaled units, and clearing
  `lu:` localStorage before taking a baseline) that cost the most time.
- **`AGENTS.md` accessibility section corrected.** It claimed study mode was the
  SC 1.4.10 reflow-conforming alternative. It is not: `.lu-selfstudy` leaves the
  deck `overflow:hidden`. The claim is now accurate and the gap is named.
- Asset query strings bumped to `v=1.1.0` across all HTML and `sw.js`.

### Known and deliberately not fixed

- **Study mode does not reflow.** Making the deck scroll in study mode changes
  how every deck behaves and is the owner's call, not a bug fix.
- **`.lu-walk__dot` is a 16x4px target**, under WCAG 2.5.8's 24px minimum.
  Widening it changes the look of every deck.
- **`<html class="lu-deck-page">`** is set on both lectures and defined nowhere.
  Harmless dead markup.

## Screen map

| Project file | Repo path once pushed | Built from |
|---|---|---|
| `index.html` | `index.html` | authored here |
| `design-system.html` | `design-system.html` | authored here |
| `lectures/kr-session-03.html` | `lectures/kr-session-03.html` | `uploads/LebUniv/Knowledge Representation/syllabus-source.json` (session 3) |
| `lectures/_template.html` | `lectures/_template.html` | authored here |
| `assets/lu.css` | `assets/lu.css` | authored here |
| `assets/lu-deck.js` | `assets/lu-deck.js` | authored here |
| `assets/sparql-lite.js` | `assets/sparql-lite.js` | authored here |
| `sw.js`, `manifest.webmanifest` | same | authored here |
| `.github/workflows/pages.yml` | same | authored here |

## Notes

- `uploads/LebUniv/` holds the source syllabi. Excluded from the intended push —
  course material, not template code.
- Asset links carry `?v=1.0.2`. Bump in all four HTML files and in `SHELL` in
  `sw.js` when `assets/` changes.
- The initial repository commit is recorded above so later syncs can diff
  against it.
