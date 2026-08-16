# Smart PLE — Upper Primary Practice App

A mobile-first UI/UX prototype of a PLE practice app for Upper Primary learners (P4–P7).

**Live:** deployed from `index.html` at the repository root.

## What this is
A single self-contained HTML file — no dependencies, no build step, no network calls.
System fonts, inline SVG icons, CSS animations. It runs offline from a phone's
Downloads folder exactly as it runs on a server.

## Screens
Home · Practice modes · Subject select · Topic select · Question · Answer feedback ·
Results · Review answers · Past Papers · Paper detail · Exam confirm · Exam question ·
Progress · Profile (+ avatar picker, offline manager, settings, about)

## Status
UI/UX structure and navigation only. **No academic content** — all questions, answers,
topics and paper names are placeholders. Real content drops into the `SUBJECTS`,
`MODES`, `PAPERS` and `topicsFor()` data blocks at the top of the script, with no
layout changes required.

See `DESIGN-NOTES.md` for design rationale.

## Run locally
Open `index.html` in any browser. That's it.
