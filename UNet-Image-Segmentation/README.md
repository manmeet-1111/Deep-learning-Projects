# U-Net Image Segmentation using Oxford-IIIT Pet Dataset

## Objective
The objective of this project is to implement the U-Net architecture for image segmentation and understand how deep learning models perform pixel-level classification.

This project includes:
- Forward pass of U-Net on a single image
- Training U-Net on Oxford-IIIT Pet dataset
- Evaluation using Accuracy and IoU metric
- Visualization of segmentation results

---

## 📂 Dataset

### 1. Single Image Demo
- A sample image is passed through the U-Net model
- Used to visualize predicted segmentation mask

---

### 2. Oxford-IIIT Pet Dataset
- Loaded using TensorFlow Datasets (tfds)
- Contains:
  - RGB images of pets
  - Pixel-level segmentation masks

---

## 🧠 U-Net Architecture

The implemented U-Net consists of:

### Encoder (Downsampling)
- Conv Block (64 filters)
- MaxPooling
- Conv Block (128 filters)
- MaxPooling

### Bottleneck
- Conv Block (256 filters)

### Decoder (Upsampling)
- UpSampling + Skip Connection with encoder
- Conv Block (128 filters)
- UpSampling + Skip Connection
- Conv Block (64 filters)

### Output Layer
- 1×1 Convolution
- Sigmoid activation (binary segmentation)

---

## ⚙️ Preprocessing
- Images resized to 128 × 128
- Pixel values normalized to [0,1]
- Masks converted to binary:
  - Pet = 1
  - Background = 0

---

## ⚙️ Training Details
- Optimizer: Adam
- Loss Function: Binary Crossentropy
- Metrics:
  - Accuracy
  - IoU (custom implemented)
- Batch Size: 16
- Epochs: 5

---

## 📊 Evaluation Metrics

###  Accuracy
- Measures pixel-wise correctness

###  IoU (Intersection over Union)
- Measures overlap between predicted mask and ground truth

---

## 📈 Results

###  Training Curves
- Loss Curve (Training vs Validation)
- Accuracy Curve (Training vs Validation)

---

###  Segmentation Output
For test images:
- Original Image
- Ground Truth Mask
- Predicted Mask

---

## 🔍 Key Observations
- U-Net effectively captures spatial information using skip connections
- IoU gives better insight than accuracy for segmentation tasks
- Model performs reasonably well even with few epochs

---



## Future Improvements
- Increase number of epochs
- Apply data augmentation (flip, rotation)
- Use Dice Loss instead of BCE
- Add Batch Normalization / Dropout
- Use pretrained encoder (ResNet, VGG)

---

## 🛠️ Tech Stack
- Python
- TensorFlow / Keras
- TensorFlow Datasets (TFDS)
- NumPy
- Matplotlib

---
