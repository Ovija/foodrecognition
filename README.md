# Food Ingredient Detection & Segmentation

## Project Overview

This project was developed as part of a computer vision course focused on food analysis. The main goal is to compare the performance of two prominent deep learning models—YOLOv8m-Seg and Mask R-CNN—on the task of ingredient detection and segmentation from food images. This project explores both accuracy and efficiency, aiming to understand the practical trade-offs between these two models in real-world food-related applications.

## Dataset

For this project the FoodSeg103 dataset, a curated benchmark featuring 103 food categories with pixel-level annotations.
* **Name:** FoodSeg103
* **Images:** 7,118
* **Classes:** 103 food ingredient types
* **Split:**
    Training: 4,983 images
    Validation: 2,135 images
  
##### To load via Hugging Face:
from datasets import load_dataset
ds = load_dataset("EduardoPacheco/FoodSeg103")

## Components

#### YOLOv8m-Seg:

    Dataset split into training and validation (80/20).
    Data formatted into YOLO format: class IDs, bounding boxes, polygon points (normalized).
    Created a YAML configuration for class names and paths.
    Trained and evaluated using the YOLOv8m segmentation pipeline.

#### Mask R-CNN:

    Dataset split into training and dev sets.
    Built a custom FoodDataset class to load images, masks, and labels.
    Applied data augmentation (resizing, normalization).
    Trained and evaluated using a PyTorch implementation of Mask R-CNN.

## Evaluation Insights

**Performance Trade-offs:**
Mask R-CNN had slightly better precision, while YOLOv8m achieved higher recall and trained over twice as fast, making it more suited for real-time applications.

**Class Imbalance Issue:**
Both models struggled with minority classes, frequently missing rare ingredients. Majority classes (e.g., bread, potato) were learned more effectively due to their abundance.

⚠️ This was a missed opportunity: techniques like oversampling, class-weighted loss functions, or focal loss could have potentially improved detection across all classes.

## Future Work
* Implement balancing techniques to improve performance on underrepresented food classes.
* Explore hybrid models combining YOLO’s speed with Mask R-CNN’s precision.
* Extend to multi-modal analysis using recipes or nutritional information.
