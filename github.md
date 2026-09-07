repo: ahmabboud/LebUniv_Course_Template
branch: main

## Last sync

date: 2026-09-07
commit: `f9c7182` (`Initial course template`)
status: pushed to `ahmabboud/LebUniv_Course_Template` on `main`.
direction: this project is the SOURCE. The design system, runtime and worked
example were authored here and published as the initial repository contents.

### Updated in this project

- Design system stylesheet, deck runtime and offline SPARQL engine authored in `assets/`.
- Worked example lecture: Knowledge Representation, Session 3 (21 slides).
- Empty lecture template, course index and design-system reference page.
- GitHub Pages workflow, PWA manifest and service worker.

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
