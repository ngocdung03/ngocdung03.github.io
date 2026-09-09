---
order: 5
title: "Retinal Imaging and AI for Dementia Risk Prediction"
subtitle: "A research proposal — study design only. No model has been trained and no results are reported."
period: "2026"
org: "Research proposal · CLSA Comprehensive Cohort"
summary: "Written research proposal specifying a multimodal deep-learning design for predicting incident dementia from fundus photography in the Canadian Longitudinal Study on Aging."
tech: ["Study design", "Multimodal deep learning", "Retinal imaging", "Cohort data"]
---

This entry describes a **research proposal**. It sets out a study design and a
set of candidate methods; no model has been trained, no data have been analysed,
and no results are reported.

Dementia affects more than 55 million people worldwide, and the majority remain
undiagnosed until late symptomatic stages, by which point disease-modifying
intervention is substantially less effective. The diagnostic gold standards —
cerebrospinal-fluid biomarkers and PET imaging — are invasive, expensive, and
unavailable in community settings, which leaves population-scale early screening
without a practical instrument.

The retina is a plausible route to one. As a direct anatomical extension of the
central nervous system, it undergoes structural and vascular change that tracks
neurodegenerative processes in the brain, and non-mydriatic colour fundus
photography is already standard equipment in optometry clinics and population
cohorts, acquired in under two minutes without pharmacological dilation.

## The setting

The proposal is built around the Canadian Longitudinal Study on Aging, whose
Comprehensive Cohort of roughly 30,000 participants undergoes deep clinical
assessment at eleven standardised sites, including fundus photography,
neuropsychological testing, biospecimens, and cardiometabolic measures, with
incident dementia confirmed longitudinally against ICD-10.

One constraint shapes every methodological choice: the CLSA deliberately collects
no optical coherence tomography, favouring throughput and cross-site
standardisation. All retinal data are therefore standard 2D colour photographs,
and any proposed method has to work from those alone.

## What the proposal specifies

- Three candidate pipelines, compared rather than assumed: **multimodal
  intermediate fusion** of image features with clinical metadata, **two-step
  machine-to-machine transfer** followed by risk prediction, and
  **segmentation-guided prediction** through vascular structures.
- An **image-quality screening stage**, since undilated photography acquired
  across eleven sites varies in quality in ways that would otherwise be learned
  as signal.
- An evaluation framework treating discrimination and calibration separately,
  consistent with the time-to-event framing that incident dementia requires.

The design draws on published work applying deep learning to CLSA fundus images,
where photographs alone explained 9.3% of variance in global cognition and
metadata fusion raised that to 22.4% — a result that sets realistic expectations
for what standard colour photography can carry, and motivates the emphasis on
fusion over image-only modelling.
