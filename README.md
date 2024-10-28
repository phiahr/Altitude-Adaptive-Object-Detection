# Investigating Altitude-Adaptive Methods for Enhancing Small Object Detection on UAVs

**Author:** Philipp Ahrendt  
**Degree:** Master’s Programme, ICT Innovation, KTH Royal Institute of Technology  
**Date:** October 17, 2024

---

## Abstract

Computer vision is vital for the recent development of aerial vision-based
applications, however, small object detection remains a challenge even
for state-of-the-art models such as YOLOv7-tiny. Object detection from
Unmanned Aerial Vehicles (UAVs) is particularly affected because of their
sometimes high flight altitude leading to a greater amount of small objects
to detect, while their limited storage and computing power capacity restricts
the model complexity. Contextual information such as the flight altitude is
often readily available from onboard sensors and can serve as relevant prior
knowledge to a neural network learning to predict the size, location, and class
of objects in an image. Despite that, research in this direction is sparse and
focuses on specific applications, demanding more general approaches. This
thesis investigates various methods to integrate altitude information into the
learning process of an object detection network. The focus of this work lies in
analyzing the influence of the proposed methods on precision, recall, and mean
average precision (mAP) for aerial datasets across different altitude levels
and in general. We demonstrate that concatenating the input image with the
altitude information or adding an auxiliary head that predicts the altitude from
an image can help to slightly boost the performance. Furthermore, despite a
reduced average precision, a dynamic loss based on altitude can offer more
controlled fine-tuning of the model depending on the specific requirements
of a UAV-based detection task. However, our results also showed that the
greatest benefits stemmed from the addition of a small object detection head
and the removal of the largest head which is unrelated to flight altitude.
Nevertheless, this approach could potentially be further improved through one
of the altitude adaptive methods since they are not mutually exclusive. The
proposed methods and benchmarks provide a foundation for future research
in the area of altitude-aware models as well as validate research on UAV-
optimized YOLO models. Overall, this work provides an overview of how
contextual information could be integrated into an existing object detection
model and its effects on the training process and inference performance.

## Keywords
Small Object Detection, Altitude adaptive, Unmanned Aerial Vehicles (UAV),
YOLOv7-tiny

<!-- This thesis addresses the challenge of detecting small objects from Unmanned Aerial Vehicles (UAVs) flying at high altitudes. Limited by their storage and processing capacity, UAVs often struggle with object detection, especially for smaller objects. Using altitude data as contextual information, this work explores how incorporating this data can improve detection performance in models like YOLOv7-tiny. Various methods, including altitude injection and dynamic loss adjustments, were tested. The findings indicate that adding an auxiliary head for altitude prediction and using altitude-adaptive loss can offer controlled improvements in detection performance. Overall, this research contributes to altitude-aware UAV models and supports future advancements in object detection on constrained devices. -->

## Table of Contents

- [Investigating Altitude-Adaptive Methods for Enhancing Small Object Detection on UAVs](#investigating-altitude-adaptive-methods-for-enhancing-small-object-detection-on-uavs)
  - [Abstract](#abstract)
  - [Keywords](#keywords)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Background](#background)
  - [Methods](#methods)
  - [Results and Analysis](#results-and-analysis)
  - [Conclusion and Future Work](#conclusion-and-future-work)
  - [Full Thesis](#full-thesis)
  - [Citation](#citation)

---

## Introduction

High-altitude UAV-based object detection presents unique challenges. This thesis investigates how altitude information, readily available through UAV sensors, can be integrated into object detection models. The core question addressed is:

> "Can altitude data improve small object detection performance through adaptive or learning-based approaches?"

This project assesses whether altitude-informed methods can enhance detection accuracy while maintaining efficiency.

## Background

Object detection in UAVs is crucial for applications ranging from wildlife monitoring and environmental protection to search-and-rescue missions. However, high-altitude flying conditions create issues with object size variation, perspective changes, and processing constraints. This thesis builds on advancements in UAV-specific adaptations of the YOLOv7-tiny model and explores methods to enhance its detection performance using altitude as a contextual variable.

## Methods

This research used a combination of experimental and quantitative methods to evaluate various approaches for integrating altitude data into object detection:

- **Dynamic Anchors**: Adjusting anchor boxes based on altitude.
- **Altitude Injection**: Integrating altitude data at different points in the network architecture.
- **Auxiliary Altitude Prediction**: Adding an auxiliary head to predict altitude alongside object detection.
- **Altitude-Adaptive Loss**: Modifying loss calculations based on altitude to improve sensitivity to object scale changes.
- **Exploratory Analysis**: Explore performance of different methods not related to dynamic altitude integration but still related to the overarching theme

The YOLOv7-tiny model served as the baseline, with altitude data enhancing prediction accuracy across different altitude levels.

## Results and Analysis

Experiments demonstrated that:
- **Dynamic Anchors and Dynamic Loss** did not yield performance increase although dynamic loss could be used as a method to better fine-tune recall and precision depending on the altitude
- **Altitude Injection and Auxiliary Prediction** showed slight performance gains, confirming altitude data’s utility for model adaptation.
- **Additional Small Object Detection Head**: This modification showed the most significant improvement by tailoring the network to detect smaller objects more effectively, though further improvements could be achieved by combining with altitude-adaptive methods.

## Conclusion and Future Work

Incorporating altitude data into object detection models holds potential for applications requiring accurate detection at varying heights. While the tested approaches showed measurable benefits, further research could explore combining altitude-adaptive methods or enhancing the robustness of this study. This work underscores the value of context-aware deep learning for UAV object detection.

## Full Thesis

The full thesis can be accessed [here](Masters_Thesis_Philipp_Ahrendt.pdf).

## Citation

If referencing this work, please cite as follows:

```plaintext
Ahrendt, Philipp. "Investigating Altitude-Adaptive Methods for Enhancing Small Object Detection on UAVs." Master’s Thesis, KTH Royal Institute of Technology, 2024.
