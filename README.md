# Real-Time Accident Detection System

A robust deep learning system that automatically detects vehicle accidents in real-time from dashcam and CCTV footage. This project served as the foundation for my research paper published in **IEEE CISCT 2024**, where the model achieved **92% accuracy**.

## 🚀 Impact & Key Achievements

- **92% Accuracy:** Achieved high precision in identifying accidents across diverse driving conditions.
- **15% Reduction in False Positives:** Engineered post-processing techniques to significantly minimize false alarms.
- **Real-Time Performance:** Optimized the model for processing streamed video footage with low latency.
- **Published Research:** This implementation is detailed in my paper presented at the IEEE Conference on Intelligent Systems and Communication Technologies (CISCT 2024).

## 🛠️ Tech Stack

- **Deep Learning Framework:** PyTorch
- **Model Architecture:** YOLOv7 (Object Detection) + Custom CNN (Accident Classification)
- **Computer Vision:** OpenCV (Video processing, bounding boxes, visualization)
- **Programming Language:** Python

## 📁 Project Architecture

The system follows a modular two-stage pipeline:
Input Module (Video Stream)
|

Object Detection (YOLOv7) -> Detects vehicles, pedestrians, etc.
|

Spatial-Temporal Feature Extraction -> Tracks objects over frames
|

Accident Classification CNN -> Analyzes features for crash prediction
|

Alert System -> Triggers alerts if probability exceeds threshold
