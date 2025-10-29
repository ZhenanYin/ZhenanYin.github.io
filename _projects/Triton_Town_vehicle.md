---
layout: page
title: "Triton Town Autonomous Vehicles"
description: An engineering study for developing a deep learning-driven autonomous vehicle capable of real-time navigation and object detection through integrated hardware design and computer vision algorithms.
img: assets/img/projects/car.png
year: 2024
authors: Zhenan Yin, advised by Prof. Maurício de Oliveira & Prof. Jack Silberman
redirect: false
---

## Overview

This project presents the design and implementation of a deep learning-based autonomous vehicle capable of real-time navigation, perception, and decision-making in structured and unstructured environments. Conducted under the supervision of Prof. Maurício de Oliveira (Department of Mechanical and Aerospace Engineering) and Prof. Jack Silberman (Halıcıoğlu Data Science Institute), this work was part of the Triton Town Autonomous Vehicles Project at UCSD. The project integrated embedded systems, computer vision, and control algorithms to build a reliable autonomous platform using Raspberry Pi, TensorFlow, and OpenCV. Deep convolutional neural networks (CNNs) were trained to perform visual recognition tasks such as lane detection and obstacle avoidance, while reinforcement-based driving models were optimized for smooth trajectory control. Through iterative design, sensor calibration, and model refinement, the vehicle successfully achieved end-to-end autonomous driving across both indoor and outdoor test tracks.

**Motivation for the project**

Autonomous vehicles represent a critical advancement in intelligent transportation, promising to reduce human error, improve mobility efficiency, and enhance road safety. However, developing robust self-driving systems requires integrating complex perception, decision-making, and control components within constrained hardware environments. Traditional rule-based navigation systems struggle to generalize across diverse driving conditions, particularly in dynamic or unstructured environments. Advances in deep learning and computer vision now enable vehicles to learn from real-world sensory data, allowing them to perceive and respond to their surroundings autonomously. This project was motivated by the goal of designing a low-cost, scalable autonomous driving prototype that combines embedded hardware with machine learning algorithms to demonstrate reliable end-to-end autonomy. By integrating real-time visual processing, neural network-based decision models, and feedback control, the project sought to bridge the gap between theoretical research and practical implementation in autonomous vehicle systems.

**Methodology**
- **Hardware Integration**: Designed and assembled the autonomous vehicle platform using Raspberry Pi as the central processing unit, integrated with electronic control modules, motor drivers, and camera sensors to enable real-time data acquisition and actuation.
- **Software Framework**: Installed and configured TensorFlow, OpenCV, and the DonkeyCar library to provide an end-to-end machine learning pipeline for perception, decision-making, and control. The system architecture supported modular experimentation across multiple algorithms and network configurations.
- **Data Collection and Preprocessing**: Captured and labeled over 35,000 driving image frames across diverse lighting and terrain conditions. Images were standardized through normalization and resizing to prepare for CNN training.
- **Deep Learning Model Development**: Implemented Convolutional Neural Networks (CNNs) trained on the CIFAR-100 dataset and custom driving data to perform real-time object detection, lane following, and steering prediction. Transfer learning was applied to improve model convergence and accuracy.
- **Model Optimization and Training**: Deployed GPU-based training pipelines for efficient model iteration, leveraging adaptive learning rate schedules and data augmentation (flipping, brightness variation) to improve generalization.
- **Control Algorithm**: Integrated the trained neural models with feedback-based control systems for smooth trajectory correction, speed adjustment, and obstacle avoidance in both simulated and physical environments.
- **Testing and Validation**: Conducted 20 iterative test runs to evaluate system stability and performance. Progressive tuning reduced the vehicle’s failure rate from 25% to 3%, achieving reliable operation over 10 indoor and 6 outdoor laps in full autopilot mode.

**Findings**

Experimental validation demonstrated that the autonomous vehicle successfully achieved reliable end-to-end navigation across both indoor and outdoor test environments. After iterative calibration and model refinement, the overall driving accuracy improved from 75% to 97%, with the failure rate reduced from 25% to 3%. The CNN-based perception module achieved over 85% object detection accuracy on the CIFAR-100 and custom image datasets, enabling consistent recognition of road boundaries and obstacles. Real-time inference on the Raspberry Pi maintained an average latency of under 150 milliseconds per frame, ensuring smooth control response during autonomous operation. The system demonstrated robustness under varying lighting and surface conditions, completing 10 indoor and 6 outdoor laps without manual intervention. These results confirm the feasibility of implementing low-cost, deep learning-driven autonomous navigation systems using embedded hardware and open-source software frameworks.

## Key Features

- End-to-end autonomous navigation framework integrating perception, decision-making, and control in real time.
- Deep convolutional neural network (CNN) models for lane detection, obstacle recognition, and steering prediction.
- Embedded implementation using Raspberry Pi for on-board computation and sensor control.
- Integration of TensorFlow, OpenCV, and DonkeyCar library to streamline data collection, training, and deployment.
- Adaptive feedback control algorithm enabling smooth trajectory correction and speed adjustment.
- Data-driven optimization through iterative training on over 35,000 driving images under diverse environmental conditions.
- Real-time performance with average inference latency below 150 ms and failure rate reduced to 3% after multi-run tuning.
- Scalable and low-cost prototype design suitable for educational research and rapid experimentation in autonomous vehicle systems.

