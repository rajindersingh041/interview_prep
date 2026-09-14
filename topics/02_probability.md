# Probability

Day 2 topic. Interview-ready depth: conditional reasoning, Bayes, random
variables, expectation and variance. Format: **plain words → because →
term → interview line**.

## 1. What probability is

**In plain words:** A number from 0 to 1 answering "how often would this
happen if we repeated the situation forever." 0 = never, 1 = always. All
possible outcomes together add to 1.

**Because:** It's a long-run frequency; every outcome has to land somewhere,
so the full sample space sums to one.

**The term:** `P(not A) = 1 − P(A)`; `P(A or B) = P(A) + P(B) − P(A and B)`.

**Trap:** Add the two probabilities without subtracting the overlap once —
common "at least one" error.

**Interview line:** *"I'd compute it as 1 minus the probability of the
complement, which is usually easier."*

## 2. Conditional probability

**In plain words:** `P(A|B)` is the chance of A **given that we already
know B happened**. The "given B" shrinks the world to only the B cases.

**Because:** Conditioning divides by P(B), renormalising the sample space
down to just the outcomes where B is true.

**The term:** `P(A|B) = P(A and B) / P(B)`. Independent means knowing B
doesn't change A's chance: `P(A|B) = P(A)`, so `P(A and B) = P(A)·P(B)`.

**Trap:** Independent ≠ mutually exclusive. Mutually exclusive events
(can't both happen) are actually *maximally dependent* — if one occurs, the
other is impossible.

**Interview line:** *"Independence means the conditional equals the
marginal; mutual exclusivity is the opposite — it makes events fully
dependent."*

## 3. Bayes' theorem

**In plain words:** Bayes flips a conditional around. You know the chance
of a **test result given the disease**; Bayes gives the chance of the
**disease given the test result** — and those are wildly different.

**Because:** The denominator counts positives from *both* sick and healthy
people. When the disease is rare, false positives from the huge healthy
group dominate, so most positives are wrong.

**The term:** `P(H|D) = P(D|H)·P(H) / P(D)`.
- `P(H)` = prior (base rate)
- `P(D|H)` = likelihood
- `P(D)` = evidence
- `P(H|D)` = posterior

**Worked example:** disease affects 1% of people; the test is 99% accurate
both ways. Test positive → chance you have it is only **~50%**, because the
healthy people's 1% false positives rival the sick people's true positives.
The **base rate dominates**.

**Trap:** Base-rate neglect. Always ask "what's the prevalence?" before
trusting a positive result. Also don't confuse `P(A|B)` with `P(B|A)`
(prosecutor's fallacy).

**Interview line:** *"The base rate is the prior; with a rare condition,
even an accurate test produces mostly false positives."*

## 4. Random variables

**In plain words:** A random variable is a number whose value depends on
chance. **Discrete** = countable values (number of heads). **Continuous** =
any value in a range (height).

**Because:** Discrete outcomes each carry a probability; continuous
outcomes have zero probability at any single point, so we talk about
intervals.

**The term:** **PMF** (discrete) gives the probability of each value and
sums to 1. **PDF** (continuous) is a density; probability of an interval =
area under the curve. **CDF** `P(X ≤ x)` works for both.

**Interview line:** *"I use a PMF for counts and a PDF for continuous
measurements; the CDF lets me ask 'at most x' for either."*

## 5. Expectation

**In plain words:** The long-run average if you repeated the situation
forever.

**Because:** It's a probability-weighted average, so each outcome counts in
proportion to how often it happens.

**The term:** `E[X] = Σ x·p(x)`. **Linearity:** `E[X + Y] = E[X] + E[Y]`
**always** — even if X and Y are dependent. `E[aX + b] = a·E[X] + b`.

**Trap:** `E[X²] ≠ (E[X])²`. Linearity of expectation does *not* extend to
multiplication unless variables are independent (or uncorrelated).

**Interview line:** *"Linearity of expectation holds even without
independence — that's why I can swap the sum and the expectation."*

## 6. Variance (probabilistic version)

**In plain words:** How spread out a random variable is around its mean.

**Because:** It averages the squared distance from the mean; squaring makes
big departures count more, and the squaring is later undone by sqrt for std.

**The term:** `Var(X) = E[(X − μ)²] = E[X²] − μ²`.
- `Var(aX + b) = a²·Var(X)` — a shift doesn't spread anything; a scale
  factor scales spread by its square.
- `Var(X + Y) = Var(X) + Var(Y)` **only if independent**, otherwise
  `+ 2·Cov(X, Y)`.

**Interview line:** *"Adding a constant doesn't change variance; scaling by
a multiplies variance by a². Variances add only when variables are
independent."*

## 7. Distributions at a glance

| Distribution | Counts | Mean | Variance |
|---|---|---|---|
| Bernoulli(p) | one trial, 0/1 | p | p(1−p) |
| Binomial(n,p) | successes in n independent trials | np | np(1−p) |
| Poisson(λ) | events in a fixed interval | λ | λ |
| Uniform(a,b) | any value equally likely | (a+b)/2 | (b−a)²/12 |
| Normal(μ,σ²) | bell curve | μ | σ² |
| Exponential(λ) | waiting time between events | 1/λ | 1/λ² |
| Geometric(p) | trials until first success | 1/p | (1−p)/p² |

**Because:** Each is the natural model for a different counting/waiting
question. Poisson's mean = variance is its fingerprint; when the sample
variance is far larger, the events are clumping → overdispersed → use the
negative binomial.

**Interview line:** *"Poisson for counts in a window, Exponential for the
gaps between them, Binomial for successes out of n trials."*

## 8. Law of Large Numbers vs CLT

**In plain words:**
- **LLN:** as the sample grows, the sample mean gets **closer to the true
  mean**.
- **CLT:** the sample mean's **distribution** becomes **normal**,
  regardless of the population's shape, with standard error `σ/√n`.

**Because:** Averaging cancels idiosyncratic noise; the mean's randomness
is many small independent contributions, which pile into a bell.

**Interview line:** *"LLN says the mean converges; CLT says how it
wobbles around the target — normally, with spread σ/√n."*

## 9. Interview traps

1. **Base-rate neglect** — ignoring the prior in Bayes.
2. **Independence vs mutually exclusive** — opposite ideas.
3. **`P(A|B)` vs `P(B|A)`** — prosecutor's fallacy.
4. **Gambler's fallacy** — independent trials don't "owe" you a win.
5. **Mean of ratios ≠ ratio of means** — average at the right unit.

## 10. Interview framing (say it like this)

- *"A p-value is a probability of the data given the null; Bayes lets me
  invert that to the probability of the hypothesis given the data."*
- *"I always anchor a positive test result to the base rate — with a rare
  condition, most positives are false positives."*
- *"Linearity of expectation is the tool I reach for: I can sum
  expectations even when the variables are dependent."*
- *"I'd simulate the CLT rather than assume it: sample means from a skewed
  population form a normal distribution as n grows."*
