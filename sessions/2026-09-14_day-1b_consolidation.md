# Day 1b — 2026-09-14 — Consolidation of Day-1 gaps

Status: complete

## Topics
- Re-teach of the 9 Day-1 gaps (A2, A4, A6, A7, A9, A10, B3, B4, B10)
- 10 new descriptive-stats questions (Block N) + 10 cumulative (Block C)

## Teaching notes (canonical)
- Plain-language re-teach of the Day-1 gaps:
  **`topics/01_descriptive_stats_distributions.md` → section 9 "Plain-English
  version"** (added Day 1b). Condensed: `cheatsheets/01_descriptive_stats.md`.
- This session file intentionally does **not** duplicate the lesson; the
  explanations live in the topic note (see `AGENTS.md` for the convention).

## Learning-method note
- **Added intervention:** teach in plain language first — plain words →
  technical term → interview line. User pushed back on the dense,
  textbook-style re-teach ("i need easy to understand, easy to remember
  lang"). (observation 0022)
- **Explain-back caught a wrong working model** that Day 1's definition
  question missed: the z-score was described correctly but the user
  believed it makes data normal. Application/transfer questions added to
  the assessment design. (observation 0023)

## Explain-back (after plain-language re-teach)

| # | Concept | Score | Note |
|---|---|---|---|
| A2 | Bessel n−1 | 5 | right instinct; said n−1 "introduces" bias (it removes it); said it bumps the mean (it bumps the variance) |
| A4 | Right-skew ordering | 7 | hostel analogy works; state full order mode<median<mean |
| A6 | z-score | 6 | scale intuition good; formula still missing |
| A9 | Kurtosis | 6 | core right; missed "extremes more likely than normal predicts" |
| A7 | Poisson | 5 | good examples; skipped mean=variance=λ |
| B3 | p-value | 0 | not attempted → re-taught |
| B4 | L1 vs L2 | 8 | strong mechanics + uses |
| A10 | Simpson's | 0 | not attempted → re-taught |
| B10 | CLT | 4 | described sampling; missed "sample mean → normal, any population" |

Explain-back sorted: 0,0,4,5,5,6,6,7,8 → **median 5/10**

## Block N — new questions (descriptive stats & distributions)

| # | Question | Score | Note |
|---|---|---|---|
| N1 | parameter vs statistic | 7 | correct population/sample split |
| N2 | mean=median=mode shape | 4 | said constant; missed symmetric + bimodal trap |
| N3 | std without "average" | 2 | described histogram shape, not spread |
| N4 | ÷n vs ÷(n−1) | 7 | correct direction; impact shrinks with n |
| N5 | coefficient of variation | 0 | no idea |
| N6 | "average session length" | 7 | right instinct: check median/mode/shape |
| N7 | IQR vs std | 4 | knew IQR + outlier rule; not the robustness contrast |
| N8 | right-skew transforms | 2 | proposed z-score to fix skew (WRONG) |
| N9 | Bernoulli/Binomial/Poisson | 1 | "count probability" — they count events |
| N10 | heavy-tailed | 6 | good example + median KPI; definition incomplete |

Sorted: 0,1,2,2,4,4,6,7,7,7 → **median 4.0/10**

## Block C — cumulative (all topics so far)

| # | Question | Score | Note |
|---|---|---|---|
| C1 | bias–variance | 3 | said perfect-train/bad-test = high bias AND high variance |
| C2 | cross-validation | 7 | estimates + tunes; doesn't guarantee unseen performance |
| C3 | p-value | 8 | precise enough — improved from 4 |
| C4 | Simpson's | 7 | concept right; example garbled |
| C5 | CLT | 3 | missed "sample mean"; empirical rule numbers wrong (60/95/99.8) |
| C6 | Poisson property | 8 | mean=variance; overdispersion → negative binomial |
| C7 | accuracy on imbalance | 8 | predicts one class; report P/R/F1 |
| C8 | sup vs unsup | 0 | said KNN unsupervised — still wrong (Day-1 gap) |
| C9 | tree vs KNN/GD scaling | 6 | trees/GD right; missed KNN |
| C10 | L1 vs L2 correlated | 3 | chose L1; correlated features → Ridge |

Sorted: 0,3,3,3,6,7,7,8,8,8 → **median 6.5/10**

## Overall
- New-question median: **4.0/10**; cumulative median: **6.5/10**
  (Day-1 baseline was 4.5 → cumulative breadth improved).
- Cleared: none (no item has ≥8 on two separate asks yet).
- Clearly improved: p-value (8), Poisson property (8), imbalance metrics (8),
  cross-validation (7), L1/L2 mechanics (8 on explain-back).
- Persisting misconceptions: z-score fixes skew; KNN is unsupervised;
  bias-variance direction; L1 for correlated features.

## Next
- **Day 2 — Probability**: conditional, Bayes, random variables,
  expectation/variance; simulate CLT.
- Weave still-open repairs into the cumulative block.
