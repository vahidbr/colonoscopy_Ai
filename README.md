# colonoscopy_Ai
Deep learning framework for colonoscopy image classification
# colonoscopy_Ai
Deep learning framework for colonoscopy image classification

# CRC Polyp Classification using Hybrid Feature Fusion and ResMLP

## 🧠 Methodology

The proposed method for colorectal polyp image classification consists of the following pipeline:

Input Image  
   ↓  
Preprocessing (resize, normalization)  
   ↓  
Feature Extraction:
   - Bag of Visual Words (BoVW)
   -  ↓
   Dimensionality Reduction:
   - Autoencoder (AE)
   -   ↓
   - Triple Embedding (TE)  
     ↓
- Handcrafted Features (HC)

   ↓  
Feature Fusion  
   ↓  
Classification:
   - Residual Multi-Layer Perceptron (ResMLP)  
   ↓  
Final Prediction:
   - Adenoma  
   - Hyperplastic  
   - Unknown  

---

## 🧠 Overview
This project proposes a hybrid machine learning framework for colorectal polyp image classification using colonoscopy datasets.

The model combines:
- Bag of Visual Words (BoVW)
- Autoencoder (AE)
- Triple Embedding (TE)
- Handcrafted Features (HC)
- Residual Multi-Layer Perceptron (ResMLP)

for classifying images into three categories:
- Adenoma
- Hyperplastic
- Unknown

---

## 📂 Datasets

This study uses a combination of publicly available and curated datasets:

### 1. Kvasir
Source: https://datasets.simula.no/kvasir/

- Open-access gastrointestinal endoscopy dataset
- Originally designed for polyp segmentation and detection
- Contains labeled endoscopic images

In the original dataset, annotations are provided as binary labels (polyp / non-polyp). In this study, these labels were used as intermediate annotations for constructing a unified multi-class classification framework.

Specifically:

- Polyp images were mapped to Adenoma or Hyperplastic when reliable annotation or metadata was available.
- Non-polyp images were assigned to the Unknown class when no clinically reliable label could be determined.

---

### 2. PolypsSet (Curated Dataset)

PolypsSet is a curated dataset constructed in this study by combining and filtering images from publicly available sources.

Images were selected based on:
- Annotation availability  
- Image quality  
- Removal of duplicates  
- Clinical relevance  

This dataset was specifically built for the proposed 3-class classification task.

Reference:
"Replication Data for: Colonoscopy Polyp Detection and Classification: Dataset Creation and Comparative Evaluations"

---

## 📊 Class Definitions

The dataset is organized into three classes for the final classification task:

- Adenoma
- Hyperplastic
- Unknown

This unified label space is used across all datasets to ensure consistency in training and evaluation.

---

## ⚙️ Data Processing Pipeline

1. Frame/image extraction from datasets  
2. Image resizing and normalization  
3. Dataset cleaning (removal of low-quality and duplicate images)  
4. . Label mapping: conversion to three classes in PolypsSet and two classes in Kvasir dataset 
5. Train/test split at image level (ensuring no overlap)  
