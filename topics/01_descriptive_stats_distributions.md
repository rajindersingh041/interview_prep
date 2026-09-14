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

---

# 9. Plain-English version (added Day 1b)

The same topic in the learner's plain language: **plain words → because →
term → interview line**. Use this to revise; the sections above are the
reference version. Template: `topics/_TEMPLATE.md`.

## Variance & standard deviation

**In plain words:** Both answer "how spread out is the data?" Variance
squares the distances, so its unit goes weird (dollars²). Std takes the
square root, back into the original unit. **Std = the typical distance a
value sits from the centre.**

**Because:** Squaring makes big distances count far more, so both are
sensitive to outliers.

**The term:** `σ² = Σ(x − μ)² / N` (population); `s² = Σ(x − x̄)² / (n − 1)`
(sample); `σ = √σ²`.

**Interview line:** *"Std is the typical distance from the mean, in the
original units."*

## Bessel's correction (why n − 1)

**In plain words:** You measured spread around your *own* sample mean,
which sits closer to your data than the true mean — so the spread looks too
small. Dividing by **n − 1** (a smaller number) bumps the **variance** back
up to be unbiased.

**Because:** Estimating the mean from the same data consumes one degree of
freedom; with n = 1 you can't estimate spread at all.

**The term:** Sample variance divides by **n − 1**; population by **N**.

**Interview line:** *"We lose one degree of freedom to estimating the mean,
so we divide by n−1 to remove the bias."*

**Trap:** n−1 changes the **variance**, not the mean.

## Coefficient of variation

**In plain words:** `CV = std / mean`. Units cancel, so it's "how variable
am I relative to my size." Use it to compare variability across different
units or scales.

**Because:** Std in different units can't be compared directly; dividing by
the mean makes it unitless.

**The term:** `CV = σ / μ`.

**Interview line:** *"CV lets me compare spread across features with
different units."*

**Trap:** Not meaningful when the mean is near zero.

## IQR vs standard deviation

**In plain words:** IQR = **Q3 − Q1**, the spread of the middle half — it
ignores the tails. Std uses **every** value and squares deviations. Add one
billionaire to a salary dataset and std explodes while IQR barely moves.

**Because:** Squaring and using all points makes std sensitive to outliers;
IQR only looks at the middle 50%.

**Rule:** skewed/outlier data → median + IQR; clean symmetric data → mean + std.

**Interview line:** *"IQR is robust to outliers; std isn't."*

## Z-score

**In plain words:** A common language for values in different units — "how
far from average, measured in steps of typical spread." One step = one
standard deviation.

**Because:** Subtracting the mean centres at 0; dividing by std makes the
unit one standard deviation.

**The term:** `z = (x − μ) / σ`.

**Interview line:** *"A z-score is how many standard deviations a point is
from the mean."*

## Skew ordering

**In plain words:** One billionaire among nine $50k earners drags the
**mean** way up, barely moves the **median** (middle of the line), and
leaves the **mode** (most common) at $50k.

**Because:** The mean sums every value, so the tail contributes fully; the
median only counts position.

**The term:** Right skew: **mode < median < mean**. Left skew reverses.

**Interview line:** *"Mean > median means a right tail — the tail pulls the
mean, the median just counts positions."*

## Kurtosis

**In plain words:** How often wild extremes show up. A normal bell is the
baseline; higher means fat tails — 4-sigma days happen far more often than
the bell predicts.

**Because:** It measures the weight in the tails of the distribution, not
the peak.

**The term:** Normal kurtosis = 3; **excess kurtosis = kurtosis − 3 = 0**;
high kurtosis ⇒ fat tails ⇒ more extremes.

**Interview line:** *"High kurtosis warns that normal-based confidence
intervals understate tail risk."*

## Skew handling (how to actually fix it)

**In plain words:** Don't delete the tail — reshape it. A z-score only
shifts and rescales; the shape survives untouched.

**Because:** The skew lives in the shape, not the scale.

**The term:** `log(x)` (squashes big values → fixes right skew), `sqrt(x)`
(milder, counts), `Box-Cox` (auto-picks the power). For outliers only:
RobustScaler (median/IQR).

**Interview line:** *"To fix skew I'd use a log or Box-Cox; z-score only
standardizes the scale."*

**Trap:** z-score does NOT make data normal.

## Discrete distributions — what each counts

**In plain words:** They count **events**, not probability.

**Because:** Each answers a different counting/waiting question.

**The term:**
- **Bernoulli(p)** — one trial → 0/1. Mean p, variance p(1−p).
- **Binomial(n,p)** — successes in n trials. Mean np, variance np(1−p).
- **Poisson(λ)** — events in a fixed interval. **Mean = variance = λ.**

**Interview line:** *"Bernoulli one trial, Binomial successes out of n,
Poisson a count in a fixed window."*

## Poisson

**In plain words:** Counts of events in a fixed window (calls/hour, typos per
page). Its fingerprint: average equals spread.

**Because:** Independent events at a constant rate produce equal mean and
variance.

**The term:** `P(k) = λᵏe^−λ / k!`; mean = variance = λ. Variance ≫ mean ⇒
overdispersion ⇒ negative binomial.

**Interview line:** *"I check whether variance ≈ mean; if not, I use a
negative binomial."*

## p-value

**In plain words:** Flip a coin 100 times, get 60 heads. Assuming a fair
coin, how weird is that? The p-value is that weirdness score. It's about
the **data** being surprising, assuming the hypothesis — not the reverse.

**Because:** It's a probability of the data conditional on the null, so the
null is taken as given, not tested.

**The term:** `p = P(data this extreme | H₀ true)`.

**Interview line:** *"It's the probability of a result this extreme if the
null were true — not the probability the null is true."*

**Trap:** Not P(H₀ true); not effect size; 0.05 is a convention.

## L1 vs L2

**In plain words:** Both shrink coefficients to keep the model simple. L1
snaps weak features clean to **zero** (picks a subset); L2 shrinks
everything a bit but rarely to zero.

**Because:** L1's penalty takes a constant-size step, so the optimum lands
on corners (exact zeros); L2's penalty grows with coefficient size, so it
only shrinks.

**The term:** Add `λ·penalty` to the loss: **L1 = Σ|w|** (Lasso, sparse);
**L2 = Σw²** (Ridge, smooth).

**Interview line:** *"Lasso for feature selection; Ridge for stable
shrinkage — and with correlated features, Ridge, because Lasso picks one
arbitrarily."*

## Simpson's paradox

**In plain words:** A drug looks better overall, but split into mild and
severe patients it's worse in both — because it was mostly given to mild
patients. The overall number is faked by **who got what**.

**Because:** An unmodelled group difference (confounder) is unevenly
distributed across the comparison groups, reversing the aggregate trend.

**The term:** Aggregate trend reverses within subgroups; caused by a
confounder.

**Interview line:** *"Before trusting an aggregate comparison, I check
whether the groups differ in composition."*

## CLT vs empirical rule

**In plain words:** Roll one die — flat. Average 30 rolls, repeat thousands
of times — the **averages** form a bell, though raw rolls never did. That's
CLT. The empirical rule is different: how a single already-normal variable
spreads (68/95/99.7).

**Because:** Averaging cancels individual noise; the mean's randomness is
many small independent contributions.

**The term:** Sampling distribution of the sample mean → Normal as n grows,
any population; standard error = σ/√n.

**Interview line:** *"The sample mean is approximately normal for large n
whatever the population — that's why t-tests and CIs work."*

**Trap:** CLT is about the **mean's distribution**, not the raw data
becoming normal.
