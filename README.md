# Plant Leaves Super-Resolution using Deep Learning

## Overview

This project implements a **4× Single Image Super-Resolution (SISR)** model using **PyTorch** to reconstruct high-resolution crop leaf images from degraded low-resolution inputs.

The objective is to learn a mapping from **32×32 RGB images** to **128×128 RGB images**, preserving fine biological textures such as leaf veins and disease patterns.

This project was developed as part of a Kaggle competition on image super-resolution.

---

## Dataset Sample

<div align="center">

<img src="assets/Plant Leaf Super Resolution.png" width="900"/>

**Figure 1:** Example of a low-resolution (32×32) crop leaf image and its corresponding high-resolution (128×128) target image used during training.

</div>

## Problem Statement

Low-cost agricultural sensors and drones often capture low-resolution images due to hardware limitations and compression. These degraded images can reduce the accuracy of automated crop disease detection systems.

The goal of this project is to reconstruct high-quality images from low-resolution inputs using a deep learning model.

```
Low Resolution Image (32×32)
            │
            ▼
     Deep Learning Model
            │
            ▼
High Resolution Image (128×128)
```

---

## Dataset

The dataset contains paired low-resolution and high-resolution crop leaf images.

| Folder                   | Description                               |
| ------------------------ | ----------------------------------------- |
| `train_Low_Resolution/`  | 1,642 degraded 32×32 RGB images           |
| `train_High_Resolution/` | Corresponding 128×128 ground truth images |
| `test_Low_Resolution/`   | 495 images used for prediction            |

---

## Model Architecture

The model follows a residual learning approach for image super-resolution.

```
Input Image (3 × 32 × 32)
          │
          ▼
Initial Convolution
          │
          ▼
16 Residual Blocks
          │
          ▼
Feature Fusion
          │
          ▼
PixelShuffle ×2
          │
          ▼
PixelShuffle ×2
          │
          ▼
Final Convolution
          │
          ▼
Output Image (3 × 128 × 128)
```

### Architecture Components

* Initial Feature Extraction using Convolution
* Residual Learning Blocks
* Skip Connections
* PixelShuffle Upsampling
* Sigmoid Output Layer

---

## Technologies Used

* Python
* PyTorch
* NumPy
* Pandas
* Pillow (PIL)
* Matplotlib
* Kaggle Notebook

---

## Concepts Explored

During this project, I explored:

* Convolutional Neural Networks (CNNs)
* Image Super-Resolution
* Residual Learning
* Skip Connections
* PixelShuffle Upsampling
* PyTorch Dataset & DataLoader
* Custom Neural Network Design
* Image Tensor Processing
* Model Training & Inference

---

## Training

### Loss Function

* **L1 Loss (Mean Absolute Error)**

The competition evaluates submissions using **Mean Absolute Error (MAE)**, making L1 Loss an appropriate objective for training.

### Optimizer

* Adam Optimizer

---

## Results

The model successfully reconstructs higher-resolution images from low-resolution inputs while learning meaningful image representations through residual learning.

This project served as a practical introduction to image reconstruction and super-resolution using deep learning.

---

## Project Structure

```text
.
├── README.md
├── Super_Resolution.ipynb
├── requirements.txt
├── train_Low_Resolution/
├── train_High_Resolution/
├── test_Low_Resolution/
├── outputs/
└── submission.csv
```

---

## Future Improvements

* Implement Perceptual Loss using VGG19
* Explore SRGAN / ESRGAN architectures
* Hyperparameter tuning
* Data augmentation
* Model checkpointing
* Mixed Precision Training

---

##  Key Learnings

Through this project, I gained hands-on experience with:

* Building custom datasets in PyTorch
* Understanding image tensors and preprocessing
* Designing CNN-based architectures
* Residual Networks
* PixelShuffle for image upsampling
* Model training, inference, and evaluation
* End-to-end computer vision workflows

Beyond implementing the model, this project helped me understand the reasoning behind architectural choices and how different components contribute to reconstructing high-resolution images from degraded inputs.

---

##  Competition

Kaggle Competition: https://www.kaggle.com/competitions/plant-leaves-super-resolution-challenge

---

## ⭐ Acknowledgements

* Kaggle
* PyTorch
* The open-source Deep Learning community
