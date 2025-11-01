---
layout: page
title: "Embeddings are Noise Eliminators: Ablation Studies to Show What is Eliminated in Foundation Models"
description: Investigating how foundation model embeddings intrinsically filter non-clinical noise in medical imaging through systematic ablation studies.
img: assets/img/projects/embedding.png
year: 2025
authors: Raajitha Muthyala, Zhenan Yin, Alekhya Jilla, Frank Li, Theo Dapamede, Bardia Khosravi, Mohammadreza Chavoshi, Judy Gichoya, and Saptarshi Purkayastha
venue: Submitted to Radiology - Artificial Intelligence (Technical Developments)
redirect: false
---

## Overview

Foundation models demonstrate remarkable robustness in medical imaging, but the mechanisms underlying this performance remain unclear. This study investigates whether embeddings from large-scale vision transformers inherently filter non-clinical noise while preserving diagnostic information, using controlled ablation experiments on 249,000+ chest X-rays.

## Research Question

**Do foundation model embeddings act as intrinsic noise eliminators?**

By introducing synthetic perturbations (circles, squares, diagonal lines) into radiological images and evaluating embedding-based classifiers, we quantify how well models distinguish clinical features from imaging artifacts.

## Key Findings

### Strong Disease Classification
- **RAD-DINO** (radiology-specific): AUC 0.91 for cardiomegaly, 0.91 for edema
- **DINOv3** (general-purpose): AUC 0.87–0.89 across conditions
- Performance maintained despite synthetic noise injection

### Poor Noise Detection
- Diagonal lines: AUC 0.50–0.58 (near random chance)
- Small squares/circles: AUC 0.51–0.71
- **Conclusion**: Embeddings suppress non-clinical artifacts

### Domain-Specific Advantage
RAD-DINO consistently outperformed DINOv3 on clinical tasks, demonstrating benefits of medical domain pretraining.

## Methodology

### Datasets
- **NIH-CXR14**: 112,120 chest X-rays
- **Emory CXRv2**: 137,280 chest X-rays

### Models Evaluated
1. **RAD-DINO**: Domain-specific ViT trained on 1M+ medical images (768-dim embeddings)
2. **DINOv3**: General ViT-7B trained on 1.6B natural images (4096-dim embeddings)

### Experimental Design
- Synthetic noise injected into 50% of images
- Noise types: circles (1-2px radius), squares (4×4, 8×8 px), diagonal lines
- Dual classification tasks:
  - **Disease detection** (clinical relevance)
  - **Noise detection** (artifact sensitivity)
- Logistic regression classifiers on frozen embeddings

### Key Insight
High disease classification + low noise detection = **embeddings filter out irrelevant patterns**

## Clinical Implications

Foundation model embeddings maintain diagnostic accuracy even under degraded imaging conditions, making them reliable for:
- Real-world deployment with variable image quality
- Cross-institutional generalization
- Trustworthy AI in clinical radiology

## Supervision
Conducted under Dr. Saptarshi Purkayastha (Indiana University Indianapolis) in collaboration with Emory University's Department of Radiology and Imaging Sciences.