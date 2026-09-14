# Cheat Sheet — Descriptive Statistics

Fast revision. Full explanations: `topics/01_descriptive_stats_distributions.md`.

## Central tendency

| Measure | Formula / rule | Use when | Weakness |
|---|---|---|---|
| Mean | Σx / n | symmetric, no extreme outliers | pulled by outliers |
| Median | middle value (avg of two if even n) | skewed data, outliers | ignores magnitude of extremes |
| Mode | most frequent value | categorical | may be absent / non-unique |
| Trimmed mean | mean after dropping top/bottom x% | robust centre | arbitrary trim |
| Geometric mean | (∏x)^(1/n) | growth rates, ratios | positive values only |

**Skew:** right (long right tail) → **mode < median < mean**; left → mean < median < mode.

## Dispersion

| Measure | Formula | Note |
|---|---|---|
| Variance (sample) | Σ(x − x̄)² / (n − 1) | Bessel's correction |
| Variance (population) | Σ(x − μ)² / N | true parameters |
| Standard deviation | √variance | original units — report this |
| Range | max − min | very outlier-sensitive |
| IQR | Q3 − Q1 | robust; middle 50% |
| Coefficient of variation | std / mean | unitless; compares scales |
| Z-score | (x − μ) / σ | "how many SDs from the mean" |

**Outlier flag:** outside `Q1 − 1.5·IQR` or `Q3 + 1.5·IQR` — a flag, not a deletion warrant.

## Shape

- **Skewness** — asymmetry; ~0 symmetric, >0 right tail, <0 left tail.
- **Kurtosis** — tail heaviness; normal = 3, excess = kurtosis − 3 = 0;
  high kurtosis ⇒ fat tails ⇒ more extremes than normal predicts.

## Traps

1. Simpson's paradox — aggregate trend reverses within subgroups (confounder).
2. Mean of ratios ≠ ratio of means.
3. Correlation ≠ causation.
4. Reporting only the mean for skewed data.
5. Deleting "outliers" without a reason.
6. Mixing sample (n−1) and population (N) formulas.

## One-liners

- *"Mean and median disagree → skew."*
- *"IQR is robust to outliers; std isn't."*
- *"z-score standardizes scale; to fix skew I use a log or Box-Cox."*
- *"I report central tendency and dispersion together."*
