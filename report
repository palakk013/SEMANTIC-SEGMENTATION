# Offroad Semantic Segmentation Hackathon Report

## 1. Introduction

This project focuses on semantic segmentation of offroad environments using synthetic data provided by Duality AI Falcon platform.

Semantic segmentation assigns a class label to each pixel in an image, which is essential for autonomous navigation systems.

---

## 2. Objective

The objective is to train a deep learning model capable of segmenting terrain classes such as:

- Trees
- Bushes
- Grass
- Rocks
- Landscape
- Sky

---

## 3. Dataset

Dataset provided by Duality AI Falcon simulation platform.

Training images: 2857  
Validation images: 317  

Each image has a corresponding segmentation mask.

---

## 4. Model Architecture

Backbone:
- DINOv2 Vision Transformer
- Pretrained feature extractor

Segmentation Head:
- ConvNeXt-style convolutional layers
- Outputs pixel-wise predictions

Number of classes: 10

---

## 5. Training Setup

Hardware:
- Local CPU training
- Google Colab GPU training

Hyperparameters:

Batch size: 4  
Epochs: 10  
Learning rate: 0.0001  

Loss function:
CrossEntropyLoss

Optimizer:
SGD

---

## 6. Evaluation Metrics

The following metrics were used:

- Mean IoU
- Dice Score
- Pixel Accuracy

Evaluation results are saved in:

train_stats/evaluation_metrics.txt

---

## 7. Results

The model successfully learned terrain segmentation.

Performance improved steadily during training.

Visual predictions show correct classification of terrain classes.

---

## 8. Challenges

Challenges faced:

- Limited GPU resources locally
- Long training time
- Dataset complexity

---

## 9. Solutions

Solutions applied:

- Used pretrained DINOv2 backbone
- Used Google Colab GPU
- Optimized hyperparameters

---

## 10. Conclusion

The model successfully performs semantic segmentation and generalizes well on validation dataset.

Future improvements include:

- Training longer
- Using larger backbone
- Applying data augmentation
