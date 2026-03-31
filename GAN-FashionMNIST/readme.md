# GAN on Fashion-MNIST 👕👟

## 📌 About the Project
In this project, I implemented a Generative Adversarial Network (GAN) to generate synthetic images from the Fashion-MNIST dataset.

The idea behind GANs is simple but powerful — one network tries to create fake images (Generator), while another tries to detect whether they are real or fake (Discriminator). Over time, both models improve and the generated images start looking more realistic.

---

## 📂 Dataset
I used the Fashion-MNIST dataset, which contains 70,000 grayscale images of clothing items like:
- T-shirts
- Shoes
- Bags
- Dresses

Each image is 28×28 pixels.

---

## ⚙️ Data Preprocessing
Before training:
- Images were reshaped to (28, 28, 1)
- Converted to float format
- Normalized to the range [-1, 1] (important for GAN training)

---

## 🧠 Model Architecture

### 🔹 Generator
The generator takes random noise as input and tries to create images.

- Dense layer → reshaped into feature maps
- Conv2DTranspose layers to upscale the image
- Batch Normalization + LeakyReLU for stability
- Final output uses **tanh activation**

---

### 🔹 Discriminator
The discriminator tries to classify images as real or fake.

- Convolutional layers extract features
- Dropout helps prevent overfitting
- Final Dense layer outputs real/fake score

---

## 🔄 Training Process
Training a GAN is different from normal models:

- Generator creates fake images
- Discriminator evaluates them
- Both models are trained together in a competitive way

I trained the model for **100 epochs** and tracked:
- Generator loss
- Discriminator loss

---

## 📈 Results
- At the beginning, generated images look like noise
- Gradually, shapes and patterns start appearing
- After several epochs, the generator starts producing recognizable fashion items

I also visualized generated images every 10 epochs to observe progress.

---

## 📉 Training Visualization
- Generator Loss vs Epoch
- Discriminator Loss vs Epoch

These graphs help understand how stable the GAN training is.
---

## ⚠️ Challenges Faced
- Training instability
- Sometimes generator produces similar images (mode collapse)
- Requires tuning learning rate and architecture

---

## 🚀 Future Improvements
- Try DCGAN (deeper architecture)
- Implement Conditional GAN (generate specific classes)
- Train for more epochs
- Use evaluation metrics like FID score

---

## 🛠️ Tools & Libraries
- Python
- TensorFlow / Keras
- NumPy
- Matplotlib

---
