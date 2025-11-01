---
layout: page
title: "The Connection Between Mycobacterium Tuberculosis and Macrophage Cells in Lung Cancer Progression"
description: An exploratory study for investigating how M. tuberculosis infection alters macrophage metabolism and identifies potential drug targets using genome-scale metabolic modeling.
img: assets/img/projects/macrophage.png
year: 2024
authors: Zhenan Yin, advised by Dr. Bridget Bannerman & Prof. Jorge Júlvez
redirect: false
---

## Overview

Chronic *Mycobacterium tuberculosis* (Mtb) infection promotes inflammation and metabolic reprogramming in macrophages, potentially accelerating lung cancer development. This computational study uses genome-scale metabolic modeling to identify infection-specific metabolic vulnerabilities as potential drug targets.

## Research Question

**How does Mtb infection alter macrophage metabolism, and which metabolic reactions are unique to infected cells?**

## Key Findings

### Metabolic Burden of Infection
- **Normal macrophage**: Biomass growth rate 0.02699 h⁻¹
- **Mtb-infected macrophage**: Biomass growth rate 0.00210 h⁻¹
- **92% reduction** in metabolic efficiency due to infection

### Drug Target Identification
- **117 essential reactions** in healthy macrophages
- **375 essential reactions** in infected macrophages
- **223 unique reactions** identified as candidate drug targets

### Critical Nutrients
Medium minimization revealed glucose and glutamine as essential substrates—blocking either flux reduced biomass growth to near zero.

## Methodology

### Genome-Scale Metabolic Models
- **iAB-AMØ-1410**: Normal macrophage metabolism
- **iAB-AMØ-1410-Mt-661**: Mtb-infected macrophage metabolism

### Computational Analysis (COBRApy)
1. **Flux Balance Analysis (FBA)**: Predicted biomass growth and steady-state flux
2. **Flux Variability Analysis (FVA)**: Evaluated reaction redundancy at 90% optimality
3. **Reaction Classification**: Identified essential, reversible, dead, and fixed reactions
4. **Systematic Knockout**: Compared infected vs. healthy models to isolate infection-specific dependencies

### Key Insight
By comparing essential reactions between healthy and infected models, we identified 223 infection-specific metabolic vulnerabilities that could be targeted therapeutically without affecting normal cell function.

## Clinical Implications

This computational framework enables:
- **Targeted drug discovery** for Mtb-associated lung cancer
- **Metabolic intervention strategies** to disrupt infection-driven tumorigenesis
- **Host-pathogen interaction insights** for understanding chronic infection consequences

## Supervision
Conducted under Dr. Bridget Bannerman (Department of Medicine and Biochemistry, University of Cambridge) and Prof. Jorge Júlvez (Information and Communication Technologies, University of Zaragoza) at Pembroke College, University of Cambridge.