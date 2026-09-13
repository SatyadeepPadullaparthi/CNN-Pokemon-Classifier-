# CNN-Pokemon-Classifier-
A Structured Project Practicum of a CNN classifier for 10 Pokemons using a reduced Keras Dataset. We explore the effects of Image Denoising on CNN models.
# 🎮 Pokémon CAPTCHA Bypass: Computer Vision & Deep Learning Pipeline

An end-to-end deep learning and computer vision pipeline designed to systematically break an adversarial Pokémon image-matching CAPTCHA validation test. This project integrates custom computer vision preprocessing with optimized Convolutional Neural Network (CNN) classifiers and an image-reconstruction Convolutional Autoencoder.

> 🔒 **Academic Integrity & Compliance Notice:** In strict accordance with the **[HKUST Academic Honor Code](https://hkust.edu.hk)**, all raw executable source code files (`.py`, `.ipynb`) and computational model training assets are securely maintained in a **Private** repository to prevent unauthorized distribution and duplication. A comprehensive structural overview, engineering layout documentation, and model performance metrics are completely documented below. Codebase access verification can be explicitly granted to recruiters upon requested review.

> 📝 **Academic Program Context:** This project was developed as a structured programming practicum within the **HKUST COMP 2211 (Introduction Artificial Intelligence)** curriculum. While the baseline workspace framework, data distribution pipelines, and task guidelines were provided and heavily assisted by course instructors, all custom engineering implementation—including deep learning model architecture topologies, hyperparameter tuning, and training compilation configurations—was executed independently.

---

## 🚀 Key Project Achievements

### 1. CAPTCHA Classification Engine
* **Peak Generalization:** Achieved a validation accuracy of **~93%** across distinct target classes.
* **Loss Optimization:** Successfully minimized categorical cross-entropy loss down to **~0.2**.
* **Trainable Parameter Efficiency:** Configured an optimized network utilizing under **700,000 trainable parameters**, ensuring efficient training and eliminating overfitting under strict constraints (< 1,000,000 parameter bounds).

### 2. Convolutional Autoencoder Denoising Engine
* **Reconstruction Precision:** Minimized reconstruction loss to **0.0030** (Validation Loss: **0.0034**) and Mean Absolute Error (MAE) to **0.0308** over 100 epochs.
* **Signal Quality Recovery:** Achieved a **71.50% Peak Signal-to-Noise Ratio (PSNR) improvement**, dramatically boosting noisy, compressed verification inputs from a baseline **7.45 dB** to a clean **12.77 dB** relative to the original source images.

---

## 📊 Dataset Specifications
* **Core Source Material:** Utilized the open-source Pokémon images dataset hosted by **Keras**.
* **Target Downsampling:** To create specific hidden test layers and simulate strict verification criteria, the original dataset framework was explicitly isolated and downsampled into a specialized, compact subset containing exactly **10 distinct Pokémon classes**.

---

## 📊 Model Training Performance Metrics

### CNN Classifier Optimization (50 Epochs)
* **Accuracy Convergence:** Climbed smoothly to ~93%, establishing highly robust validation boundaries.
* **Loss Convergence:** Minimal variance or divergence between training and validation trends, settling tightly near 0.2.

### Autoencoder Reconstruction Optimization (100 Epochs)
* **Reconstruction Loss:** Converged smoothly to a final validation layer of 0.0034, showing highly stable matrix mapping.
* **Error Bounds (MAE):** Validated error bounds consistently plateaued near 0.0308, proving precise spatial recovery.

---

## 🛠️ Pipeline Architecture & Components

### 1. Data Augmentation Preprocessing Engine (`OpenCV`)
To actively resolve severe class imbalances and highly constrained data sample limits, custom pixel manipulation functions were engineered to perform targeted **Color Jittering** data augmentations:
* **Contrast Modulation:** Adjusted categorical image contrast limits via `cv2.convertScaleAbs`.
* **Linear Brightness Translation:** Applied systematic value modifications across multidimensional pixel matrices.
* **Saturation Calibration:** Transformed raw RGB tensors into the HSV color model via `cv2.cvtColor` to directly isolate and scale the **S (Saturation) channel**.

### 2. CNN Classifier Topology (`Keras`)
* **Feature Extraction Stack:** Implemented deep 2D Convolutional (`Conv2D`) layers integrated with custom spatial kernels.
* **Dimensionality Suppression:** Down-sampled spatial matrices using max-pooling filters (`MaxPooling2D`).
* **Regularization Overfitting Control:** Applied strategic `Dropout` configurations to decouple network weights.
* **Classification Output Head:** Routed a final `Flatten` layer into a 10-node `Dense` Softmax layer to evaluate categorical cross-entropy target distributions.

### 3. Convolutional Autoencoder Image Reconstruction (`Keras`)
Engineered a self-contained image-reconstruction network to clear high-frequency noise and adversarial compression artifacts from the CAPTCHA inputs before classification:
* **Encoder Module:** Compresses incoming noisy image vectors (`X_noisy`) down to highly concentrated lower-dimensional latent space representations using structured `Conv2D` and `MaxPooling2D` groupings.
* **Decoder Module:** Reconstructs the compressed spatial maps back up to target spatial resolutions by combining inverted `UpSampling2D` filters with specialized convolutional layers.
* **Target Mapping:** Supervised training using structural error minimization targets to cleanly translate corrupted inputs back into exact original clean visual matrix targets (`y`).

---

## 🧰 Technologies & Toolkits Used
* **Languages:** Python
* **Deep Learning Frameworks:** Keras
* **Computer Vision Libraries:** OpenCV (`cv2`)
* **Scientific Computing & Visualization:** NumPy, Pandas, Matplotlib
* **Development Environments:** Google Colab
