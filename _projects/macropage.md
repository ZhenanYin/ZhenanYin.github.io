---
layout: page
title: "The Connection Between Mycobacterium Tuberculosis and Macrophage Cells in Lung Cancer Progression"
description: An exploratory study for investigating how Mycobacterium tuberculosis influences macrophage metabolism and contributes to lung cancer development through genome-scale metabolic modeling.
img: assets/img/projects/macrophage.png
year: 2024
authors: Zhenan Yin, advised by Dr. Bridget Bannerman & Prof. Jorge Júlvez
redirect: false
---

## Overview

This project presents an exploratory systems biology investigation into how *Mycobacterium tuberculosis* (Mtb) infection perturbs macrophage metabolism and contributes to lung cancer progression. The study was conducted under the supervision of Dr. Bridget Bannerman (Department of Medicine and Biochemistry, University of Cambridge) and Prof. Jorge Júlvez (Information and Communication Technologies, University of Zaragoza) as part of the Online Summer Research Program at Pembroke College, University of Cambridge.

**Motivation for the project**

Lung cancer remains one of the most fatal malignancies globally, with increasing evidence suggesting a bidirectional association between *Mycobacterium tuberculosis* infection and tumorigenesis. Chronic Mtb-induced inflammation promotes cellular instability and metabolic reprogramming in macrophages, which may accelerate malignant transformation. Elucidating the metabolic mechanisms underlying Mtb–macrophage interactions offers valuable insight for identifying potential metabolic drug targets to disrupt infection-associated cancer pathways.

**Methodology**
- Metabolic Model Reconstruction: Two genome-scale metabolic reconstructions were employed—Bordbar2010 Macrophage Metabolism (*iAB-AMØ-1410*) and Bordbar2010 M. tuberculosis Macrophage (*iAB-AMØ-1410-Mt-661*).
- Computational Framework: Analyses were implemented in COBRApy (Constraint-Based Reconstruction and Analysis in Python) to perform:
    - Flux Balance Analysis (FBA) for steady-state flux optimization and biomass growth prediction.
    - Flux Variability Analysis (FVA) under default and 90% optimality constraints to evaluate reaction redundancy and flexibility.
- Reaction Characterization: Essential, reversible, dead, and fixed reactions were systematically identified through iterative reaction knockout and flux analysis.
- Drug Target Identification: Essential reaction sets were compared between infected and non-infected models to isolate reactions unique to Mtb infection as candidate drug targets.
- Medium Minimization: Nutrient dependency was quantified by minimizing exchange reactions to identify substrates critical for optimal biomass generation.

**Findings**

Computational simulation revealed that the Mtb-infected macrophage model contained 375 essential reactions, compared to 117 in the healthy macrophage model. After eliminating redundant and exchange reactions, 223 unique essential reactions were identified as candidate drug targets. Flux analysis indicated that Mtb infection markedly reduced biomass production rates, underscoring the energetic burden imposed by infection.

## Key Features

- Genome-scale metabolic modeling integrating host–pathogen co-metabolism.
- COBRApy-based implementation of FBA and FVA for metabolic flux characterization.
- Systematic essential reaction screening for identifying infection-specific metabolic dependencies.
- Quantitative classification of reversible, dead, and fixed reactions under variable flux constraints.
- Medium minimization to evaluate nutrient essentiality and metabolic bottlenecks.

## Results

- Biomass Growth Rate (FBA):
    - Normal macrophage model: 0.02699 h⁻¹
    - Mtb-infected macrophage model: 0.00210 h⁻¹
    - *Interpretation*: Infection causes a drastic reduction in metabolic efficiency due to increased energy consumption by Mtb.
- Essential Reactions:
    - Normal model: 117 reactions
    - Infected model: 375 reactions
    - Drug target candidates (unique to infected model): 223 reactions
- Reaction Classification (Mtb-infected model):
    - Reversible: 1365 → 343 → 445 (default → FVA → FVA at 90%)
    - Dead: 63 → 1426 → 1949
    - Fixed: 63 → 1426 → 1951
- Medium Minimization Results:
    - Nineteen limiting exchange reactions were identified, with glucose (EX_glc) and glutamine (EX_gln) proving essential. Blocking either flux reduced biomass growth to near zero, confirming their critical role in sustaining infected macrophage metabolism.

## Overall Conclusion

This study provides a computational framework to elucidate how *M. tuberculosis* infection reconfigures macrophage metabolism and identifies infection-specific essential reactions as potential therapeutic targets. The combined use of COBRApy-based FBA/FVA, essential reaction mapping, and medium optimization establishes a reproducible pipeline for probing host–pathogen metabolic interactions. These findings advance the mechanistic understanding of Mtb-driven metabolic dysregulation and offer a foundation for targeted drug discovery aimed at mitigating Mtb-associated lung carcinogenesis.