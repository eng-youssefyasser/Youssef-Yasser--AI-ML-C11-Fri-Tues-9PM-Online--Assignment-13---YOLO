# 🔥 Fire and Smoke Detection using YOLOv8

## 📌 Project Overview

This project implements a real-time Fire and Smoke Detection system using **YOLOv8 Nano** and Deep Learning.

The main objective is to train an object detection model capable of identifying fire and smoke in images and videos. This project simulates a safety monitoring application that can help detect potential fire hazards automatically.

## 🎯 Objectives

- Prepare and process a Fire and Smoke detection dataset.
- Train a YOLOv8 object detection model.
- Evaluate model performance using standard detection metrics.
- Detect fire and smoke in unseen video footage.
- Save and visualize prediction results.

## 📂 Dataset

The dataset was obtained from Roboflow Universe.

- **Project:** Fire and Smoke Detector
- **Workspace:** gfo-fc1de
- **Version:** 14
- **Format:** YOLOv8
- **Classes:**
  - Fire (Class 0)
  - Smoke (Class 1)

🔗 [Dataset Source – Roboflow](https://universe.roboflow.com/gfo-fc1de/fire-and-smoke-detector-yykya/dataset/14)

The dataset is divided into three subsets:

- Training: 3,940 images
- Validation: 1,017 images
- Testing: 639 images

## 🛠️ Technologies Used

- Python
- YOLOv8 (Ultralytics)
- Roboflow
- PyTorch
- OpenCV
- Matplotlib
- Kaggle Notebook
- NVIDIA Tesla T4 GPU

## ⚙️ Model Training

The YOLOv8 Nano model was selected because it provides a lightweight architecture with relatively fast training and inference.

**Training Configuration:**

| Parameter | Value |
|---|---|
| Model | YOLOv8 Nano |
| Task | Object Detection |
| Image Size | 640 × 640 |
| Epochs | 50 |
| Batch Size | 16 |
| Device | NVIDIA Tesla T4 |
| Optimizer Patience | 10 |

The model was initialized using pretrained YOLOv8 Nano weights and fine-tuned on the Fire and Smoke dataset.

## 📊 Model Evaluation

The trained model achieved the following validation results:

| Metric | Score |
|---|---:|
| Precision | 0.662 |
| Recall | 0.529 |
| mAP@50 | 0.567 |
| mAP@50-95 | 0.276 |

### Class-wise Performance

| Class | Precision | Recall | mAP@50 |
|---|---:|---:|---:|
| Fire | 0.725 | 0.660 | 0.706 |
| Smoke | 0.599 | 0.398 | 0.428 |

The results show better detection performance for fire compared to smoke on the validation dataset.

## 🎥 Video Prediction

After training, the best model weights (`best.pt`) were loaded and used to perform inference on an unseen video.

The prediction process includes:

1. Loading the trained YOLO model.
2. Reading the input video.
3. Detecting fire and smoke in video frames.
4. Drawing bounding boxes around detected objects.
5. Displaying class labels and confidence scores.
6. Saving the annotated video.

## 📁 Project Outputs

The training process generates the following important files:

- `best.pt`: Best-performing model weights.
- `last.pt`: Model weights from the final training epoch.
- `results.png`: Training and validation performance graphs.
- `confusion_matrix.png`: Classification and detection evaluation matrix.
- `results.csv`: Training metrics recorded across epochs.
- Prediction video: Video containing detected fire and smoke objects.

## 🚀 How to Run

1. Open the notebook in Kaggle.
2. Enable GPU acceleration.
3. Install the required libraries: `ultralytics` and `roboflow`.
4. Connect to Roboflow and download the dataset.
5. Configure the dataset paths in `data.yaml`.
6. Load the YOLOv8 Nano model and start training.
7. Load `best.pt` and run prediction on a test video.

## 👨‍💻 Author

**Youssef Yasser**

Engineering Student

---

*This project was developed as part of an AI and Computer Vision assignment.*
