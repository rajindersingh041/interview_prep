# AGENTS.md

Guidance for AI agents working in this repo.

## What this repo is
A 30-day, ~2h/day ML/Data-Scientist interview-prep system, resumable from
any device via git. Read `progress.md` first, then `roadmap.md`.

## Teaching-notes convention (important)
Explanations are part of the deliverable, not just the Q&A.

- **Whenever a concept is taught, persist it to `topics/NN_<slug>.md`** in
  the plain-language shape defined by `topics/_TEMPLATE.md`:
  **In plain words → Because → The term → Interview line** (+ optional Trap).
- Keep **`cheatsheets/`** updated with the condensed formula/table version.
- **`sessions/`** files summarize what was taught and **link** to the topic
  note; do not duplicate the full lesson there.
- Write each teach block to disk **as it completes** (not only at day end),
  so nothing lives only in the chat transcript.
- **Commit** the teaching and assessment together after a session:
  `day-NN: <topic>` then push.

## Daily loop
1. Repair segment if the previous topic's median was < 7 (roadmap rule).
2. Teach the day's topic (plain-language format above).
3. Recall Q&A — 10 new questions on the most recent topic.
4. Cumulative Q&A — 10 across all topics, weighted to the weak-area queue.
5. Score each /10 (see README), update `questions/question-bank.md`,
   `progress.md`, `sessions/`, `topics/`, `cheatsheets/`.
6. Commit and push.

## Scoring
- 9–10 interview-ready · 7–8 solid · 5–6 partial · <5 needs re-teach.
- Weak items (score < 7) resurface in the cumulative block until cleared
  (cleared = ≥8 on two separate asks).
