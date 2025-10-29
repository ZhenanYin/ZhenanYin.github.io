---
layout: page
title: "CrossSeizure: Learning Generalizable Representations for Cross-Dataset Epileptic Seizure Classification"
description: A deep learning study that develops a CNN–Transformer hybrid framework to achieve cross-dataset generalization in epileptic seizure classification using minimally preprocessed raw EEG signals from multiple datasets.
img: assets/img/projects/crossseizure.png
year: 2025 - 10
authors: Zhenan Yin and Saptarshi Purkayastha
redirect: false
---

## Overview

This project presents a deep learning framework designed to overcome the generalization challenges of epileptic seizure classification across heterogeneous EEG datasets. Conducted under the supervision of Dr. Saptarshi Purkayastha (Department of Biomedical Engineering and Informatics, Indiana University Indianapolis), this work investigates the limitations of traditional feature-engineered methods and proposes a CNN–Transformer hybrid architecture to learn dataset-invariant representations directly from raw EEG signals. The study evaluates model robustness across multiple benchmark datasets—BEED, BONN, UCI, and CHB-MIT—each collected under different sampling rates, channel configurations, and acquisition conditions.

The project builds upon the limitations identified in SeqBoostNet, a state-of-the-art ensemble approach combining FFT and UMAP feature extraction, which achieves high within-dataset accuracy but fails in cross-dataset scenarios due to dataset-specific spectral and manifold dependencies. CrossSeizure introduces a lightweight attention-based model that integrates EEGNet-style convolutional layers for temporal–spatial feature extraction with Transformer modules for long-range temporal dependency modeling. Through multi-dataset pretraining and domain adaptation, the model aims to achieve robust cross-domain seizure recognition without requiring dataset-specific tuning. This project establishes new experimental benchmarks for cross-dataset generalization in EEG-based seizure detection and contributes a reproducible open-source framework for future clinical and computational neuroscience research.

**Motivation for the project**

Epilepsy affects over 50 million people globally, making it one of the most prevalent neurological disorders. Automated seizure detection using electroencephalogram (EEG) data has shown great potential for early intervention, personalized treatment, and continuous monitoring. However, current machine learning models for seizure classification exhibit poor cross-dataset generalization, performing well within a single dataset but failing drastically when exposed to EEG signals collected under different clinical conditions, hardware configurations, or sampling protocols. This lack of robustness prevents these systems from being deployed reliably across hospitals and patient populations.

Traditional methods based on hand-crafted features—such as Fast Fourier Transform (FFT) and Uniform Manifold Approximation and Projection (UMAP)—achieve high accuracy only within their training datasets. These features depend heavily on dataset-specific frequency distributions and manifold geometries, leading to overfitting and poor transferability. Addressing this limitation requires learning dataset-invariant representations that capture universal seizure dynamics rather than recording-specific artifacts.

Motivated by recent advances in Transformer architectures and attention-based representation learning, this project explores whether combining CNN-based spatial–temporal encoding with Transformer-based global attention can yield models that generalize across multiple EEG datasets. By minimizing preprocessing and leveraging multi-dataset pretraining, the proposed framework aims to develop a clinically viable and computationally efficient approach for generalizable seizure classification.

**Methodology**
- **Study Design**: A comparative experimental framework was established to evaluate and enhance the cross-dataset generalization of epileptic seizure classification models. The study consisted of four major phases: baseline replication, cross-dataset evaluation, CNN–Transformer model development, and domain generalization benchmarking.
- **Datasets**: Three EEG datasets were selected to ensure diversity in sampling rates, recording environments, and channel configurations:
   - BEED (Bangalore EEG Epilepsy Dataset): 8,000 samples, 16 EEG channels, 256 Hz sampling rate, and 4 evenly distributed classes (physical-movement seizure, healthy control, generalized seizure, focal seizure).
   - BONN: 500 single-channel EEG recordings, 173.61 Hz sampling rate, 5 balanced classes representing seizure and non-seizure brain activity.
   - CHB-MIT: Clinical dataset containing EEG recordings from 5 patients with 23 channels, 256 Hz sampling rate, and 2 binary classes (seizure and non-seizure).
- **Phase 1 – Baseline Replication**: The SeqBoostNet framework combining Fast Fourier Transform (FFT) and Uniform Manifold Approximation and Projection (UMAP) feature extraction was reproduced to validate prior within-dataset performance benchmarks. The ensemble classifier integrated LSTM, XGBoost, and Gradient Boosting with AdaBoost as the meta-learner. Baseline experiments were performed independently on BEED, BONN, and CHB-MIT to establish reference accuracies using handcrafted features.
- **Phase 2 – Cross-Dataset Evaluation**: The handcrafted pipeline was evaluated in cross-dataset settings—training on one dataset (e.g., BEED) and testing on another (e.g., BONN or CHB-MIT)—to quantify domain transferability. Performance degradation was analyzed to highlight the dataset dependency of FFT–UMAP feature spaces, particularly under differences in channel count and sampling rate.
- **Phase 3 – CNN–Transformer Hybrid Development**: A lightweight hybrid model integrating EEGNet-based convolutional blocks with a Transformer encoder was designed to learn generalizable seizure representations from raw EEG signals.
   - CNN Component: Depthwise separable convolutions captured local temporal and spatial relationships across EEG channels.
   - Transformer Component: Multi-head self-attention modeled long-range temporal dependencies and cross-channel relationships.
   - Preprocessing: Minimal preprocessing was applied—only a 0.5 Hz high-pass filter—to preserve native EEG characteristics and test model resilience under realistic conditions.
- **Phase 4 – Cross-Dataset Generalization and Domain Adaptation**: The proposed CNN–Transformer model was trained on one dataset and tested on others to evaluate cross-dataset generalization. Additional experiments employed Domain Adversarial Neural Network (DANN) and Conditional Domain Adaptation Network (CDAN) strategies to encourage domain-invariant feature learning. Leave-one-dataset-out validation (e.g., training on BONN + CHB-MIT, testing on BEED) was used to assess clinical transferability.
- **Data Augmentation**: To enhance model robustness, the training pipeline applied time-warping (60%), window slicing (30%), and amplitude scaling (10%) to increase variability and reduce overfitting.
- **Evaluation Metrics**: Model performance was measured using accuracy, precision, recall, F1-score, ROC–AUC, sensitivity, and specificity. Statistical reliability was ensured through stratified 5-fold cross-validation and paired t-tests.
- **Implementation**: All experiments were implemented in Python using PyTorch for model training, scikit-learn for baseline ensemble methods, and SciPy for signal transformations. Visualizations and performance analyses were conducted with Matplotlib and Seaborn on GPU-enabled JupyterHub environments.


