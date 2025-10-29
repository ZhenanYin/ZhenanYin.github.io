---
layout: page
title: "Conformal Ultrasonic Device for Non-Invasive Central Blood Pressure Monitoring"
description: An engineering study focused on developing a conformal ultrasonic device using stretchable circuit patterning for non-invasive monitoring of central blood pressure and deep-tissue hemodynamics.
img: assets/img/projects/ultrasonic.png
year: 2018
authors: Chonghe Wang, Xiaoshi Li, Hongjie Hu, Lin Zhang, Zhenlong Huang, Muyang Lin, Zhuorui Zhang, Zhenan Yin, Brady Huang, Hua Gong, Shubha Bhaskaran, Yue Gu, Mitsutoshi Makihata, Yuxuan Guo, Yusheng Lei, Yimu Chen, Chunfeng Wang, Yang Li, Tianjiao Zhang, Zeyu Chen, Albert P. Pisano, Liangfang Zhang, Qifa Zhou, and Sheng Xu
venue: Nature Biomedical Engineering, 2018
links:
  - name: Paper
    url: https://www.nature.com/articles/s41551-018-0287-x
redirect: false
---

## Overview

This project presents the development of a stretchable conformal ultrasonic device designed for non-invasive, continuous monitoring of central blood pressure and deep-tissue hemodynamics. Conducted under the supervision of Prof. Sheng Xu (Department of NanoEngineering, University of California San Diego) at the Xu Research Group, the research focused on the fabrication, characterization, and validation of a soft, skin-conformal ultrasound transducer capable of maintaining signal integrity under natural body motion. The work integrated stretchable circuit patterning, laser micro-cutting for electrode precision, and soft elastomeric encapsulation to ensure mechanical flexibility, durability, and biocompatibility.

The conformal ultrasonic patch was evaluated through experimental measurements of arterial pulsation from the carotid artery and internal jugular vein, confirming its ability to capture high-fidelity waveforms correlated with central blood pressure. The results demonstrated that the device achieved stable acoustic coupling and reliable signal acquisition even during motion, marking a significant advancement in wearable biomedical sensing technology. This research contributed to the publication “Monitoring of the Central Blood Pressure Waveform via a Conformal Ultrasonic Device” in Nature Biomedical Engineering (2018), establishing a foundational step toward continuous, non-invasive cardiovascular monitoring.

**Motivation for the project**

Cardiovascular diseases remain the leading cause of mortality worldwide, emphasizing the critical need for continuous and accurate blood pressure monitoring to support early diagnosis and prevention. Conventional cuff-based sphygmomanometers and invasive catheter systems provide only intermittent or hospital-limited measurements, which fail to capture dynamic blood pressure fluctuations under real-world conditions. Central blood pressure, which reflects hemodynamic load on major organs, is a more accurate predictor of cardiovascular risk than peripheral measurements. However, existing methods for central pressure assessment are either invasive or require bulky and immobile equipment.

This project was motivated by the goal of developing a non-invasive, wearable ultrasound device capable of continuously monitoring central blood pressure waveforms with clinical-grade accuracy. By leveraging advances in soft materials, stretchable electronics, and conformal ultrasound transducers, the study aimed to overcome the mechanical and acoustic limitations of rigid sensors. The ability to maintain intimate contact with curved and moving body surfaces—such as the neck and chest—enables real-time monitoring of vascular health without patient discomfort. This innovation represents a transformative step toward continuous cardiovascular monitoring, integrating bioengineering and materials science to create next-generation medical devices for personalized healthcare.

**Methodology**
- Metabolic Model Reconstruction: Two genome-scale metabolic reconstructions were employed—Bordbar2010 Macrophage Metabolism (*iAB-AMØ-1410*) and Bordbar2010 M. tuberculosis Macrophage (*iAB-AMØ-1410-Mt-661*).
- Computational Framework: Analyses were implemented in COBRApy (Constraint-Based Reconstruction and Analysis in Python) to perform:
    - Flux Balance Analysis (FBA) for steady-state flux optimization and biomass growth prediction.
    - Flux Variability Analysis (FVA) under default and 90% optimality constraints to evaluate reaction redundancy and flexibility.
- Reaction Characterization: Essential, reversible, dead, and fixed reactions were systematically identified through iterative reaction knockout and flux analysis.
- Drug Target Identification: Essential reaction sets were compared between infected and non-infected models to isolate reactions unique to Mtb infection as candidate drug targets.
- Medium Minimization: Nutrient dependency was quantified by minimizing exchange reactions to identify substrates critical for optimal biomass generation.

**Findings**

The project combined materials engineering, device fabrication, and experimental validation to design a soft, skin-conformal ultrasonic system for continuous cardiovascular monitoring. The device was built on a multilayered structure consisting of a stretchable copper–polyimide circuit network embedded within a soft elastomeric substrate that provided both mechanical flexibility and biocompatibility. A thin piezoelectric transducer array was patterned through laser micro-cutting and encapsulated using silicone-based elastomers to maintain acoustic transparency while protecting the electrodes from deformation and environmental exposure. The fabrication process emphasized maintaining uniform electrical connectivity during repetitive bending and stretching, ensuring device stability under physiological motion.

The conformal patch was applied to the carotid artery and internal jugular vein regions, where it continuously transmitted and received ultrasonic waves to measure arterial pulsation. The acquired ultrasonic signals were processed to reconstruct blood pressure waveforms and quantify hemodynamic parameters such as pulse transit time and waveform morphology. Comparative analyses against standard ultrasound probes validated the accuracy of the wearable system, confirming its ability to maintain consistent acoustic coupling and waveform fidelity under dynamic conditions. The experimental results established the feasibility of integrating soft electronics and conformal ultrasound transduction into wearable systems capable of reliable, non-invasive cardiovascular monitoring.

## Key Features

- Development of a soft, skin-conformal ultrasonic patch capable of continuous and non-invasive central blood pressure monitoring.
- Integration of stretchable copper–polyimide circuits with elastomeric encapsulation for mechanical flexibility and biocompatibility.
- Use of laser micro-cutting fabrication for precise electrode patterning and high transducer density.
- Maintenance of stable acoustic coupling and signal fidelity during body motion, enabling reliable long-term monitoring.
- Successful measurement of carotid and jugular pulse waveforms, demonstrating correlation with central hemodynamic parameters.
- Validation of performance against standard rigid ultrasound probes, confirming comparable waveform quality.
- A foundational step toward wearable, continuous cardiovascular monitoring systems for clinical and home-based health applications.

## Overall Conclusion

This project demonstrates the successful design and fabrication of a stretchable conformal ultrasonic device for continuous, non-invasive monitoring of central blood pressure and deep-tissue hemodynamics. By integrating soft materials, stretchable circuitry, and precision microfabrication, the device achieves reliable acoustic coupling and high-fidelity waveform capture even under natural body motion. Experimental validation through carotid and jugular measurements confirmed that the system can accurately reconstruct central blood pressure waveforms comparable to those obtained by clinical ultrasound instruments. These results establish a critical foundation for the development of wearable ultrasound technologies that combine clinical-grade accuracy with user comfort. The work represents an important advance toward the realization of continuous cardiovascular monitoring and personalized health assessment through flexible bioelectronic systems.