# Insect Classifier using CNN

A Convolutional Neural Network implementation for classifying insect images into 5 categories, developed as a project for the Neural Networks course at University of Belgrade, School of Electrical Engineering.

## Overview

This project implements a CNN model to classify images of insects into the following categories:
- Butterfly
- Dragonfly
- Grasshopper
- Ladybug
- Mosquito

The model achieves approximately **65% accuracy** on the validation set.

## Dataset

The project uses the [Insects Recognition](https://www.kaggle.com/datasets/vencerlanz09/insects-recognition-dataset) dataset from Kaggle.

**Setup:** Download the dataset and place it in a folder named `Podaci` in the project root directory.

## Model Architecture

- **Input:** 64x64 RGB images
- **Data Augmentation:** Random flip, rotation (25%), and zoom (10%)
- **Convolutional Layers:**
  - Conv2D (16 filters, 3x3) → MaxPooling2D
  - Conv2D (32 filters, 3x3) → MaxPooling2D
  - Conv2D (64 filters, 3x3)
- **Regularization:** Dropout (0.2)
- **Fully Connected:** Dense (128 units, ReLU) → Dense (5 units, Softmax)
- **Total Parameters:** ~2.1M trainable parameters

## Training Configuration

- **Optimizer:** Adam (learning rate = 0.001)
- **Loss Function:** Sparse Categorical Crossentropy
- **Epochs:** 50
- **Batch Size:** 64
- **Train/Validation Split:** 80/20

## Requirements

```
tensorflow
keras
numpy
matplotlib
seaborn
scikit-learn
```

## Usage

1. Install the required dependencies
2. Download and extract the dataset to the `Podaci` folder
3. Run the training script:

```bash
python conv.py
```

The script will:
- Display dataset distribution
- Show sample images from each class
- Train the CNN model
- Generate accuracy and loss plots
- Display confusion matrix
- Show classification report with precision, recall, and F1-scores
- Visualize sample predictions

## Results

The model demonstrates good performance across all classes, with particularly strong results for Ladybug and Mosquito (87% precision). The confusion matrix reveals that some visually similar insects (e.g., Dragonfly and Mosquito) are occasionally misclassified due to wing structure similarities.

Detailed results and analysis are available in `CNN.pdf`.
