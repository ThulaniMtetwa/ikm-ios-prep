# IKM iOS Prep Console

A self-contained practice tool for an IKM-style **Apple iOS Application Programming**
(Objective-C + Swift) assessment. No build step, no dependencies — a single
`index.html` you can open locally or host anywhere static.

**Live:** https://ikm-ios-prep.vercel.app

## Features
- Three modes: **Full mock** (51 questions / 61 min, timed), **Weak-area focus**
  (legacy + interop), and **Topic drill** (one sub-skill with instant explanations).
- Study vs. exam feedback toggle and answer shuffling.
- Per-sub-skill result profile (weak / proficient / strong) with links to the
  official Apple / Swift documentation for any topic you missed.
- Dark / light theme (persisted).

The question bank deliberately overweights legacy and interop topics — manual memory
management, Obj-C messaging, Interface Builder, Core Animation/Quartz, and
Swift ↔ Objective-C bridging — since that's where an IKM iOS assessment probes hardest.

## Develop
Everything lives in `index.html`. Edit it and refresh the browser.

## Deploy
Hosted on Vercel with Git auto-deploy: every push to `main` ships to production.

## Roadmap
See [IMPROVEMENTS.md](IMPROVEMENTS.md).

## Feedback
Set `FEEDBACK_URL` near the top of the `<script>` in `index.html` to a Google Form
(or any) link to enable the in-app "Share feedback" links.

---
Original practice content. Not affiliated with IKM / TeckChek.
