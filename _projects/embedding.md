---
layout: page
title: "Embeddings are Noise Eliminators: Ablation Studies to Show What is Eliminated in Foundation Models"
description: An exploratory study examining how foundation model embeddings inherently eliminate non-clinical noise and imaging artifacts through systematic ablation experiments, revealing their role as intrinsic noise filters in medical image representation.
img: assets/img/projects/embedding.png
year: 2025
authors: Raajitha Muthyala, Zhenan Yin, Alekhya Jilla, Frank Li, Theo Dapamede, Bardia Khosravi, Mohammadreza Chavoshi, Judy Gichoya, and Saptarshi Purkayastha
venue: Submitted to Radiology - Artificial Intelligence (Technical Developments)
redirect: false
---

## Overview

This project presents an exploratory study that investigates the intrinsic noise-filtering mechanisms of foundation model embeddings in medical imaging. Conducted under the supervision of Dr. Saptarshi Purkayastha (Department of Biomedical Engineering and Informatics, Indiana University Indianapolis) in collaboration with researchers from Emory University’s Department of Radiology and Imaging Sciences, this study systematically examines how embeddings derived from large-scale vision transformers suppress non-clinical noise while preserving diagnostically relevant features. Using two state-of-the-art models—RAD-DINO (a domain-specific radiology foundation model) and DINOv3 (a general-purpose vision transformer)—the research team performed controlled ablation studies across more than 249,000 chest X-rays from the NIH-CXR14 and Emory CXRv2 datasets. By introducing synthetic perturbations such as circles, squares, and diagonal lines, and evaluating the resulting embeddings through logistic regression classifiers, the study quantitatively demonstrates that foundation model embeddings act as inherent noise eliminators. The results highlight the embeddings’ capacity to filter imaging artifacts and enhance downstream diagnostic accuracy, offering insights into how self-supervised learning enables robust and interpretable representations for radiological applications.

**Motivation for the project**

Foundation models have transformed medical image analysis by enabling generalizable, training-free representations that support a wide range of diagnostic and predictive tasks. However, despite their strong performance across radiological applications, the internal mechanisms that make these embeddings robust to noise and variability remain poorly understood. Radiological images often contain non-clinical artifacts such as scanner noise, acquisition markings, or patient motion blur that can obscure subtle pathologies and compromise model reliability. Understanding whether foundation model embeddings inherently suppress such irrelevant visual signals is critical for ensuring trustworthy deployment of AI systems in clinical settings. This project was motivated by the need to elucidate how pre-trained embeddings process noise versus clinical information and whether their performance resilience arises from intrinsic noise-filtering capabilities. By conducting systematic ablation studies on large-scale chest X-ray datasets with controlled synthetic perturbations, the study aims to reveal the representational mechanisms that allow foundation models to maintain diagnostic accuracy even under suboptimal imaging conditions.

**Methodology**
- **Study Design**: A retrospective computational study was conducted to investigate the intrinsic noise-filtering properties of foundation model embeddings using large-scale chest radiography datasets. The analysis focused on understanding how pre-trained embeddings respond to synthetic perturbations and whether these perturbations influence disease classification performance.
- **Datasets**: Two major chest X-ray datasets were utilized: NIH-CXR14 (n = 112,120) and Emory CXRv2 (n = 137,280). Both datasets contained frontal radiographs representing a range of cardiothoracic conditions. Data were split into training (80%) and testing (20%) subsets with fixed random seeds to ensure reproducibility.
- **Synthetic Noise Injection**: Controlled perturbations were systematically introduced into 50% of the images to create balanced “noisy” and “clean” subsets. Noise patterns included filled circles (radius = 1–2 px), squares (4×4 px and 8×8 px), and diagonal lines. Intensity sampling was guided by local image histograms (mode ± 20 gray levels) to ensure realistic artifact generation while preserving anatomical context.
- **Preprocessing**: NIH-CXR14 images were analyzed at native resolution (1024×1024 px) to avoid interpolation artifacts, while Emory CXRv2 images were padded and resized to 1024×1024 px using LANCZOS4 interpolation for aspect ratio preservation. Noise placements were restricted to the central 70% region of each image to ensure anatomical overlap.
- **Model Architectures**: Two self-supervised foundation models were evaluated:
   - *RAD-DINO* – A radiology-specific Vision Transformer trained on over one million medical images (RadImageNet). Embeddings were 768-dimensional, extracted from the CLS token.
   - *DINOv3* – A general-purpose Vision Transformer (ViT-7B) trained on 1.6 billion natural images, generating 4096-dimensional embeddings with 32 attention heads.
- **Feature Extraction and Classification**: Models were loaded in inference mode with frozen weights. CLS token embeddings were extracted and used as features for downstream logistic regression classifiers trained separately for (1) disease classification and (2) synthetic noise detection. Classification performance was evaluated using AUC and F1-score.
- **Implementation and Computing Environment**: All analyses were performed using Python 3.x, PyTorch ≥ 2.0, Hugging Face Transformers, and scikit-learn. Image processing was parallelized using ThreadPoolExecutor on CUDA-enabled GPUs for efficiency.
- **Statistical Analysis**: Comparative performance across models and datasets was summarized descriptively. Disease classification and noise detection AUC/F1 metrics were used to assess model robustness and to quantify each model’s inherent noise-filtering ability.

**Findings**

Both foundation models demonstrated a clear distinction between their performance on clinical disease classification and synthetic noise detection tasks, supporting the hypothesis that embeddings inherently suppress non-clinical artifacts. Across the NIH-CXR14 and Emory CXRv2 datasets, RAD-DINO and DINOv3 achieved strong disease classification results, with AUC values ranging from 0.71 to 0.91 for cardiomegaly, lung lesion, and edema detection. RAD-DINO consistently outperformed DINOv3 in clinical classification, achieving an AUC of 0.91 for cardiomegaly and 0.91 for edema on NIH-CXR14, demonstrating superior domain-specific representation.

In contrast, both models showed markedly poor performance in detecting synthetic noise, with most AUC values near random chance (0.50–0.71). The weakest detection was observed for diagonal line noise (AUC 0.50–0.58), while DINOv3 exhibited slight sensitivity to larger geometric artifacts, achieving AUC 0.87 for circle noise with radius 2 pixels. Despite this limited noise detection, both models maintained high disease classification accuracy, indicating that embeddings selectively eliminate irrelevant perturbations while preserving clinically meaningful structures.

F1-scores for disease classification were modest (0.04–0.57), reflecting dataset imbalance, but consistently higher for shape detection due to balanced binary classes. Cross-dataset testing revealed reduced generalization from NIH-CXR14 to Emory CXRv2, emphasizing domain dependency and distributional shift effects. Overall, the findings confirm that foundation model embeddings function as intrinsic noise filters, prioritizing diagnostic features over artificial patterns and sustaining reliable performance even in the presence of image perturbations.

## Key Features

- Large-scale ablation study evaluating intrinsic noise-filtering properties of foundation model embeddings using over 249,000 chest X-rays from NIH-CXR14 and Emory CXRv2 datasets.
- Comparative analysis of two state-of-the-art Vision Transformer (ViT) architectures: RAD-DINO (domain-specific medical model) and DINOv3 (general-purpose foundation model).
- Controlled synthetic noise injection pipeline introducing geometric artifacts (circles, squares, diagonal lines) to quantify model robustness and feature preservation.
- Embedding-level evaluation using logistic regression classifiers to separately measure disease classification and noise detection performance.
- Evidence that embeddings suppress non-clinical artifacts while maintaining high diagnostic accuracy, confirming their function as intrinsic noise eliminators.
- Integration of AUC and F1 metrics for comprehensive assessment of classification quality and robustness across datasets.
- Cross-institutional validation demonstrating performance consistency and highlighting distributional shifts between datasets.
- Scalable and reproducible computational framework using PyTorch, Hugging Face Transformers, and CUDA-based parallelization for high-throughput analysis.

## Results

- **Disease Classification (AUC)**:
   - Cardiomegaly: RAD-DINO – 0.91 (NIH-CXR14), 0.83 (Emory CXRv2); DINOv3 – 0.87 (NIH-CXR14), 0.80 (Emory CXRv2).
   - Lung Lesion: RAD-DINO – 0.79 (NIH-CXR14), 0.84 (Emory CXRv2); DINOv3 – 0.71 (NIH-CXR14), 0.73 (Emory CXRv2).
   - Edema: RAD-DINO – 0.91 (NIH-CXR14), 0.82 (Emory CXRv2); DINOv3 – 0.89 (NIH-CXR14), 0.77 (Emory CXRv2).
   - *Interpretation*: RAD-DINO consistently outperformed DINOv3 on clinical tasks, demonstrating that domain-specific pretraining on radiological data enhances diagnostic robustness.
- **Synthetic Noise Detection (AUC)**:
   - 4×4 Square: 0.54–0.71 across models and datasets.
   - 8×8 Square: DINOv3 achieved 0.82 (Emory CXRv2), RAD-DINO averaged 0.61.
   - Diagonal Lines (4×4 / 8×8): 0.50–0.58 for both models, approximating random chance.
   - Circles: Radius 1 – 0.51–0.68; Radius 2 – up to 0.87 (DINOv3 on NIH-CXR14).
   - *Interpretation*: Both models showed minimal ability to detect small synthetic artifacts, confirming that embeddings suppress non-clinical geometric noise during feature encoding.
- **F1-Score Comparison**:
   - Disease classification: 0.04–0.57, affected by dataset imbalance.
   - Noise detection: 0.51–0.79, higher due to balanced class structure.
   - *Interpretation*: Although noise detection achieved higher F1-scores, AUC-based analyses confirmed that clinical signals dominate embedding representations.
- **Cross-Dataset Performance**:
   - Disease detection performance decreased by 5–12% when transferring from NIH-CXR14 to Emory CXRv2.
   - *Interpretation*: Domain shift impacts generalization, but the preservation of disease classification performance despite noise confirms intrinsic embedding robustness.
- **Overall Observation**:
   - Foundation model embeddings act as noise eliminators, filtering out irrelevant features while retaining essential diagnostic information.
   - This property explains the sustained high AUCs for disease tasks despite synthetic perturbations, underscoring the value of embeddings in real-world, imperfect imaging environments.

## Overall Conclusion

This study provides empirical evidence that foundation model embeddings function as intrinsic noise eliminators in medical imaging. Through controlled ablation experiments on over 249,000 chest radiographs from NIH-CXR14 and Emory CXRv2, both RAD-DINO and DINOv3 demonstrated strong disease classification performance while exhibiting minimal sensitivity to synthetic noise perturbations. These results indicate that the embedding layers selectively suppress non-clinical image artifacts, preserving diagnostically relevant features that contribute to robust downstream classification. The superior performance of RAD-DINO on clinical tasks underscores the benefits of domain-specific pretraining, while DINOv3’s limited noise responsiveness suggests a broader generalization to geometric patterns. Together, these findings highlight the role of embeddings as the representational core that enables foundation models to maintain diagnostic accuracy even under degraded imaging conditions. This intrinsic noise-filtering capability has significant implications for deploying AI systems in real-world radiology, where imaging quality varies widely. Future work will expand these ablation studies to additional imaging modalities and investigate the mechanisms through which self-supervised learning drives the emergence of this robust, noise-tolerant behavior.