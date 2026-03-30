# CIFAR-10 Image Classification using ANN vs CNN

## 📌 Project Overview
This project implements and compares two deep learning models:

- Artificial Neural Network (ANN / MLP)
- Convolutional Neural Network (CNN)

for image classification on the CIFAR-10 dataset.

The goal is to understand how CNNs outperform ANNs in handling image data due to their ability to capture spatial features.

---

## 📂 Dataset
- CIFAR-10 dataset (10 classes, 32×32 RGB images)
- Loaded using TensorFlow/Keras

### Preprocessing Steps:
- Converted images to float32
- Normalized pixel values to range [0,1]
- One-hot encoded labels

---

## 🧠 Models Implemented

### 🔹 ANN Model (Baseline)
- Input: Flattened image (32×32×3 → 3072)
- Architecture:
  - Dense (512) + ReLU
  - Dropout (0.3)
  - Dense (256) + ReLU
  - Dropout
  - Dense (128) + ReLU
  - Output Layer (Softmax)

- Limitation:
  - Cannot capture spatial relationships in images

---

### 🔹 CNN Model
- Architecture:
  - Conv2D (32 filters, 3×3 kernel) + ReLU
  - MaxPooling
  - Conv2D (64 filters, 5×5 kernel) + ReLU
  - MaxPooling
  - Conv2D (128 filters, 7×7 kernel) + ReLU
  - Flatten
  - Dense Layer
  - Output Layer (Softmax)

- Advantage:
  - Learns spatial features like edges, textures, shapes

---

## ⚙️ Training Details
- Epochs: 20
- Batch Size: 128
- Validation Split: 20%
- Optimizer: Adam
- Loss Function: Categorical Crossentropy

Training time is recorded for both models.

---

## 📊 Evaluation Metrics
- Test Accuracy
- Test Loss
- Classification Report:
  - Precision
  - Recall
  - F1-score
- Confusion Matrix
- Misclassified Samples Visualization

---

## 📉 Visualizations
- Training vs Validation Accuracy
- Training vs Validation Loss
- Confusion Matrix
- Misclassified Images

---

## 🔍 Key Observations
- CNN significantly outperforms ANN in accuracy
- ANN fails to understand image structure
- CNN captures spatial hierarchy (edges → shapes → objects)
- CNN shows better generalization on test data

---

## ⚠️ Limitations
- ANN is not suitable for image data
- CNN requires more computation time
- Model performance can improve with more epochs and tuning

---

## 🚀 Future Improvements
- Increase epochs for better learning
- Apply Data Augmentation
- Use Transfer Learning (ResNet, VGG)
- Hyperparameter tuning

---

## 🛠️ Tech Stack
- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Scikit-learn
- Pandas
