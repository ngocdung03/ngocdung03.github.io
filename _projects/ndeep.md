---
order: 1
title: "nDeep — Deep Survival Analysis"
subtitle: "A neural network for time-to-event cancer-risk prediction on prospective cohort data."
period: "2022 – present"
org: "MoAdata"
summary: "Open-source deep survival model for time-to-event cancer-risk prediction on large prospective cohorts."
tech: ["PyTorch", "Survival analysis", "Cox PH baseline", "Cohort data"]
repo: "https://github.com/ngocdung03/nDeep"
---

Classical survival models — Cox proportional hazards above all — remain the
default for cancer-risk prediction on cohort data, and for good reason: they are
interpretable, well understood, and hard to beat when the hazard really is
proportional and the covariate effects are roughly linear. They are also
constrained by exactly those assumptions.

**nDeep** replaces the linear predictor with a neural network while keeping the
survival-analysis machinery intact — censoring handled properly, time-to-event
structure preserved, risk scores that remain comparable to a Cox baseline.

## What it does

- Learns a non-linear risk function over covariates from prospective cohort data.
- Handles right-censored observations natively rather than reducing the problem
  to fixed-horizon binary classification.
- Produces individual risk trajectories over time, not a single scalar score.
- Benchmarks against Cox PH on the same cohort and split, so any gain is
  attributable to the model rather than the preprocessing.

## Why it matters

For prevention work, the useful question is rarely "will this person develop
cancer" — it is "over what horizon, and with what confidence." Discrimination
metrics like the concordance index only tell half that story; calibration over
time tells the rest. The model was developed with both in view.

## Related publication

The methodological groundwork appears in *A Study on Survival Analysis Methods
Using Neural Networks to Prevent Cancers* (**Cancers**, 2023), where I
contributed the deep survival modelling, data cleaning, analysis, and
manuscript.
