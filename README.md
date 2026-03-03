## Overview

ECG Age Estimation is a biomedical signal processing project focused on estimating **biological age from 12-lead electrocardiogram (ECG) signals** using deep learning regression models.

The project implements and evaluates multiple time-series architectures, including:

- 1D CNN baselines  
- ResNet1D variants  
- LSTM + MLP models  
- Hybrid **CNN + Transformer + MLP** architecture (final model)

The input consists of fixed-length multi-lead ECG windows (e.g., 640 samples × 12 leads), optionally combined with structured clinical metadata (QRS duration, QT interval, heart rate, sex, etc.).

The final model achieved:

- **MAE ≈ 7.55 years**
- **R² ≈ 0.80**

---

## Datasets

Training was primarily performed using a **proprietary clinical dataset (Meschiset)**, which is not publicly available.

For reproducibility and experimentation, the pipeline also supports publicly available ECG datasets:

- **PTB-XL**
- **WFDB Chapman-Shaoxing**

This repository does not redistribute any dataset. It provides preprocessing scripts and standardized formatting pipelines for multi-source ECG integration.

---

## Technical Scope

The repository includes:

- Multi-dataset ingestion and normalization pipeline  
- Signal preprocessing and lead-wise standardization  
- Train/validation/test split strategy  
- Regression-oriented loss configuration  
- Error analysis (scatter plots, regression bias, Bland–Altman)  
- Model comparison framework  

Key technical challenges addressed:

- Age distribution imbalance and regression-to-the-mean effects  
- Cross-dataset normalization consistency  
- Stability of Transformer blocks on biomedical time-series  
- Generalization across heterogeneous ECG sources  

---

## Engineering Perspective

Although developed as a deep learning project, the architecture and pipeline are structured with a **deployment-oriented mindset**, enabling future:

- ONNX / TFLite export  
- Quantization and optimization  
- Edge / SoC integration  
- Embedded biomedical inference workflows

## Authors

- **Lucas Starita**
- **Juan Manuel Meneghini**
