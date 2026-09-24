# Glossary

One row per term, grouped by the session that introduces it. The decks turn
every term here into a clickable definition automatically: run
`python3 scripts/build-glossary.py` after editing this file (it writes
`assets/glossary.js`), then `python3 scripts/check-glossary.py` to list
acronyms on the slides that are still undefined.

Rules for the build (see the top of scripts/build-glossary.py):
SKIP holds plain English words that must never be linked,
ONCE_PER_DECK holds common words linked once per deck, ALIASES holds other
spellings. Every other term is linked at its first use on every slide.

## Session 1 · Example

| Term | Plain definition |
|---|---|
| **Glossary** | The course's list of terms with plain definitions; the slides link to it automatically. |
| **HTML** | HyperText Markup Language: the text format web pages are written in. |
