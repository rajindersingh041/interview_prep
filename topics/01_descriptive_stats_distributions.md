# Descriptive Statistics & Distributions

Day 1 topic. Interview-ready depth: explain clearly, know when each measure
is used, and handle the common traps.

## 1. The two jobs of descriptive stats

- **Central tendency** — where is the middle? (mean, median, mode)
- **Dispersion** — how spread out is it? (range, variance, std, IQR)

A number without a spread is half a story. Interview soundbite: *"I report
central tendency and dispersion together, because the mean of a bimodal or
skewed variable describes almost nobody in the dataset."*

## 2. Central tendency

| Measure | Definition | Use when | Weakness |
|---|---|---|---|
| Mean | sum / n | roughly symmetric, no extreme outliers | pulled by outliers |
| Median | 50th percentile | skewed data, outliers, income/latency | ignores magnitude of extremes |
| Mode | most frequent value | categorical data | can be non-unique/absent |
| Trimmed mean | mean after dropping top/bottom x% | robust central value | arbitrary trim choice |
| Geometric mean | nth root of product | growth rates, ratios, compounding | only positive values |

**Key interview point:** mean ≠ median signals skew. Right-skew (income,
house prices): mean > median. Left-skew: mean < median.

## 3. Dispersion

- **Variance** σ² = average squared deviation from the mean.
- **Standard deviation** σ = √variance, in the original units (why we
  usually report std, not variance).
- **Sample vs population:** sample variance divides by **n−1** (Bessel's
  correction) to make it an unbiased estimator of the population variance.
  Population variance divides by **N**.
- **Range** = max − min; very outlier-sensitive.
- **IQR** = Q3 − Q1; robust spread; basis of the boxplot.
- **Coefficient of variation** = σ/mean; unitless, compares variability
  across different scales.
- **Z-score** = (x − mean)/std; "how many std from the mean"; basis for
  standardization and outlier flags (|z| > 3).

**Outlier rule of thumb:** points below Q1 − 1.5·IQR or above Q3 + 1.5·IQR.
Not a law — it's a flag, not a deletion warrant.

## 4. Shape

- **Skewness** — asymmetry. ~0 symmetric; >0 right tail; <0 left tail.
- **Kurtosis** — tail heaviness / peakedness. Normal has kurtosis 3
  (excess kurtosis 0). High kurtosis ⇒ fat tails ⇒ more extreme events
  than a normal predicts (finance).
- **Bimodal / multimodal** — mean/median hide it; always plot.

## 5. Distributions to know

### Discrete
- **Bernoulli(p)** — one trial, 0/1. Mean p, var p(1−p).
- **Binomial(n, p)** — number of successes in n independent trials.
- **Poisson(λ)** — count of events in a fixed interval; mean = var = λ.
  Used for counts (arrivals, defects). If mean ≈ var, Poisson is plausible;
  var ≫ mean ⇒ overdispersion (use negative binomial).

### Continuous
- **Uniform(a, b)** — flat density.
- **Normal(μ, σ²)** — bell curve; empirical rule 68/95/99.7%; sum of many
  small independent effects (CLT).
- **Log-normal** — log is normal; right-skewed; income, prices.
- **Exponential(λ)** — waiting time between Poisson events; memoryless.
- **t-distribution** — normal-ish with fatter tails, used when σ is unknown
  and n is small; converges to normal as n grows.
- **Chi-square** — sum of squared normals; used for variance tests,
  goodness-of-fit.
- **F-distribution** — ratio of variances; basis of ANOVA, regression
  overall test.
- **Power law / Pareto** — heavy tail; a few observations dominate.

## 6. Why this matters in DS interviews

- EDA choice of summary stats depends on skew and outliers.
- Feature scaling (StandardScaler uses mean/std; RobustScaler uses
  median/IQR) is a distribution decision.
- Model assumptions: linear regression assumes roughly normal residuals;
  Poisson regression assumes mean ≈ variance.
- Metric distributions (revenue per user is heavy-tailed) determine whether
  mean, median, or a trimmed metric is the right KPI.

## 7. Common traps

1. **Simpson's paradox** — an aggregate trend reverses within subgroups.
2. **Mean of ratios ≠ ratio of means** — always average the ratio at the
   right unit (per user, not per event).
3. **Correlation ≠ causation** — confounding.
4. **Reporting only the mean** for skewed/heavy-tailed data.
5. **Dropping "outliers"** without a reason — they're often the signal.
6. **Sample vs population formulas** mixed up.

## 8. Interview framing (say it like this)

- *"For a skewed metric like session duration I'd lead with the median and
  IQR, and show the distribution, because the mean would overstate the
  typical user."*
- *"StandardScaler is fine when the feature is roughly normal; if it has
  heavy outliers I'd prefer RobustScaler based on median and IQR."*
- *"A z-score tells me how many standard deviations a point is from the
  mean, which is how I'd flag anomalies — but I'd validate any flagged
  point before acting on it."*
