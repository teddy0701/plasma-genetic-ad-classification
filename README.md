# Plasma–Genetic Alzheimer’s Disease Classification

This repository presents a machine learning and sequence-based modeling framework
for Alzheimer’s disease (AD) classification using plasma biomarkers and genetic
risk information. The project explores both cross-sectional and longitudinal
approaches to modeling disease status, with an emphasis on interpretability,
reproducibility, and methodological rigor.

## Project Overview
Early and minimally invasive biomarkers are critical for improving Alzheimer’s
disease diagnosis and risk stratification. Plasma biomarkers, combined with
genetic risk factors such as the APOE genotype, offer a promising alternative
to more invasive or expensive diagnostic procedures.  
This project investigates how different modeling strategies can leverage these
data sources to distinguish Alzheimer’s disease from cognitively normal status.

## Data Description
The analysis uses de-identified research data consisting of:
- Plasma biomarkers: Aβ40, Aβ42, Tau, and phosphorylated Tau (p-Tau)
- Genetic risk information encoded from APOE genotype
- Longitudinal visit information for subjects with repeated measurements

Raw data are not included in this repository. All analyses assume that data have
been preprocessed in accordance with institutional and IRB requirements.

## Modeling Approaches
Multiple modeling strategies are implemented and compared:

### 1. Multilayer Perceptron (MLP)
An MLP model is trained using baseline plasma biomarker features and APOE genotype
encoding. This approach serves as a strong non-linear baseline for cross-sectional
classification.

### 2. Gated Recurrent Unit (GRU)
To capture temporal dynamics in biomarker trajectories, GRU models are applied
to longitudinal plasma biomarker sequences. This enables modeling of disease-
related changes over time rather than relying on single-visit measurements.

### 3. FiLM-Conditioned GRU
A Feature-wise Linear Modulation (FiLM) mechanism is incorporated into the GRU
architecture to condition sequence modeling on APOE genotype. This allows genetic
risk to modulate biomarker representations dynamically, providing a biologically
motivated form of conditional modeling.

## Evaluation
Models are evaluated using standard classification metrics, including accuracy
and ROC-based measures. Subject-level data splitting is used to prevent data
leakage across training and evaluation sets. Comparative performance across
models is analyzed to assess the benefits of longitudinal and conditional
modeling strategies.

## Repository Contents
- `genetic-plasma-7.ipynb`  
  End-to-end notebook containing data preprocessing, feature engineering,
  model training, evaluation, and result visualization.

## Reproducibility and Transparency
This repository emphasizes clear documentation, reproducible analysis workflows,
and transparent modeling choices. While raw clinical data cannot be shared,
the code structure and methodology are designed to be adaptable to similar
biomedical datasets.

## Intended Audience
This project is intended for:
- Clinical and translational researchers interested in biomarker-based modeling
- Data scientists working with longitudinal health data
- Students and researchers exploring conditional and sequence-based deep learning
  methods in biomedical applications

## Notes
This repository is for research and educational purposes only and is not intended
for clinical decision-making.
