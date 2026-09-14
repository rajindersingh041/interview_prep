# ML / Data Scientist Interview Prep

A 30-day, 2h/day self-study system for classical ML, statistics, and DS
interview craft. Built to be resumed from any device via git.

## Goal

Be able to **explain** core ML topics in simple language, **go deeper on
demand**, and **answer interview questions** — without PhD-level math.
Target role: Data Scientist. Math ceiling: intuition + interview-ready.

## The daily loop (~2h)

1. **Teach** (35–45m) — plain English → why/assumptions → key formula(s)
   → when to use → pitfalls → how to say it in an interview.
2. **Recall Q&A — previous topic** (35m) — 10 *new* questions on the
   most recent topic (never asked before).
3. **Cumulative Q&A** (35m) — 10 questions across *all* topics so far,
   weighted toward weak areas (spaced repetition).
4. **Score & feedback** (5–10m) — each answer rated /10 with strengths
   and improvement areas; weak items go back in the queue.
5. **Commit** — `day-NN: <topic>` then push.

Multiple topics per day? Say **"bundle"** and we take 2 lighter topics;
the loop still runs, questions split across both.

## Repo map

| Path | What it holds |
|---|---|
| `roadmap.md` | The 30-day schedule and topic dependency map |
| `progress.md` | Session memory: day counter, mastery /10, weak-area queue |
| `sessions/` | One file per day: teaching notes + Q&A + scores |
| `topics/` | Canonical notes that grow across sessions |
| `questions/question-bank.md` | Every question asked, with scores and resurfacing status |
| `cheatsheets/` | Stats, metrics, algorithm-comparison, sklearn API |
| `code/` | From-scratch + sklearn implementations |
| `mocks/` | Mock interview transcripts and scores |

## Resuming on another device

```bash
git pull
# read progress.md -> "Next up" and the weak-area queue
```

After a session:

```bash
git add -A && git commit -m "day-NN: <topic>" && git push
```

## Session file naming

`sessions/YYYY-MM-DD_day-NN_<slug>.md`

## Teaching-notes convention

Explanations are part of the deliverable, not just the questions.

- Each taught concept is persisted to `topics/NN_<slug>.md` in the
  plain-language shape (see `topics/_TEMPLATE.md`):
  **In plain words → Because → The term → Interview line** (+ optional Trap).
- `cheatsheets/` holds the condensed formula/table version for fast revision.
- `sessions/` files summarize what was taught and **link** to the topic
  note; they don't duplicate the full lesson.
- Teach blocks are written to disk **as they complete**, so nothing lives
  only in the chat transcript.
- Agents: see `AGENTS.md` for the full convention and daily loop.

## Scoring convention

- **9–10** interview-ready: crisp, correct, includes a nuance or trade-off.
- **7–8** solid: correct core, missing depth or precision.
- **5–6** partial: right idea, gaps that would cost you in a real loop.
- **<5** needs re-teach: queued for cumulative questions.

Weak items (score < 7) resurface in the cumulative block until they clear.
