# Cheat Sheet — Probability & Distributions

Fast revision. Full explanations: `topics/02_probability.md`.

## Probability rules

- `P(not A) = 1 − P(A)`
- `P(A or B) = P(A) + P(B) − P(A and B)`
- `P(A|B) = P(A and B) / P(B)`
- Independent: `P(A|B) = P(A)` and `P(A and B) = P(A)·P(B)`
- Mutually exclusive: `P(A and B) = 0` (maximally dependent, NOT independent)

## Bayes

```
P(H|D) = P(D|H)·P(H) / P(D)
         likelihood · prior / evidence = posterior
```

**Base-rate example:** prevalence 1%, test 99% accurate → a positive leaves
only ~50% chance of disease. The base rate dominates.

## Expectation & variance

- `E[X] = Σ x·p(x)`
- **Linearity:** `E[X + Y] = E[X] + E[Y]` (always, even dependent)
- `E[aX + b] = a·E[X] + b`
- `Var(X) = E[(X − μ)²] = E[X²] − μ²`
- `Var(aX + b) = a²·Var(X)`
- `Var(X + Y) = Var(X) + Var(Y)` iff independent, else `+2·Cov`
- `E[X²] ≠ (E[X])²`

## Distributions

| Distribution | Counts | Mean | Variance |
|---|---|---|---|
| Bernoulli(p) | one trial 0/1 | p | p(1−p) |
| Binomial(n,p) | successes in n trials | np | np(1−p) |
| Poisson(λ) | events in an interval | λ | λ |
| Uniform(a,b) | value equally likely | (a+b)/2 | (b−a)²/12 |
| Normal(μ,σ²) | bell | μ | σ² |
| Exponential(λ) | time between events | 1/λ | 1/λ² |
| Geometric(p) | trials to first success | 1/p | (1−p)/p² |

## LLN vs CLT

- **LLN:** sample mean → true mean as n grows.
- **CLT:** sampling distribution of the mean → Normal, any population, SE = σ/√n.

## Traps

1. Base-rate neglect.
2. Independence vs mutually exclusive.
3. `P(A|B)` vs `P(B|A)` (prosecutor's fallacy).
4. Gambler's fallacy.
5. Mean of ratios ≠ ratio of means.
