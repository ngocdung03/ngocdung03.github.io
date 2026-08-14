---
order: 2
title: "Metabolic Health and Thyroid Cancer Risk"
subtitle: "Survival analysis of metabolic phenotype and central obesity in the Korean Genome and Epidemiology Study."
period: "2020 – 2021"
org: "National Cancer Center, South Korea"
summary: "Cohort survival analysis showing metabolic health and central obesity are jointly associated with thyroid cancer risk."
tech: ["Cox PH", "R", "KoGES cohort", "Epidemiology"]
paper: "https://aacrjournals.org/cebp"
---

Obesity is an established risk factor for thyroid cancer, but "obese" is a
coarse label. A sizeable fraction of people with high BMI are metabolically
healthy, and a sizeable fraction of people with normal BMI are not. The
interesting question is which axis carries the risk.

## Approach

Using prospective data from the **Korean Genome and Epidemiology Study
(KoGES)**, I cross-classified participants by metabolic health status and by
central obesity, then fitted Cox proportional-hazards models for incident
thyroid cancer across the resulting phenotype groups.

- Defined the analytic cohort and exclusion criteria; cleaned and integrated the
  source datasets.
- Specified the research questions and the statistical-analysis plan.
- Fitted and diagnosed the survival models, including proportional-hazards
  checks and covariate adjustment.
- Wrote the manuscript.

## Finding

Metabolic health status and central obesity were both significantly associated
with increased thyroid cancer risk — the association was not reducible to BMI
alone. This matters for screening: the metabolic phenotype adds information that
a weight-based criterion discards.

Published in *Cancer Epidemiology, Biomarkers & Prevention* (2021).
