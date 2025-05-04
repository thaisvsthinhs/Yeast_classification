# Yeast Cell Classification

This repository implements an **image classification pipeline** to detect normal vs. abnormal yeast cells from microscopy data using a ResNet-32 Convolutional Neural Network.

## Project Overview

- **Objective:** Build and train a CNN model to classify yeast cell images (32×32 grayscale) into normal and abnormal categories.  
- **Dataset:** Microscopy images annotated via Excel files. The dataset is split into training, validation, and test sets.

## Pipeline Components
1. **Data Preparation**  
   - Parse annotation Excel files and filter malformed entries.  
   - Split data into train/dev/test subsets.  
   - Compute per-channel mean and standard deviation for normalization.

2. **Data Augmentation**  
   - Applied random flips, rotations, color jitter, affine transforms.  
   - Employed MixUp to improve model generalization on limited biological data.

3. **Model Architecture**  
   - Custom **ResNet-32** tailored for 32×32 input images.  
   - Integrates batch normalization, dropout, and bi-directional residual connections.

4. **Loss Function & Optimization**  
   - Custom **Focal Loss** with class-weighting to address dataset imbalance.  
   - Trained using **AdamW** optimizer with **ReduceLROnPlateau** scheduler and **early stopping**.

5. **Evaluation & Analysis**  
   - Reported test accuracy (85.54%) and monitored validation loss.  
   - Visualized training/validation curves.  
   - Analyzed misclassified samples with plotting utilities.

