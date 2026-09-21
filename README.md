# Brain MRI Tumor Classification

Deep learning framework for four-class brain MRI classification with rigorous cross-dataset overlap screening, external validation, uncertainty-aware evaluation, and Telegram-based deployment.

## Overview

This project develops and evaluates a deep learning system for classification of brain MRI images into four categories:

- Glioma
- Meningioma
- Pituitary tumor
- No tumor

The project emphasizes not only predictive performance, but also dataset integrity, independent external validation, reproducibility, and practical deployment.

## Data Integrity and Leakage Control

A major focus of the study was preventing data leakage between development and external validation datasets.

The external dataset initially contained 7,200 images.

After screening:

- 3,409 exact duplicate images were removed
- Additional near-duplicate screening was performed
- Final deduplicated external validation cohort: 3,106 images

This process was designed to ensure that external validation performance reflected genuine generalization rather than cross-dataset overlap.

## Model

The final deployment model is based on:

- MobileNetV3-Large
- Transfer learning
- 224 × 224 RGB image input
- Four-class softmax classification

The trained deployment model is fingerprint-verified using SHA-256 before inference.

## External Validation

Performance on the final independent external validation cohort:

- Accuracy: 94.95%
- Balanced accuracy: 94.05%
- Macro-F1: 94.26%
- Matthews Correlation Coefficient: 0.9324
- Macro AUROC: 0.9935
- Macro AUPRC: 0.9819

Performance uncertainty was assessed using 2,000 stratified bootstrap replicates with 95% confidence intervals.

## Evaluation

The notebook includes:

- Accuracy
- Balanced accuracy
- Precision
- Recall
- Macro-F1
- Matthews Correlation Coefficient
- AUROC
- AUPRC
- Per-class sensitivity and specificity
- Confusion matrices
- Calibration analysis
- Prediction-confidence analysis
- Bootstrap confidence intervals
- Misclassification analysis

## External Validation Visualizations

The analysis generates publication-quality figures including:

- External cohort construction
- Class distribution
- Raw confusion matrix
- Normalized confusion matrix
- ROC curves
- Precision-recall curves
- Per-class performance
- Calibration curves
- Bootstrap confidence intervals
- Misclassification patterns

## Deployment

The final model was integrated into a Telegram-based research decision-support interface.

Users can submit a brain MRI image and receive:

- Predicted class
- Prediction confidence
- Probabilities for all four classes

The Telegram system is intended for research use only and is not a substitute for clinical or radiological diagnosis.

## Repository Contents

`brain_tumor_mri_classification.ipynb`

Main research notebook containing:

- Data preparation
- Duplicate and near-duplicate screening
- Model development
- Training
- Internal evaluation
- External validation
- Statistical analysis
- Visualization
- Deployment

## Research Focus

This project explores robust and clinically relevant medical image analysis with particular emphasis on:

- Generalization across datasets
- Leakage-resistant evaluation
- External validation
- Model calibration
- Reproducibility
- Deployment of medical AI systems

## Author

**Babatunde Ogunmiloro, M.D.**

Medical doctor and applied biomedical AI researcher.

Research interests include medical image analysis, clinical artificial intelligence, deep learning, external validation, and deployable decision-support systems.

## Disclaimer

This project is intended for research purposes only. It is not intended to provide medical diagnosis or replace assessment by qualified healthcare professionals.
