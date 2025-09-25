# 🧠 Emotion Classification using Facial Expressions and EEG

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://python.org)
[![XGBoost](https://img.shields.io/badge/XGBoost-1.6%2B-orange.svg)](https://xgboost.readthedocs.io/)
[![Accuracy](https://img.shields.io/badge/Accuracy-93%25-brightgreen.svg)](#results)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **Advanced multimodal emotion recognition system combining EEG brainwave patterns with facial expression analysis to achieve 93% classification accuracy.**

## 🎯 Project Overview

This project tackles the challenging problem of emotion classification by fusing two powerful modalities:
- **EEG signals**: Capturing neural activity and brainwave patterns
- **Facial expressions**: Analyzing micro-expressions and facial features via Affectiva

**Key Achievement**: 93% classification accuracy using advanced feature engineering and XGBoost modeling.

## 🏗️ System Architecture

```mermaid
graph TD
    A[EEG Signals] --> D[Feature Engineering]
    B[Facial Expressions<br/>Affectiva] --> D
    C[TIVA Dataset] --> D
    
    D --> E[Variance Threshold]
    E --> F[Multicollinearity<br/>Removal]
    F --> G[XGBoost Feature<br/>Selection Top 45]
    
    G --> H[Class Imbalance<br/>Handling]
    H --> I[SMOTE Oversampling]
    H --> J[Class Weighting]
    
    I --> K[XGBoost Classifier]
    J --> K
    
    K --> L[Emotion Prediction<br/>93% Accuracy]
    
    %% Dark theme styling
    style A fill:#1e3a8a,stroke:#60a5fa,stroke-width:2px,color:#ffffff
    style B fill:#7c2d12,stroke:#fb923c,stroke-width:2px,color:#ffffff
    style C fill:#166534,stroke:#4ade80,stroke-width:2px,color:#ffffff
    style D fill:#581c87,stroke:#c084fc,stroke-width:2px,color:#ffffff
    style E fill:#0f172a,stroke:#94a3b8,stroke-width:2px,color:#ffffff
    style F fill:#0f172a,stroke:#94a3b8,stroke-width:2px,color:#ffffff
    style G fill:#0f172a,stroke:#94a3b8,stroke-width:2px,color:#ffffff
    style H fill:#7f1d1d,stroke:#f87171,stroke-width:2px,color:#ffffff
    style I fill:#0f172a,stroke:#94a3b8,stroke-width:2px,color:#ffffff
    style J fill:#0f172a,stroke:#94a3b8,stroke-width:2px,color:#ffffff
    style K fill:#134e4a,stroke:#2dd4bf,stroke-width:2px,color:#ffffff
    style L fill:#065f46,stroke:#10b981,stroke-width:3px,color:#ffffff
```

## 📊 Data Pipeline

```mermaid
flowchart LR
    A[Raw EEG Data] --> B[Time Window<br/>Segmentation<br/>1-5s]
    C[Facial Features<br/>TIVA.csv] --> B
    
    B --> D[Feature Alignment<br/>& Concatenation]
    D --> E[Data Cleaning &<br/>Preprocessing]
    E --> F[Feature Engineering<br/>Pipeline]
    
    F --> G[Model Training<br/>& Validation]
    
    %% Dark theme styling with orange accent
    style A fill:#ea580c,stroke:#fb923c,stroke-width:2px,color:#ffffff
    style B fill:#0f172a,stroke:#f97316,stroke-width:2px,color:#ffffff
    style C fill:#ea580c,stroke:#fb923c,stroke-width:2px,color:#ffffff
    style D fill:#0f172a,stroke:#f97316,stroke-width:2px,color:#ffffff
    style E fill:#0f172a,stroke:#f97316,stroke-width:2px,color:#ffffff
    style F fill:#0f172a,stroke:#f97316,stroke-width:2px,color:#ffffff
    style G fill:#c2410c,stroke:#fdba74,stroke-width:3px,color:#ffffff
```

## 🚀 Key Features

### 🔧 Advanced Feature Engineering
- **Variance Threshold Filtering**: Removes low-variance features
- **Multicollinearity Detection**: Eliminates redundant features
- **XGBoost Feature Importance**: Selects top 45 most predictive features
- **Time-Window Alignment**: Synchronized EEG and facial expression data

### ⚖️ Class Imbalance Solutions
- **SMOTE Oversampling**: Generates synthetic samples for minority classes
- **Class Weighting**: Adjusts loss function for balanced learning
- **Strategic Undersampling**: Manages dominant emotion classes

### 🎯 Model Performance
- **Algorithm**: XGBoost Classifier
- **Accuracy**: 93%
- **Multimodal Fusion**: EEG + Facial Expression features

## 📈 Results

| Metric | Score |
|--------|-------|
| **Accuracy** | **93%** |
| **Model** | XGBoost Classifier |
| **Features** | 45 (optimized) |
| **Data Modalities** | EEG + Facial Expressions |



## 📁 Project Structure

```
emotion-classification/
├── data/
│   ├── EEG.csv              # EEG brainwave features
│   └── TIVA.csv             # Facial expression data
├──  notebooks/
│   ├── 01_preprocessing.ipynb       # Data cleaning & preprocessing
│   ├── 02_feature_engineering.ipynb  # Feature importance & selection
│   └──  03_modeling_baseline.ipynb              # XGBoost classifier
└── README.md 
```

## 🔍 Methodology

### 1. Data Preparation
- **Time-window segmentation** (1-5 second windows)
- **Feature alignment** between EEG and facial expression data
- **Label assignment** based on dominant emotion per window

### 2. Feature Engineering Pipeline
- Variance threshold filtering
- Multicollinearity removal
- XGBoost-based feature importance ranking
- Top 45 feature selection

### 3. Class Imbalance Handling
- SMOTE oversampling for minority emotions
- Class weight adjustment in loss function
- Strategic undersampling of dominant classes

### 4. Model Training
- XGBoost classifier with optimized hyperparameters
- Cross-validation for robust performance estimation
- Feature importance analysis for interpretability

## 📊 Emotion Classes

The system classifies the following emotional states:
- **Engaged** 🎯
- **Confused** 🤔  
- **Neutral** 😐
-
