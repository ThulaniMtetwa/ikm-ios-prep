# IKM iOS Prep Console

A self-contained practice tool for an IKM-style **Apple iOS Application Programming**
(Objective-C + Swift) assessment. No build step, no dependencies, no accounts — a
single `index.html` you can open locally or host anywhere static. All progress is
stored privately in your browser.

**Live:** https://ikm-ios-prep.vercel.app

## Modes
- **Full mock** — weighted questions across all sub-skills, timed at 61 minutes,
  feedback at the end (exam mode).
- **Weak-area focus** — legacy + interop only, untimed, with instant explanations.
- **Review mistakes** — re-drills *only* the questions you've previously gotten
  wrong; the list shrinks as you master them.
- **Topic drill** — pick a single sub-skill and grind it with explanations and
  documentation links.

## Features
- **Progress that persists** (localStorage) — per-question outcomes, sub-skill
  mastery, and session history survive across visits. A menu dashboard shows your
  best score, sessions completed, how many questions are queued for review, and a
  per-sub-skill mastery bar (weakest first). Includes a reset control.
- **Adaptive ordering** — the queue is weighted toward weak topics, previously
  missed, and unseen questions; mastered questions fade out. Toggle off for plain
  shuffle.
- **Per-question documentation deep links** — every question links to the *specific*
  Apple / Swift documentation page for its subject (e.g. generics →
  the-swift-programming-language/generics/), surfaced prominently when you answer
  incorrectly so you can read up and lock it in.
- **Result profile** — weak / proficient / strong banding plus a per-sub-skill
  breakdown with documentation links for topics you missed.
- **Study vs. exam toggle**, answer shuffling, and a persisted **dark / light theme**.

The question bank deliberately overweights legacy and interop topics — manual memory
management, Obj-C messaging, Interface Builder, Core Animation/Quartz, and
Swift ↔ Objective-C bridging — since that's where an IKM iOS assessment probes hardest.

## Develop
Everything lives in `index.html` — markup, styles, and logic inline. Edit it and
refresh the browser; there is no build step.

## Deploy
Hosted on Vercel with Git auto-deploy: every push to `main` ships to production.

## Roadmap
See [IMPROVEMENTS.md](IMPROVEMENTS.md). Tier 1 (persistence, review mode, adaptive
ordering, dashboard) is shipped; Tier 2 (grow the bank, code-snippet questions) and
Tier 3 (keyboard shortcuts, flagging) are next.

## Feedback
The in-app "Share feedback" links (footer and results screen) point to a Google
Form. To change the destination, edit the `FEEDBACK_URL` constant near the top of
the `<script>` in `index.html` (leave it as the placeholder to hide the links).

---
Original practice content. Not affiliated with IKM / TeckChek.
