# Progress

> Session memory. Read this first when resuming on another device.

## Status

- **Current day:** 1b done (consolidation) — **next: Day 2 (Probability)**
- **Start date:** 2026-09-13
- **Pace:** 30-day sprint, ~2h/day, bundle allowed
- **Target role:** Data Scientist
- **Math ceiling:** intuition + interview-ready (no long derivations)

## Day log

| Day | Date | Topic(s) | Median score | Notes |
|----|------|----------|-------------|-------|
| 1 | 2026-09-13 | Descriptive stats & distributions + baseline diagnostic | 4.0 topic / 4.5 baseline | Needs consolidation; see `sessions/2026-09-13_day-01_descriptive-stats.md` |
| 1b | 2026-09-14 | Consolidation of Day-1 gaps + 10 new + 10 cumulative | 4.0 new / 6.5 cumulative | Cumulative breadth up from 4.5; no items cleared yet. `sessions/2026-09-14_day-1b_consolidation.md` |

## Topic mastery (/10)

| Topic | Median | Status |
|---|---|---|
| Descriptive stats & distributions | 4.0 | needs consolidation |
| Baseline / cumulative breadth | 6.5 | improving |

## Weak-area queue

> Items scoring < 7 are re-asked in the cumulative block until cleared.
> Clearance = ≥8 on two separate asks.

| Topic | Concept missing | Added | Cleared |
|---|---|---|---|
| Coefficient of variation | std/mean, unitless comparison | Day 1b | — |
| Supervised vs unsupervised | KNN is supervised | Day 1 | — |
| Discrete distributions | Bernoulli/Binomial/Poisson count events | Day 1b | — |
| Std definition | spread / typical distance from centre | Day 1b | — |
| Skew transforms | z-score does NOT fix skew; use log/Box-Cox/RobustScaler | Day 1b | — |
| Bias–variance | perfect-train/bad-test = low bias + high variance; remedies | Day 1 | — |
| CLT | sample-mean normality, any population; empirical rule 68/95/99.7 | Day 1 | — |
| L1 vs L2 | correlated features → Ridge, not Lasso | Day 1 | — |
| Bessel's correction (n−1) | removes bias; bumps variance, not the mean | Day 1 | — |
| Poisson | mean = variance = λ | Day 1 | — |
| Mean=median=mode | mirror of symmetry; bimodal can hide under it | Day 1b | — |
| IQR vs std | std blew up by outliers, IQR robust | Day 1b | — |
| z-score | formula (x−μ)/σ; meaning in SDs | Day 1 | — |
| Skew handling | don't delete outliers; transform | Day 1 | — |
| Kurtosis | tail heaviness; extremes > normal predicts | Day 1 | — |
| Simpson's paradox | groups not comparable; confounder | Day 1 | — |
| LogReg vs Decision Tree | choice criteria | Day 1 | — |
| Overfitting remedies | CV detects, doesn't fix | Day 1 | — |
| Cross-validation | estimate vs remedy | Day 1 | — |
| Skew ordering | mode < median < mean | Day 1 | — |
| p-value | precise definition | Day 1 | — |
| Heavy-tailed | tails thicker than normal; KPI choice | Day 1b | — |
| Decision-tree/KNN/GD scaling | why each does/doesn't need scaling | Day 1b | — |

## Learning method (active interventions)

1. Explain-back in own words before any quiz.
2. Every fact gets a "because" chain.
3. Retrieval practice over re-reading; missed items re-asked from empty memory.
4. **Plain-language first (added Day 1b):** plain words → technical term →
   interview line. User rejected dense, textbook-style explanation.
5. **Application over definition (added Day 1b):** include transfer/apply
   questions, because a correct definition can sit on a wrong mental model
   (e.g. z-score believed to make data normal).

## Next up

1. **Day 2 — Probability**: conditional probability, Bayes, random variables,
   expectation/variance; hands-on: simulate CLT.
2. Weave open repairs (weak-area queue) into the cumulative block; prioritise
   the 0–3 scores first.

## Diagnostics snapshot

- **Strengths:** p-value definition; Poisson property; imbalance metrics;
  cross-validation purpose; L1/L2 mechanics; reasoning under uncertainty.
- **Gaps:** foundational definitions under application (std, CV, discrete
  distribution units), z-score vs skew misconception, supervised examples
  (KNN), bias–variance direction, L1–L2 trade-off under correlation.
- **Plan adjustments:** Day 1b inserted and completed; learning-method
  interventions now include plain-language-first and application questions;
  retain 30-day structure, expect 1–2 half-day buffers.
