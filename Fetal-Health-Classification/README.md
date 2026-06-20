# Fetal Health Classification

## Overview

Classification of fetal health conditions into **Normal**, **Suspect**, and **Pathological** categories using Cardiotocogram (CTG) measurements and supervised machine learning techniques.

Cardiotocography is a non-invasive prenatal monitoring technique used to assess fetal well-being by measuring fetal heart rate patterns and uterine contractions. Accurate classification of fetal health can assist healthcare professionals in identifying potential risks and taking timely medical interventions.

## Dataset

The dataset contains **2,126 CTG records** with **21 clinical features** extracted from Cardiotocogram examinations.

### Target Classes

| Class | Description  |
| ----- | ------------ |
| 1     | Normal       |
| 2     | Suspect      |
| 3     | Pathological |

### Dataset Characteristics

* Total Samples: 2,126
* Features: 21
* Missing Values: None
* Problem Type: Multiclass Classification

## Machine Learning Models

The following supervised classification algorithms were implemented and evaluated:

### K-Nearest Neighbors (KNN)

A distance-based classification algorithm that predicts the class of a sample based on the majority class of its nearest neighbors.

### Support Vector Machine (SVM)

A powerful classification algorithm that finds the optimal decision boundary between classes and performs well in high-dimensional feature spaces.

### Decision Tree

A rule-based classification algorithm that recursively partitions the feature space to make predictions. Decision trees provide interpretable decision paths and feature importance information.

## Feature Scaling

Since KNN and SVM are distance-based algorithms, **StandardScaler** was applied to normalize feature values before training.

## Hyperparameter Tuning

GridSearchCV with 5-fold cross-validation was used to identify optimal model parameters and improve model performance.

## Evaluation Metrics

Models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix

Due to class imbalance in the dataset, special attention was given to **F1 Macro Score** and **Recall** for minority classes.

## Results

| Model         | Accuracy |
| ------------- | -------- |
| KNN           | 91%      |
| SVM           | 92%      |
| Decision Tree | 93%      |

## Key Findings

* The dataset is moderately imbalanced, with the majority of observations belonging to the Normal class.
* Feature scaling significantly improves the performance of distance-based algorithms.
* Hyperparameter tuning improves model generalization and classification performance.

## Author

**Harini Ramanan**


