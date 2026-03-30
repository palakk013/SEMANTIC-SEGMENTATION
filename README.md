# Offroad Semantic Segmentation using DINOv2
Duality AI Hackathon Submission

---

## Project Overview

This project implements a semantic segmentation model for offroad environments using the Duality AI Falcon synthetic dataset. The objective is to classify each pixel in an image into one of the terrain classes such as trees, bushes, grass, rocks, landscape, and sky.

Semantic segmentation is an essential computer vision task used in autonomous navigation, robotics, and offroad vehicle perception.

This implementation uses a pretrained DINOv2 Vision Transformer backbone and a ConvNeXt-style segmentation head.

---

## Model Architecture

### Backbone
- Model: DINOv2 Vision Transformer (ViT-S/14)
- Purpose: Feature extraction
- Pretrained on large-scale image datasets
- Frozen during training to leverage pretrained knowledge

### Segmentation Head
- ConvNeXt-style convolutional architecture
- Takes backbone features as input
- Outputs pixel-wise class predictions

### Number of Classes

The model predicts 10 classes:

0: Background  
1: Trees  
2: Lush Bushes  
3: Dry Grass  
4: Dry Bushes  
5: Ground Clutter  
6: Logs  
7: Rocks  
8: Landscape  
9: Sky  

---

## Dataset

Dataset provided by Duality AI Falcon simulation platform.

Structure:

Offroad_Segmentation_Training_Dataset/

train/  
&nbsp;&nbsp;&nbsp;&nbsp;Color_Images/  
&nbsp;&nbsp;&nbsp;&nbsp;Segmentation/  

val/  
&nbsp;&nbsp;&nbsp;&nbsp;Color_Images/  
&nbsp;&nbsp;&nbsp;&nbsp;Segmentation/  

Offroad_Segmentation_testImages/

Color_Images/  
Segmentation/  

Training images: 2857  
Validation images: 317  

Each image has a corresponding segmentation mask.

---

## Installation

Install dependencies using pip:

```bash
pip install torch torchvision opencv-python matplotlib tqdm pillow timm numpy
```
## Training Instructions
To train the model, run:

```bash
python train_segmentation.py
```

This will:

Load dataset

Load pretrained DINOv2 backbone

Train segmentation head

Compute metrics

Save trained model

Generate training graphs

Output files generated:
```
segmentation_head.pth
train_stats/
```


train_stats folder contains:

1. training_curves.png
2. iou_curves.png
3. dice_curves.png
4. evaluation_metrics.txt

## Testing Instructions

To run inference and generate predictions:

```bash
python test_segmentation.py
```


This will generate:

```
predictions/
    masks/
    masks_color/
    comparisons/
```

## Evaluation Metrics

The following evaluation metrics are used:

1. Mean IoU (Intersection over Union)
2. Dice Score
3. Pixel Accuracy

Evaluation results are saved in:

```bash
train_stats/evaluation_metrics.txt
```

## Results

The model successfully learns to segment offroad terrain using synthetic data.

Performance improves steadily during training as shown in:

1. IoU curves
2. Loss curves
3. Dice score curves

Visual predictions demonstrate correct segmentation of terrain classes.

## Repository Structure

```
train_segmentation.py
test_segmentation.py
segmentation_head.pth
README.md
report.pdf
requirements.txt
train_stats/
predictions/
```

## Hardware Used

Local training:
CPU training environment

Cloud training:
Google Colab GPU (NVIDIA Tesla T4)

## Challenges Faced

1. Limited GPU availability locally
2. Long training time on CPU
3. Class imbalance in dataset

## Solutions Applied

1. Used pretrained DINOv2 backbone
2. Used ConvNeXt segmentation head
3. Used Google Colab GPU for faster training
4.Optimized hyperparameters

## Future Improvements

Possible improvements include:

1.Training larger backbone models
2.Applying data augmentation
3.Increasing number of training epochs
4.Using advanced segmentation architectures

## Conclusion

This project successfully demonstrates semantic segmentation of offroad environments using pretrained transformer-based feature extraction and convolutional segmentation head.

The model achieves strong performance and demonstrates the effectiveness of synthetic training data for real-world autonomous navigation tasks.
