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

*Input Module (Video Stream)
|

*Object Detection (YOLOv7) -> Detects vehicles, pedestrians, etc.
|

*Spatial-Temporal Feature Extraction -> Tracks objects over frames
|

*Accident Classification CNN -> Analyzes features for crash prediction
|

*Alert System -> Triggers alerts if probability exceeds threshold

## 📊 Dataset & Model Training

- **Dataset:** Trained and evaluated on a combination of public datasets ([CCD](https://crisisnlp.qcri.org/ccd)), [Dashcam Accident Dataset (DAD)](https://aliensunmin.github.io/project/dashcam/), and custom-collected footage.
- **Preprocessing:** Applied frame sampling, spatial normalization, and data augmentation (rotation, flipping, contrast changes) to improve model generalization.
- **Training:** The model was trained on an NVIDIA GTX 3080, using a combination of cross-entropy loss and custom temporal consistency constraints.

## 📸 Demo / Results

![Accident Detection Demo](results/demo.gif) <!-- Replace with a link to your actual GIF -->

*Example of the system correctly detecting a collision and generating an alert.*

## 🔧 Installation & Setup

1.  **Clone the repository and navigate into it:**
    ```bash
    git clone https://github.com/AliSayyed123/accident-detection-system.git
    cd accident-detection-system
    ```

2.  **Install dependencies:**
    It is recommended to use a virtual environment (`venv` or `conda`).
    ```bash
    pip install -r requirements.txt
    ```

3.  **Download model weights:**
    *   Download the pre-trained YOLOv7 weights from the official repository.
    *   Download the custom accident classification model weights from [link to your uploaded weights, e.g., Google Drive]. Place them in the `models/` directory.

## 🚀 How to Run

1.  **For a video file:**
    ```bash
    python detect.py --source path/to/your/video.mp4 --weights models/accident_model.pt
    ```

2.  **For a webcam stream:**
    ```bash
    python detect.py --source 0 --weights models/accident_model.pt
    ```

3.  **For a remote video stream (URL):**
    ```bash
    python detect.py --source https://your-video-stream.com/stream.m3u8 --weights models/accident_model.pt
    ```

