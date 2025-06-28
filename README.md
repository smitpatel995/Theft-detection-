# 🛒 Video Theft Detection for Shops

This project implements a **video-based theft detection system** to classify shoplifting behaviour in retail shops using computer vision and deep learning (PyTorch).

---

## 📌 Overview

Retail theft remains a significant challenge globally. This solution automates theft detection from surveillance videos, reducing manual monitoring efforts and enhancing security.

The notebook:

- Extracts frames from CCTV/shop videos.
- Preprocesses frames efficiently.
- Trains a CNN-based classifier to detect shoplifting behaviour.
- Evaluates performance with detailed metrics.

---

## 🚀 Features

✅ Frame extraction from videos  
✅ Data preprocessing and augmentation  
✅ PyTorch-based model for binary classification (shoplifter / non-shoplifter)  
✅ Evaluation metrics: accuracy, confusion matrix, classification report  
✅ GPU-compatible training pipeline  
✅ Modular functions for easy integration into production

---

## 🛠️ Installation

1. **Clone this repository**

```bash
git clone https://github.com/yourusername/video-theft-detection-for-shops.git
cd video-theft-detection-for-shops
```

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

---

## 📦 Requirements

Here is your `requirements.txt`:

```
numpy
pandas
matplotlib
torch
torchvision
scikit-learn
opencv-python
tqdm
Pillow
gdown
```

---

## 📂 Dataset Structure

Organise your dataset as follows:

```
data/Shop DataSet/
├── non shop lifters/
│   ├── video1.mp4
│   └── ...
└── shop lifters/
    ├── video2.mp4
    └── ...
```

Ensure class folder names match the `CLASS_NAMES` in the notebook: `["non shop lifters", "shop lifters"]`.

---

## 💻 Usage

Run the notebook:

```bash
jupyter notebook video-theft-detection-for-shops.ipynb
```

Key functions include:

- **extract_frames(video_path, num_frames=8, target_size=(160, 160))**  
  Extracts evenly spaced, resized frames from input videos.

- **Model Training**  
  Defines CNN architecture, loss function, optimizer, and training loop.

- **Evaluation**  
  Generates classification report and confusion matrix for performance analysis.

---

## 🔬 Results

The model is evaluated on:

- **Accuracy Score**
- **Confusion Matrix**
- **Classification Report** (Precision, Recall, F1-score)

> *Improve performance by tuning hyperparameters, augmenting data, or using advanced video action recognition models.*

---

## 🎯 Future Scope

✅ Real-time CCTV integration using OpenCV streams  
✅ Action recognition models (e.g. I3D, SlowFast) for temporal behaviour detection  
✅ Deployment as a REST API with Flask/FastAPI for edge devices  
✅ Streamlit dashboard for shop owners to monitor predictions

---

