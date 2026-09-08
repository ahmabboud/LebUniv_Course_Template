# LU Interactive Teaching Slides

Interactive, graphic-first HTML lectures for the Lebanese University. Static pages, no build step, deployable to GitHub Pages as-is.

- **`index.html`**, course index, links every lecture.
- **`design-system.html`**, the design system and a live gallery of all twelve interactive components. Start here.
- **`lectures/kr-session-03.html`**, the worked example: Knowledge Representation, Session 3, 21 slides.
- **`lectures/_template.html`**, copy this to start a new lecture.
- **`AGENTS.md`**, the authoring brief. Read it before writing a lecture, whether you are a person or an agent.
- **`PROMPT.md`**, the paste-ready brief for handing a new session to an agent, and the syllabus-field-to-slide mapping.

## What a lecture gives you

Presenter view on a second screen with speaker notes, elapsed time and pacing against the plan · deep-linkable slides (`#/12`) · contents panel and full-text search · a study mode that expands every popover, held-back answer and build step · one-page-per-slide printing with the instructor notes attached · offline support once installed · answers and position saved on the student's own device and never transmitted.

Twelve interactive components: term popovers, click-to-reveal, multiple choice with per-option rationales, step-through diagram walkthroughs, progressive builds, code blocks with copy and a sandboxed JavaScript runner, drag-to-order with a keyboard path, fill-in-the-blank, compare wipes, a live offline SPARQL sandbox, timed room polls, and an end-of-deck self-check.

## Run it locally

Open any HTML file directly in a browser. Everything works from `file://` except the offline service worker, which needs `http`. For that:

```
python3 -m http.server 8000
```

## Deploy

Enable GitHub Pages with **GitHub Actions** as the source, then push to `main`. `.github/workflows/pages.yml` uploads the repository unchanged.

## Before teaching from it

- Replace the `LU` placeholder in the lockup with the official crest at `assets/lu-crest.svg`. The mark in this repository is a typographic stand-in, not the university's emblem.
- Replace the `.lu-figure__ph` placeholders with real captures. Each one states the path and what must be visible.
- Optionally self-host the webfonts into `assets/fonts/` for a fully network-free deck (see `design-system.html` §3).

## Accessibility

Built to WCAG 2.2 AA, with the contract and one stated exception documented in `design-system.html` §10.

## Licence

Course content belongs to its authors. The template, stylesheet and runtime are yours to reuse and adapt.
