# 30-Day Roadmap

Target: Data Scientist. Depth: intuition + interview-ready. Hands-on:
concepts + from-scratch code + practical sklearn. Pace: ~2h/day, bundle
allowed.

Approach: a compressed 4-day foundations block, then core algorithms in
dependency order, with continuous spiral review via the cumulative Q&A.

## Week 1 — Foundations + Regression

| Day | Topic | Hands-on |
|---|---|---|
| 1 | Diagnostic quiz + setup; Descriptive stats & distributions | code: describe/quantiles |
| 2 | Probability: conditional, Bayes, random variables, expectation/variance | simulate CLT |
| 3 | Inference: sampling, CLT, CI, hypothesis testing, p-values, power, Type I/II | t-test demo |
| 4 | Linear algebra + calculus for ML: matrices, norms, derivatives, gradient descent | gradient descent by hand |
| 5 | Linear Regression I: OLS, assumptions (LINE), MLE, R² | from-scratch OLS |
| 6 | Linear Regression II: GD, Ridge/Lasso/ElasticNet, multicollinearity, diagnostics | regularization demo |
| 7 | Review + Week-1 mini mock | — |

## Week 2 — Classification + Evaluation

| Day | Topic | Hands-on |
|---|---|---|
| 8 | Logistic Regression I: sigmoid, log-odds, cross-entropy, decision boundary | from-scratch GD |
| 9 | Logistic Regression II: regularization, multiclass, interpretation, imbalance | class_weight demo |
| 10 | Bias–variance, over/underfitting, cross-validation, model selection | CV curves |
| 11 | Classification metrics: confusion matrix, P/R/F1, ROC-AUC, PR-AUC, calibration | metrics notebook |
| 12 | Regression metrics + loss functions: MSE/MAE/RMSE/Huber/R²/adj-R² | loss comparison |
| 13 | Decision Trees: entropy/Gini/information gain, CART, pruning | from-scratch split |
| 14 | Review + Week-2 mini mock | — |

## Week 3 — Ensembles + SVM + Other Supervised

| Day | Topic | Hands-on |
|---|---|---|
| 15 | Bagging + Random Forest, feature importance, OOB | RF vs single tree |
| 16 | Boosting: AdaBoost, Gradient Boosting, XGBoost/LightGBM/CatBoost, tuning | boosting tuning |
| 17 | Stacking/blending + ensemble interview traps | stacking demo |
| 18 | SVM I: margins, support vectors, hinge loss, soft margin | margin intuition |
| 19 | SVM II: kernels, kernel trick, RBF, multiclass | kernel comparison |
| 20 | KNN + Naive Bayes + model-comparison cheat sheet *(bundle)* | sklearn KNN/NB |
| 21 | Review + Week-3 mini mock | — |

## Week 4 — Unsupervised + DS-Specific + Mocks

| Day | Topic | Hands-on |
|---|---|---|
| 22 | Clustering: k-means, hierarchical, DBSCAN, GMM, evaluation | from-scratch k-means |
| 23 | Dimensionality reduction: PCA, SVD, t-SNE/UMAP | PCA from scratch |
| 24 | Feature engineering: scaling, encoding, imbalance, leakage, pipelines | sklearn pipeline |
| 25 | Experimentation for DS: A/B tests, power, multiple testing, causal basics | power calc |
| 26 | SQL + metric definition + product sense *(bundle)* | SQL drills |
| 27 | ML system design & case questions for DS | case walkthrough |
| 28 | Full cumulative mock interview #1 | — |
| 29 | Weak-area repair + mock #2 | — |
| 30 | Final consolidation: cheat sheets, behavioral prep, cold review | — |

## Dependency map

```
stats/prob/calc ─▶ linear regression ─▶ logistic regression ─▶ metrics
                                      └▶ bias-variance ─▶ trees ─▶ ensembles
                                                                    └▶ SVM (independent)
unsupervised (needs scaling + algebra)
experimentation (needs inference)
system design (needs all)
```

## Adjusting the plan

- If a day's topic lands ≥9/10 median, mark it "compress" and consider
  bundling the next day.
- If <7/10 median, insert a repair segment into the next session before
  new material.
- Swaps are fine — update `progress.md` and this file together.
