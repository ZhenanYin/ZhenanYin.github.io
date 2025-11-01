---
layout: page
title: "Triton Town Autonomous Vehicles"
description: An engineering study for developing a deep learning-driven autonomous vehicle with real-time navigation and object detection using Raspberry Pi and computer vision algorithms.
img: assets/img/projects/car.png
year: 2024
authors: Zhenan Yin, advised by Prof. Maurício de Oliveira & Prof. Jack Silberman
redirect: false
---

## Overview

Developed a fully autonomous vehicle capable of real-time navigation in indoor and outdoor environments using Raspberry Pi, TensorFlow, and OpenCV. The system integrates deep learning-based perception with feedback control algorithms to achieve end-to-end autonomous driving.

## Key Achievements

### Performance Improvements
- **Driving accuracy**: Improved from 75% → 97%
- **Failure rate**: Reduced from 25% → 3% after 20 test runs
- **Autonomous laps**: 10 indoor + 6 outdoor consecutive laps without intervention

### Technical Performance
- **Object detection**: 85% accuracy on CIFAR-100 dataset
- **Real-time inference**: <150ms latency per frame on Raspberry Pi
- **Training dataset**: 35,000 driving images across diverse conditions

## System Architecture

### Hardware
- **Controller**: Raspberry Pi (central processing unit)
- **Sensors**: Camera module for visual perception
- **Actuators**: Motor drivers for steering and speed control

### Software Stack
- **Deep Learning**: TensorFlow for CNN training and inference
- **Computer Vision**: OpenCV for image preprocessing
- **Control Framework**: DonkeyCar library for end-to-end pipeline
- **Training**: GPU clusters for model optimization

### Deep Learning Pipeline
1. **Data Collection**: 35,000 labeled driving frames
2. **Model Training**: CNN architecture with transfer learning
3. **Object Detection**: Lane boundaries and obstacle recognition
4. **Steering Prediction**: Neural network-based control
5. **Real-time Inference**: On-board Raspberry Pi deployment

## Key Features

- **End-to-end autonomy**: Direct mapping from camera input to steering control
- **Adaptive control**: Feedback-based trajectory correction and speed adjustment
- **Robust perception**: Operates under varying lighting and terrain conditions
- **Low-cost platform**: Scalable design using affordable embedded hardware

## Technical Highlights

### Model Optimization
- GPU-accelerated training with adaptive learning rates
- Data augmentation: flipping, brightness variation
- Transfer learning from CIFAR-100 for faster convergence

### System Reliability
Through iterative testing and calibration:
- Progressive hardware-software optimization
- Sensor calibration and control tuning
- Real-world validation across multiple environments

## Applications

This project demonstrates practical autonomous vehicle capabilities for:
- Educational robotics and AI research
- Rapid prototyping of perception algorithms
- Low-cost autonomous navigation systems

## Supervision

Conducted under Prof. Maurício de Oliveira (Mechanical and Aerospace Engineering) and Prof. Jack Silberman (Halıcıoğlu Data Science Institute) as part of ECE 148, UC San Diego.