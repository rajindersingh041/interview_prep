# Day 1 — 2026-09-13 — Descriptive Stats & Distributions + Baseline Diagnostic

Status: complete (needs consolidation → see Day 1b)

## Topics
- Descriptive statistics & distributions (`topics/01_descriptive_stats_distributions.md`)
- Baseline diagnostic across stats/probability/ML

## Learning-method note
User self-reports poor retention: recognises terms, forgets "why".
Diagnosis: recognition reading, not understanding → no retrieval cues.
Countermeasures introduced: explain-back before quizzing, "because" chains,
retrieval practice over re-reading.

## Block A — Topic questions

| # | Question | Score | User answer (summary) | Feedback |
|---|---|---|---|---|
| A1 | mean/median/mode + when median | 7 | mean = sum/n; median = middle after sort, even → avg of middle two (deduced); mode = most frequent; median for outliers | Correct. Mode of all-distinct values = no mode. Be explicit on skew |
| A2 | why n−1 | 3 | "related to sample vs population; n is population, n−1 sample" (guess) | Bessel's correction: dividing by n underestimates population variance; n−1 makes it unbiased |
| A3 | std vs variance | 7 | std is same unit; variance abstract | Correct. Variance is squared units; std restores scale |
| A4 | right skew ordering | 5 | mean > median; mode unknown | Full order: mode < median < mean |
| A5 | IQR + outlier rule | 7 | Q3−Q1; outside Q1−1.5·IQR / Q3+1.5·IQR | Correct; knew from notes → aim to derive from "middle 50% spread" |
| A6 | z-score | 4 | standardizes, comparable across series | z = (x−μ)/σ; "number of SDs from mean"; formula missing |
| A7 | Poisson | 3 | good reading example | Mean = variance = λ; P(k)=λᵏe^−λ/k! |
| A8 | skewed feature handling | 4 | remove outliers | WRONG approach: use log/Box-Cox or robust scaling; do not delete without cause |
| A9 | kurtosis | 0 | no idea | Tail heaviness; normal kurtosis 3 (excess 0); fat tails → more extremes |
| A10 | Simpson's paradox | 0 | no idea | Aggregate trend reverses within subgroups; confounding |

Topic block sorted: 0,0,3,3,4,4,5,7,7,7 → **median 4/10**

## Block B — Baseline diagnostic

| # | Question | Score | Feedback |
|---|---|---|---|
| B1 | bias–variance | 4 | Described overfit gap; missing bias=underfit, variance=overfit, the trade-off |
| B2 | logreg vs tree | 1 | LogReg: linear, interpretable, calibrated; Tree: nonlinear, interactions, no scaling |
| B3 | p-value | 4 | Precision: P(data this extreme \| H0 true), not P(H0 true) |
| B4 | L1 vs L2 | 4 | L1=|w| sparse; L2=w² smooth shrinkage; both add a penalty term λ·penalty |
| B5 | cross-validation | 5 | Gives unbiased performance estimate; guards optimistic model selection |
| B6 | imbalance metrics | 6 | Good intuition (predict-all-majority); add F1, ROC-AUC, PR-AUC (best for heavy imbalance) |
| B7 | gradient descent | 7 | Strong: iterative, random init, LR, no global-min guarantee; add gradient = steepest ascent, step against it |
| B8 | overfitting fixes | 5 | CV detects, doesn't fix; use regularization, more data, simpler model, early stopping |
| B9 | sup vs unsup | 5 | KNN is SUPERVISED (labeled targets); unsupervised → clustering/PCA/autoencoders |
| B10 | CLT | 2 | Confused with empirical rule; CLT: sampling distribution of the mean → normal as n→∞, any population |

Baseline sorted: 1,2,4,4,4,5,5,5,6,7 → **median 4.5/10**

## Overall
- Topic median: **4/10**, Baseline median: **4.5/10**
- Strong signals: gradient descent, imbalance intuition, reasoning under uncertainty.
- Gaps to consolidate: Bessel, CLT, distributions, z-score, skew, kurtosis, p-value, L1/L2, supervised examples.

## Next
- **Day 1b (consolidation)**: re-teach A2, A4, A6, A7, A9, A10, B3, B4, B10 with "because" chains → new 10 questions + 10 cumulative.
- Then Day 2 (Probability) as planned.
