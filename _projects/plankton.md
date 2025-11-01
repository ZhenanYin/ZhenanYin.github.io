---
layout: page
title: "Deep Learning for Plankton Image Retrieval"
description: Automating plankton image labeling and retrieval using CNNs and approximate nearest neighbor search to accelerate oceanographic research.
img: assets/img/projects/plankton.png
year: 2018
authors: Zhenan Yin, Devon Stanfield, and Nuno Vasconcelos
redirect: false
---

## Overview

Developed an automated plankton image retrieval system that accelerates marine ecosystem analysis by **5-10× faster** than manual labeling. Using deep learning and approximate nearest neighbor search, the system processes millions of underwater images to help oceanographers identify and catalog plankton species.

## Problem Statement

**Challenge**: Marine biologists spend weeks manually labeling plankton images—one expert taking a month to annotate 30,000 images. This bottleneck limits large-scale ecological studies.

**Solution**: Automated CNN-based retrieval system that finds visually similar plankton specimens, reducing annotation time from weeks to days.

## Key Achievements

### Performance Improvements
- **Labeling speed**: 5-10× faster than manual annotation
- **Retrieval accuracy**: Improved from 65% → 90% with data augmentation
- **Query latency**: <4 seconds for 10,000+ image datasets
- **Scale**: Processing capability for millions of images

### Technical Impact
Transformed workflow: 30,000 images labeled in **days instead of months**

## System Architecture

### Computer Vision Pipeline
1. **Feature Extraction**: InceptionResNetV2 & ResNet-50 CNNs
2. **Embedding Generation**: High-dimensional visual feature vectors
3. **Similarity Search**: Approximate Nearest Neighbor (ANN) algorithms
4. **Distance Metrics**: Cosine, Euclidean, and Hamming distances

### Optimization Techniques
- **Binary hashing**: Fast similarity computation
- **Hyperplane partitioning**: Efficient large-scale indexing
- **Data augmentation**: Rotation, flipping, Gaussian blur for robustness

### Full-Stack Implementation
- **Backend**: Django + PostgreSQL (metadata management)
- **Frontend**: jQuery web interface (real-time visualization)
- **Database**: Scalable image metadata storage

## Technical Highlights

### Deep Learning Approach
- Pre-trained CNNs (ImageNet) fine-tuned on plankton imagery
- Classification layer removed for feature embedding extraction
- Transfer learning accelerated model convergence

### Similarity Search
Approximate Nearest Neighbor (ANN) retrieval enables:
- Sub-second search across millions of images
- Multiple distance metrics for flexible comparison
- Binary encoding for memory-efficient storage

### Data Augmentation Benefits
Enhanced model robustness through:
- Geometric transformations (rotation, flipping)
- Photometric variations (brightness, contrast)
- Simulated underwater imaging conditions

## Research Impact

### Oceanographic Applications
- **Biodiversity monitoring**: Track plankton population changes
- **Climate research**: Analyze ecosystem responses to environmental shifts
- **Real-time assessment**: Accelerate environmental impact studies

### Workflow Transformation
Automated retrieval enables:
- Large-scale dataset annotation
- Collaborative labeling across research institutions
- Rapid species identification for time-sensitive studies

## Collaboration

Developed in partnership with **Scripps Institute of Oceanography** to support marine ecosystem research and oceanographic data analysis.

## Supervision

Conducted under Prof. Nuno Vasconcelos, Department of Electrical and Computer Engineering, UC San Diego (Statistical Visual Computing Lab).