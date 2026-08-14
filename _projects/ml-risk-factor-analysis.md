---
order: 3
title: "Machine-Learning Risk-Factor Analysis"
subtitle: "Identifying predictive factors of disease from metabolic and epidemiological data."
period: "2020 – 2021"
org: "National Cancer Center, South Korea"
summary: "ML pipelines in R and Python to surface predictive disease factors from metabolic and epidemiological cohort data."
tech: ["scikit-learn", "R", "Feature selection", "Cohort data"]
---

Epidemiological analysis usually starts from a hypothesis: pick the exposure,
adjust for confounders, estimate the effect. That is the right tool when you
already know what to look for. It is a poor tool for the opposite situation —
a wide cohort with hundreds of measured variables and no strong prior about
which of them matter.

## Approach

I built R and Python pipelines applying machine-learning algorithms to metabolic
and epidemiological cohort data to rank candidate predictors of disease, then
carried the surviving candidates back into conventional models where their
effects could be estimated and interpreted properly.

- Preprocessing and imputation strategies appropriate to cohort data, with
  missingness treated as informative where the study design implied it.
- Comparison of several algorithm families rather than a single model, since
  feature rankings are not stable across model classes.
- Cross-validated selection, so the reported predictors were not artefacts of a
  single split.
- Findings fed into a peer-reviewed epidemiological study.

## Why the two-stage design

Pure ML feature importance is easy to over-read: correlated covariates share
credit unpredictably, and importance is not effect size. Using ML for *screening*
and classical survival or regression models for *estimation* keeps the strengths
of both and makes the result defensible to a clinical audience.
