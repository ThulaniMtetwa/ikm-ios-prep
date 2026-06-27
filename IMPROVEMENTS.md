# IKM iOS Prep Console — Improvement Roadmap

Ideas to make the tool stand out and add real value to someone preparing for an
IKM-style iOS assessment.

The biggest gap today: the tool is **stateless**. Close the tab and every missed
question and every score is gone (only the theme persists). Most of the highest-value
improvements below close that gap — and none of them need a backend; they all use
`localStorage`.

---

## Tier 1 — Turn it into a study system, not just a quiz

Backed by how people actually learn for an exam. Self-contained, client-side only.

### 1. Persist progress + a "Review your mistakes" mode
- Track per-question outcomes (correct/incorrect, last seen, attempt count) across
  sessions in `localStorage`.
- Add a mode that re-serves **only the questions previously answered wrong**.
- **Why it matters:** the entire point of drilling is to revisit what you failed.
  Right now you can't — wrong answers vanish the moment you move on.

### 2. Adaptive weighting (lightweight spaced repetition)
- Replace pure random ordering with a weighted queue that favors weak topics and
  previously-missed questions; let mastered questions fade out of rotation.
- **Why it matters:** the drill should get harder where you're weak — which also
  mirrors the real IKM, a computer-adaptive test.

### 3. Stats dashboard on the menu
- Show best score, attempts over time, and a per-sub-skill mastery bar that persists
  between sessions.
- **Why it matters:** lets you watch the legacy/interop rows actually improve.
  Motivation and signal in one place.

---

## Tier 2 — Depth & authenticity

### 4. Add real code-snippet questions
- The engine **already supports them** (`if(q.code)` renders a `<pre class="code">`
  block) but no question uses it yet.
- Add "what does this code do / what's wrong with it" items: ARC retain cycles,
  Obj-C messaging, GCD deadlocks, optional unwrapping.
- **Why it matters:** real iOS assessments lean heavily on reading code. This makes
  the tool feel like the exam, not just trivia.

### 5. Grow the question bank & fix the mock count
- At ~45 questions the set is memorizable in a couple of runs.
- The "51-question, 61-minute" mock currently caps at `min(51, BANK.length)` and
  silently serves ~45, so the headline format isn't actually met.
- **Why it matters:** more questions fixes both realism and the memorization problem,
  and makes the advertised mock format true.

---

## Tier 3 — Polish that makes it feel premium

### 6. Keyboard shortcuts
- `A`–`D` to answer, `Enter` / `→` to advance.
- **Why it matters:** fast drilling is the difference between doing 20 questions and
  doing 200.

### 7. Flag / bookmark questions
- Let the user flag a question to revisit, plus an end-of-exam "review the ones you
  flagged or missed" screen.
- **Why it matters:** results currently show only aggregate per-topic scores — you
  never see the actual questions again.

---

## Suggested starting point

Start with **Tier 1** (persist progress + review-mistakes mode + adaptive weighting):

- Largest single jump in value.
- Self-contained.
- Everything else — the stats dashboard, flagging, code questions — builds naturally
  on the same saved-progress layer.

---

## Status legend

| Tier | Item | Status |
| ---- | ---- | ------ |
| 1 | Persist progress + review mistakes | ✅ Shipped |
| 1 | Adaptive weighting / spaced repetition | ✅ Shipped |
| 1 | Stats dashboard | ✅ Shipped |
| 2 | Code-snippet questions | Not started |
| 2 | Grow bank + fix mock count | Not started |
| 3 | Keyboard shortcuts | Not started |
| 3 | Flag / bookmark questions | Not started |
