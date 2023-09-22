# | CNN | CV | Brain | Prediction

[Kaggle](https://www.kaggle.com/code/yannicksteph/cnn-cv-brain-prediction)

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Objectives](#objectives)
4. [References and Research Sources](#references-and-research-sources)
5. [Implementation](#implementation)
6. [Training Setup Explained](#training-setup-explained)

## 1. Introduction
The primary goal of this project is to facilitate the diagnosis and treatment of glioblastoma, a severe form of brain cancer. By leveraging radiogenomics and MRI scans, we aim to predict the genetic profile of the tumor, focusing on the presence of MGMT promoter methylation—a key prognostic factor. This project is part of a competition organized by RSNA and MICCAI, making it a timely and impactful endeavor.

## 2. Dataset Overview
Data is sourced from RSNA and MICCAI, two reputable organizations in the medical imaging community. For more details, visit [RSNA-MICCAI Brain Tumor Radiogenomic Classification](https://www.kaggle.com/competitions/rsna-miccai-brain-tumor-radiogenomic-classification/data?select=train_labels.csv).

## 3. Objectives
- To predict the MGMT promoter methylation status of glioblastoma tumors between values of 0 and 1.

## 4. References and Research Sources
- MGMT
    - [Is it Possible to Predict MGMT Promoter Methylation from Brain Tumor MRI Scans using Deep Learning Models](https://arxiv.org/abs/2201.06086)
    - [Automatic Prediction of MGMT Status in Glioblastoma via Deep Learning-Based MR Image Analysis](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7530505/)
    - [MRI-Based Deep-Learning Method for Determining Glioma MGMT Promoter Methylation Status](https://www.ajnr.org/content/42/5/845.abstract)
    - [Improving MGMT methylation status prediction of glioblastoma through optimizing radiomics features using genetic algorithm-based machine learning approach](https://www.nature.com/articles/s41598-022-17707-w)
- Data augmentation
    - [Data augmentation for deep learning based accelerated MRI reconstruction with limited data](https://arxiv.org/abs/2106.14947)
    - [Data augmentation: how to overcome small radiology datasets](https://www.quantib.com/blog/image-augmentation-how-to-overcome-small-radiology-datasets?hs_amp=true)

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

<img width="500" alt="model" src="https://github.com/YanSte/CNN-CV-Brain-Prediction/assets/6950194/31aee031-58fe-47d2-a1fc-30bd775b31f7">
