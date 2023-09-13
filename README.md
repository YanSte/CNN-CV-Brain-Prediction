# | CNN | CV | Brain | Classification

[Kaggle](https://www.kaggle.com/code/yannicksteph/cnn-cv-brain-classification)

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Research Efforts](#research-efforts)
4. [Objectives](#objectives)
5. [References and Research Sources](#references-and-research-sources)
6. [Implementation](#implementation)
7. [Training Setup Explained](#training-setup-explained)

## 1. Introduction
The primary goal of this project is to facilitate the diagnosis and treatment of glioblastoma, a severe form of brain cancer. By leveraging radiogenomics and MRI scans, we aim to predict the genetic profile of the tumor, focusing on the presence of MGMT promoter methylation—a key prognostic factor. This project is part of a competition organized by RSNA and MICCAI, making it a timely and impactful endeavor.

## 2. Dataset Overview
Data is sourced from RSNA and MICCAI, two reputable organizations in the medical imaging community. For more details, visit [RSNA-MICCAI Brain Tumor Radiogenomic Classification](https://www.kaggle.com/competitions/rsna-miccai-brain-tumor-radiogenomic-classification/data?select=train_labels.csv).

## 3. Objectives
- To predict the MGMT promoter methylation status of glioblastoma tumors between values of 0 and 1.

## 4. References and Research Sources
- [Various papers and articles](#)

## 6. Implementation
The implementation is structured as follows:
- Training Setup
- Data Retrieval
- Data Preparation
- Model Creation
- Model Training
- Model Evaluation

## 6. Training Setup Explained
### Cross-Validation
- **Method**: Stratified K-Fold
- **Configuration**: 5 Folds; 1st fold used for validation

### Processing
- **Dimensions**: 128x128 pixels, grayscale
- **Sequence**: 32 sequential images
- **Scale**: 85% of original image size

### Augmentation
- Crop, Rotate, Translate, Blur, Contrast, and Brightness

### Train
- **Batch Size**: 8
- **Epochs**: 32
- **Optimizer**: SGD with learning rate 0.001
- **Loss Function**: Binary Cross-Entropy
- **Metrics**: AUC

### Model Architecture
- **Model**: DeepScanModel (3D CNN)
