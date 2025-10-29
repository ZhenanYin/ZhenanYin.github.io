---
layout: page
title: "Deep Learning for Plankton Image Retrieval"
description: A computational study for developing a deep learning-based system that automates plankton image labeling and retrieval to support oceanographic research on marine ecosystem analysis.
img: assets/img/projects/plankton.png
year: 2018
authors: Zhenan Yin, Devon Stanfield, and Nuno Vasconcelos
redirect: false
---

## Overview

This project presents a computational deep learning framework for automated plankton image retrieval and labeling, designed to accelerate large-scale oceanographic data analysis. The system integrates Convolutional Neural Networks (CNNs) for feature extraction with Approximate Nearest Neighbor (ANN) search algorithms to identify visually similar plankton species across millions of underwater images. Developed under the supervision of Prof. Nuno Vasconcelos (Department of Electrical and Computer Engineering, University of California, San Diego) in collaboration with the Scripps Institute of Oceanography, this work was conducted at the Statistical Visual Computing Lab (SVCL). The project further incorporates a Django-based backend with a PostgreSQL database and a web-based frontend interface for real-time retrieval, significantly enhancing the efficiency and scalability of marine image annotation workflows.

**Motivation for the project**

Marine ecosystems play a critical role in sustaining global biodiversity and regulating climate, yet their monitoring heavily relies on the manual identification of microscopic plankton from vast underwater image datasets. Traditional labeling approaches are labor-intensive and time-consuming, with a single expert often requiring weeks to annotate a small subset of data. This limitation constrains large-scale ecological analyses and hinders timely environmental assessment. Advances in deep learning and computer vision offer the potential to automate and accelerate this process by enabling machines to learn discriminative visual features of plankton species. Developing a scalable and accurate image retrieval system can therefore transform marine research workflows, enhance dataset accessibility, and facilitate a deeper understanding of oceanic biodiversity dynamics.

**Methodology**
- **Feature Extraction with CNNs**: The system employed deep convolutional neural networks (CNNs), including *InceptionResNetV2* and *ResNet-50*, pre-trained on ImageNet and fine-tuned for plankton imagery. The classification layer was removed, and intermediate activations were extracted as feature embeddings representing high-level visual characteristics of each image.
- **Similarity Search Framework**: Extracted feature vectors were indexed using *Approximate Nearest Neighbor (ANN)* algorithms to enable efficient retrieval of visually similar images. Multiple distance metrics：*Euclidean, Cosine, and Hamming* were evaluated to quantify similarity in the high-dimensional feature space.
- **Hashing and Hyperplane Partitioning**: To enhance retrieval speed and scalability, feature vectors were encoded into binary hash codes and partitioned using hyperplane-based indexing, allowing sub-second search performance on large-scale datasets.
- **Data Augmentation**: Training data were expanded through geometric and photometric transformations, including rotation, flipping, and Gaussian blurring, to improve model generalization and robustness to underwater imaging variability.
- **System Architecture**: The backend was implemented using the Django web framework with a PostgreSQL database for image metadata management. The frontend interface, developed with jQuery, facilitated user queries and visualization of retrieved plankton images.
- **Performance Evaluation**: Retrieval accuracy, latency, and scalability were benchmarked using labeled datasets from the Scripps Institute of Oceanography, demonstrating a 5–10× improvement in labeling efficiency compared to manual annotation.

**Findings**

Experimental evaluation demonstrated that the CNN-based feature extraction combined with Approximate Nearest Neighbor (ANN) retrieval achieved a substantial improvement in both speed and precision of plankton image labeling. Compared to manual annotation, the automated system accelerated the labeling process by approximately 5–10 times, reducing the time required for one scientist to label 30,000 images from one month to just a few days. Quantitative analysis showed that feature embeddings from InceptionResNetV2 provided the highest retrieval accuracy, with cosine similarity outperforming Euclidean and Hamming distances in discriminating fine-grained plankton morphology. The integration of hashing and hyperplane partitioning reduced retrieval latency to under four seconds for datasets exceeding 10,000 images, while maintaining high recall of visually similar species. Furthermore, data augmentation enhanced classification robustness, increasing top-1 retrieval accuracy from 65% to over 90%. These findings demonstrate the system’s scalability and effectiveness for large-scale marine image analysis.

## Key Features

- Deep convolutional neural network (CNN) framework for hierarchical feature extraction from high-resolution plankton imagery.
- Approximate Nearest Neighbor (ANN) search for fast and scalable similarity retrieval across millions of images.
- Integration of multiple distance metrics (Euclidean, Cosine, and Hamming) for flexible and accurate feature-space comparison.
- Hashing and hyperplane-based partitioning to optimize retrieval latency and computational efficiency.
- Comprehensive data augmentation pipeline to improve generalization under diverse underwater imaging conditions.
- Full-stack system architecture combining Django–PostgreSQL backend with jQuery-based frontend for real-time visualization and interaction.
- Performance evaluation demonstrating 5–10× acceleration in labeling efficiency and significant gains in retrieval accuracy through feature embedding optimization.

## Overall Conclusion

This project successfully demonstrates the potential of deep learning to transform large-scale marine image analysis through automated plankton image retrieval and labeling. By integrating CNN-based feature extraction with Approximate Nearest Neighbor search, the system achieved high retrieval accuracy and significant efficiency gains over traditional manual methods. The use of hashing and hyperplane partitioning further enabled scalable performance across datasets containing millions of underwater images. Through a robust Django–PostgreSQL architecture and an intuitive web interface, the framework provides a practical and accessible tool for marine researchers. Overall, this work highlights how modern computer vision and scalable search algorithms can accelerate ecological discovery, enhance biodiversity monitoring, and support data-driven environmental research.