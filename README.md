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
  
### To load via Hugging Face:
from datasets import load_dataset
ds = load_dataset("EduardoPacheco/FoodSeg103")
