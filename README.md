# Efficient Object Detection with YOLOv5 on DOTA Dataset
## Overview
This project implements an object detection solution using the YOLOv5 model on the DOTA (Dataset for Object Detection in Aerial Images). The goal is to detect and classify multiple objects in aerial images with high precision and efficiency. The model is optimized for limited-resource environments, such as Google Colab's free tier.

#### (Please note that I'm still working on the final submission, and this is just a summary of what the actual project may look like and implementation steps that I've decided as of now.)

---

## Dataset
### DOTA: Dataset for Object Detection in Aerial Images
**Description: DOTA is a large-scale aerial image dataset containing annotations for 15 object categories, such as vehicles, buildings, and ships.**
**Challenges Addressed:**
 - Multi-scale objects
 - Complex backgrounds
 - Irregular object orientations
 - **Dataset Link: [DOTA Official Website](https://captain-whu.github.io/DOTA/dataset.html)**
### Key Features of DOTA
 - Contains ~2,800 images and ~280,000 labeled object instances.
 - Objects annotated with rotated bounding boxes to handle orientations.
 - **Use cases: Aerial surveillance, disaster management, and urban planning.**

---

## Model Architecture
### YOLOv5
 - #### Why YOLOv5?
    - Lightweight and efficient, ideal for real-time and resource-constrained environments.
    - Provides state-of-the-art accuracy for object detection tasks with pre-trained weights for transfer learning.
    - Robust to scale variations and dense object environments.
 - #### Key Features:
    - Speed: Near real-time inference capability.
    - Accuracy: Competitive mean Average Precision (mAP) for aerial imagery.
    - Flexibility: Supports multiple object sizes and custom dataset integration.
    - Variants: Starting with yolov5s for faster training on Colab, with options to scale up to larger models (yolov5m, yolov5l, etc.) if needed.

#### References
- [YOLOv5 GitHub Repository](https://github.com/ultralytics/yolov5)
- [YOLOv4 Paper (Predecessor to YOLOv5)](https://arxiv.org/abs/2004.10934)

---

## Solution Workflow
### 1. Dataset Preparation
 - Convert DOTA annotations into YOLO format: [class_id, x_center, y_center, width, height].
 - Apply data augmentation (e.g., scaling, flipping, rotation) to enhance training data diversity.
### 2. Model Training
 - Platform: Google Colab Free Tier
 - Steps:
    - Use pre-trained weights (yolov5s.pt) for transfer learning.
    - Configure training parameters:
    - Image size: 640 pixels
    - Batch size: 8
    - Epochs: 20–50
 - Save checkpoints to Google Drive to ensure progress retention.

### 3. Evaluation
 - Measure performance using:
    - mAP (mean Average Precision)
    - IoU (Intersection over Union)
 - Validate model robustness on:
    - Varying object scales.
    - Complex orientations in aerial images.

### 4. Deployment
 - Real-time inference using YOLOv5’s integrated tools or OpenCV.
 - Applications in surveillance, urban planning, and disaster response.

---

## Research Papers and References
### Dataset
 - [DOTA Paper: DOTA: A Large-Scale Dataset for Object Detection in Aerial Images](https://arxiv.org/abs/1711.10398)
### Model
 - [YOLOv4 Paper (Foundation for YOLOv5): YOLOv4: Optimal Speed and Accuracy of Object Detection](https://arxiv.org/abs/2004.10934)
 - [YOLOv5 GitHub Repository: YOLOv5 by Ultralytics](https://github.com/ultralytics/yolov5)