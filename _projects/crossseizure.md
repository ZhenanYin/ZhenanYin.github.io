---
layout: page
title: "CrossSeizure: Learning Generalizable Representations for Cross-Dataset Epileptic Seizure Classification"
description: A CNN-Transformer hybrid framework for generalizable epileptic seizure detection across diverse EEG datasets.
img: assets/img/projects/crossseizure.png
year: 2025 - 10
authors: Zhenan Yin and Saptarshi Purkayastha
redirect: false
---

## Overview

Traditional machine learning models for epileptic seizure classification perform well within a single dataset but fail when tested on EEG data from different clinical settings. This project develops a lightweight CNN-Transformer hybrid architecture that learns generalizable seizure representations directly from minimally preprocessed raw EEG signals, achieving robust cross-dataset performance without dataset-specific tuning.

## Key Contributions

- **Novel Architecture**: Combined EEGNet-style convolutions with Transformer attention for temporal-spatial feature learning
- **Cross-Dataset Generalization**: Achieved robust performance across BEED, BONN, and CHB-MIT datasets with different sampling rates and channel configurations
- **Minimal Preprocessing**: Used only 0.5 Hz high-pass filtering, preserving native EEG characteristics
- **Domain Adaptation**: Implemented DANN and CDAN strategies for domain-invariant feature learning

## Problem Statement

Current seizure detection models exhibit poor cross-dataset generalization due to:
- Dataset-specific frequency distributions and manifold geometries
- Dependence on hand-crafted features (FFT, UMAP)
- Overfitting to recording-specific artifacts

Our framework addresses these limitations by learning universal seizure dynamics rather than dataset-specific patterns.

## Methodology

### Datasets
- **BEED**: 8,000 samples, 16 channels, 256 Hz (4 classes)
- **BONN**: 500 samples, 1 channel, 173.61 Hz (5 classes)
- **CHB-MIT**: Clinical data, 23 channels, 256 Hz (2 classes)

### Model Architecture
1. **CNN Component**: Depthwise separable convolutions for local temporal-spatial features
2. **Transformer Component**: Multi-head self-attention for long-range dependencies
3. **Training Strategy**: Multi-dataset pretraining with domain adaptation

### Data Augmentation
Time-warping (60%), window slicing (30%), and amplitude scaling (10%) to enhance robustness.

## Results

*On-going Project*

## Supervision
Conducted under the supervision of Dr. Saptarshi Purkayastha, Department of Biomedical Engineering and Informatics, Indiana University Indianapolis.