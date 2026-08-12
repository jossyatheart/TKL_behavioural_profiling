# Participant-Aware Behavioural Profiling in Augmented Reality Learning Environments

This repository contains the analysis code, reproducibility materials, and supporting outputs for the manuscript:

**Participant-Aware Behavioural Profiling in Augmented Reality Learning Environments**

## Study overview

The study analyses behavioural interaction data collected using Microsoft HoloLens 2 during a five-minute augmented-reality learning activity. The original experimental environment and data-collection procedure are described by Nwobodo et al. (2025).

The analytical dataset contains:

- **1,551 learner–object behavioural records**
- **36 participants**
- **10 virtual AR objects**

Four behavioural measures were analysed:

- gaze duration
- interaction frequency
- revisit count
- head movement

  ## Data provenance

The behavioural data analysed in this repository originate from the augmented-reality learning experiment reported in:

> Nwobodo, O. J., Kuaban, G. S., Wereszczyński, K., & Cyran, K. A. (2025).  
> *Enhancing learning in augmented reality (AR): A deep learning framework for predicting memory retention in AR environments.*  
> In *International Conference on Computational Science* (pp. 92–106).  
> https://doi.org/10.1007/978-3-031-97573-8_7

The present repository contains a **secondary participant-aware analysis** of behavioural data from that experiment. The current analysis focuses on behavioural interaction profiling and does not reuse the previously derived Memory State variable as an independent validation outcome.

## Analytical approach

The primary analysis uses **participant-weighted K-means clustering** to account for unequal numbers of behavioural records contributed by individual participants.

The preferred solution contains two behavioural interaction profiles:

- **Lower-Intensity Interaction Profile**
- **Higher-Intensity Interaction Profile**

Robustness was evaluated using:

- candidate cluster solutions from K = 2 to K = 6;
- participant-balanced cluster-validity measures;
- conventional unweighted K-means;
- Gaussian mixture modelling;
- agglomerative hierarchical clustering;
- algorithmic consensus;
- leave-one-participant-out validation;
- participant-level bootstrapping;
- sparse-participant sensitivity analysis;
- feature-ablation and single-feature analyses;
- principal component analysis;
- PC1-only clustering; and
- PC1 median-split sensitivity analysis.

The analyses indicate that the two profiles are best interpreted as comparatively lower- and higher-intensity regions along a predominantly continuous behavioural interaction-intensity dimension rather than as fixed learner types.

The profiles should not be interpreted as direct measures of learning achievement, engagement, cognitive state, cognitive load, or memory performance.

## Analytical cohort

The analysis is restricted to the **36 participant sessions corresponding to the original experimental cohort**.

The source data available for secondary analysis contained four additional later-numbered session identifiers. These sessions were excluded to maintain consistency with the published 36-participant experiment rather than because they were judged invalid.

The cohort-selection procedure is documented in the reproducibility outputs.

## Repository contents

The repository contains:

- the Jupyter notebook used for the complete analysis;
- cohort-selection and participant-audit outputs;
- clustering and robustness-analysis outputs;
- participant- and object-level summaries;
- final profile assignments;
- statistical model outputs; and
- figures used in the manuscript.

Key reproducibility outputs are written to the `analysis_outputs/` directory.

## Reproducing the analysis

The main notebook should be run sequentially from top to bottom.

Required Python packages include:

```text
numpy
pandas
scipy
scikit-learn
statsmodels
matplotlib
