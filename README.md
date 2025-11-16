# DIT5411 Chinese Character Recognition

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.12%2B-orange)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

A deep learning system for recognizing 13,065 Chinese handwritten characters using convolutional neural networks (CNNs). This project achieves over 80% accuracy in classifying thousands of distinct Chinese characters.

## 🎯 Project Overview

This project implements a comprehensive solution for Chinese handwritten character recognition, addressing the challenge of classifying 13,065 different characters using deep learning techniques. The system employs multiple CNN architectures with advanced regularization methods to prevent overfitting and improve generalization.

## 📊 Key Results

| Model | Architecture | Test Accuracy |
|-------|--------------|---------------|
| Model 1 | Regularized CNN | 82.89% |
| Model 2 | Simplified CNN | 75.63% |
| Model 3 | Lightweight CNN | 69.84% |

**Best Model Performance**: 82.89% accuracy on test set

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- TensorFlow 2.12+
- See `requirements.txt` for full dependencies
- 

# 🏗️ Model Architectures
## Model 1: Regularized CNN (Best Performing)
3 convolutional layers with batch normalization

Strong regularization: Dropout (0.2-0.4) + Batch Normalization

Global Average Pooling for better generalization

Direct connection to 2,000-class output layer

Total parameters: ~1.78 million

## Model 2: Simplified CNN
Streamlined architecture with He normal initialization

3 convolutional layers (48→96→192 filters)

Moderate dropout (0.3-0.5)

Global Average Pooling before classification

Total parameters: ~2.73 million

## Model 3: Lightweight CNN
Minimal architecture with L2 regularization

3 convolutional layers (24→48→96 filters)

Additional dense layer (128 units) before output

Aggressive dropout (0.3-0.5)

Total parameters: ~1.75 million


# 📊 Data Augmentation Method
The project uses TensorFlow's ImageDataGenerator for data augmentation to address limited training samples:
```bash
datagen = tf.keras.preprocessing.image.ImageDataGenerator(
    rotation_range=10,           # ±10 degree rotation
    width_shift_range=0.1,       # ±10% horizontal shift
    height_shift_range=0.1,      # ±10% vertical shift
    shear_range=0.1,             # ±10% shear transformation
    zoom_range=0.1,              # ±10% zoom
    fill_mode='constant',        # Fill new pixels with constant value
    cval=0                       # Fill value = 0 (black)
)
`````
# 🔍 Reference

https://github.com/AI-FREE-Team/Traditional-Chinese-Handwriting-Dataset

https://github.com/kimanalytics/Handwritten-Digit-Recognition-using-Keras-and-TensorFlow
