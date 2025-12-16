# 🐍 Sss or Safe? Snake Venom Classification

[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0+-FF6F00?logo=tensorflow)](https://www.tensorflow.org/)
[![Gradio](https://img.shields.io/badge/Gradio-UI-blue?logo=gradio)](https://gradio.app/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

> **A Deep Learning project to classify snake species as Venomous or Non-Venomous using Transfer Learning.**

## 📘 Project Overview
This project applies Computer Vision to wildlife safety. Using a dataset of Philippine and global snake species, we trained a Convolutional Neural Network (CNN) to distinguish between **Venomous** and **Non-Venomous** snakes.

The final model utilizes **MobileNetV2** architecture, optimized for mobile efficiency and high accuracy.

**Try the Live Demo:** [Link to your Hugging Face Space](https://huggingface.co/spaces/deesim/venomous-or-nonvenomous-snake-classifier)

## 🎯 Objectives
* Prepare and merge diverse snake image datasets (iNaturalist sources).
* Compare architectures: Vanilla CNN vs. EfficientNet vs. MobileNetV2.
* Deploy a user-friendly web interface for real-time classification.

## 🧠 Model Performance
After experimenting with Vanilla CNNs and Ensembles, the **MobileNetV2** model provided the best balance of speed and accuracy.

| Metric | Score | Interpretation |
| :--- | :--- | :--- |
| **Accuracy** | **77.15%** | Overall correctness on unseen data. |
| **ROC-AUC** | **0.8505** | Excellent distinction between classes. |
| **Recall** | **74.52%** | Sensitivity: effectively catches dangerous snakes. |
| **Precision** | **66.51%** | Minimizes false alarms. |

*Generalization Check: The gap between Training Accuracy (79.6%) and Test Accuracy (77.1%) is <2.5%, indicating no significant overfitting.*

## ⚙️ Methodology
1.  **Data Preprocessing:** Images resized to 224x224, normalized to [-1, 1], and augmented with rotation, zoom, and flips.
2.  **Architecture:** * Base: MobileNetV2 (Pre-trained on ImageNet, Frozen).
    * Head: GlobalAveragePooling -> Dense(256) -> Dropout(0.4) -> Dense(1, Sigmoid).
3.  **Training:** Trained for 20 epochs with Early Stopping and Class Weights (1:1.74) to handle dataset imbalance.
4.  **Threshold Tuning:** Optimal decision threshold tuned to **0.50** (or your specific saved npy value) to maximize F1-Score.

## 🚀 Installation & Usage

### 1. Clone the repo
```bash
git clone [https://github.com/YOUR_USERNAME/Snake-Venom-Detection.git](https://github.com/YOUR_USERNAME/Snake-Venom-Detection.git)
cd Snake-Venom-Detection
```
### 2. Install dependencies
```bash
pip install -r requirements.txt
```
### 3. Run the App
```bash
python app.py
```

👩‍💻 Authors
Dave Shanna Gigawin - Lead ML Engineer
John Paul Ullegue - Data Specialist

Institution: University of Southeastern Philippines – College of Information and Computing
