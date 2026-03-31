# Adversarial Attacks on CIFAR-10 (FGSM, BIM, PGD)

## 📌 About the Project
In this project, I explored how vulnerable deep learning models can be to small, almost invisible changes in input images.

I trained a CNN model on the CIFAR-10 dataset and then applied three popular adversarial attacks:
- FGSM
- BIM
- PGD

The goal was to see how these attacks affect model performance and understand model robustness.

---

## 📂 Dataset
- CIFAR-10 dataset (60,000 images)
- 10 classes: airplane, car, bird, cat, deer, dog, frog, horse, ship, truck
- Image size: 32×32 (RGB)

---

## ⚙️ Preprocessing
- Normalized images to [0,1]
- One-hot encoded labels
- Used standard train-test split

---

## 🧠 CNN Model
I built a CNN with 3 convolution layers using different kernel sizes:

- Conv Layer (3×3) → MaxPooling  
- Conv Layer (5×5) → MaxPooling  
- Conv Layer (7×7) → MaxPooling  
- Flatten → Dense → Dropout → Output  

This model was trained for 50 epochs with early stopping and model checkpointing.

---

## ⏱️ Training
- Optimizer: Adam  
- Loss: Categorical Crossentropy  
- Batch size: 64  
- Validation split: 20%  
- Training time recorded  

---

## 📊 Evaluation (Clean Data)
Before applying attacks, I evaluated the model on normal test data using:
- Accuracy
- Loss
- Precision, Recall, F1-score
- Confusion Matrix

---

## ⚠️ Adversarial Attacks Implemented

### 🔹 FGSM (Fast Gradient Sign Method)
- One-step attack
- Adds small noise using gradient sign

Tested with multiple epsilon values:
- 0.01, 0.03, 0.05, 0.1

---

### 🔹 BIM (Basic Iterative Method)
- Iterative version of FGSM
- Applies small changes multiple times

Parameters:
- ε = 0.03  
- α = 0.005  
- Iterations = 10  

---

### 🔹 PGD (Projected Gradient Descent)
- Stronger version of BIM
- Includes random initialization

Parameters:
- ε = 0.03  
- α = 0.005  
- Iterations = 20  

---

## 📈 Results & Analysis

I evaluated the model under:
- Clean data  
- FGSM attacks  
- BIM attack  
- PGD attack  

For each case, I measured:
- Accuracy
- Loss
- Precision
- Recall
- F1-score
- Confusion Matrix

---

## 🖼️ Visualization
I visualized:
- Original image  
- Adversarial image  
- Perturbation (difference)  

Also displayed:
- True label  
- Prediction before attack  
- Prediction after attack  

This clearly shows how small changes can fool the model.

---

## 🔍 Key Observations
- Even tiny perturbations can reduce accuracy significantly  
- FGSM is fast but less powerful  
- BIM performs better than FGSM  
- PGD is the strongest attack among all  

---

## ⚠️ Challenges Faced
- Generating adversarial examples efficiently  
- Maintaining image quality after perturbation  
- Longer computation time for iterative attacks  

---

## 🛠️ Tools & Libraries
- Python  
- TensorFlow / Keras  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  
