# Image Classification using Machine Learning Algorithms  
**Author:** Stan Petrisor Catalin (342C3)  
**Date:** November 2024  

---

## Overview
This project presents an **image classification** built in Python.  
The main goal was to compare and evaluate multiple **feature extraction** and **machine learning algorithms** on two datasets: **Fashion-MNIST** and **Fruits-360**.

The approach involves extracting relevant visual features from images, selecting the most significant attributes, training classical ML models and analyzing their performance through multiple evaluation metrics.

---

## Project Structure
- `tema1.ipynb` – Jupyter Notebook containing the full implementation (feature extraction, preprocessing, model training, and evaluation).  
- `Clasificare de imagini pe baza algoritmilor de invatare automata.pdf` – Report including algorithm explanations, experimental results, performance tables and conclusions.  

---

## Methodology

### Feature Extraction
Different feature extraction techniques were applied to highlight structural and visual information:
- **HOG (Histogram of Oriented Gradients)** – captures object shapes and edges; ideal for grayscale data such as Fashion-MNIST.  
- **PCA (Principal Component Analysis)** – reduces dimensionality while preserving 95% of variance.  
- **ORB (Oriented FAST and Rotated BRIEF)** – used for color-aware feature extraction in the Fruits-360 dataset.

### Feature Selection
After extraction, features were organized using **StandardScaler** and filtered using **SelectPercentile** (top 10%) to retain only the most relevant attributes.

### Models and Training
Several classical ML algorithms were trained and fine-tuned using hyperparameter search:
- **Logistic Regression**
- **Support Vector Machines (SVM)**
- **Random Forest**
- **Gradient Boosted Trees**

Training and evaluation were performed using stratified data splits to ensure balanced class representation.

---

## Results Summary

### Fashion-MNIST
- Best results achieved with **SVM** — accuracy ≈ **88.6%**.  
- **Gradient Boosted Trees** also achieved strong performance (~87%).  
- **Logistic Regression** provided stable but slightly lower results (~84%).  
- **Random Forest** performed between 85–86%.  

### Fruits-360
- Overall accuracy significantly lower due to dataset imbalance and color dependence.  
- **ORB** extraction improved results compared to HOG.  
- Best performance achieved by **SVM** (~52%).  
- **Logistic Regression** and **Random Forest** performed weaker (below 50%).  

---

## Key Insights
- **Feature selection** had a major impact on training speed and accuracy.  
- **HOG** is highly effective for shape-based classification tasks (Fashion-MNIST).  
- **Color-sensitive descriptors** like ORB are crucial for datasets where color defines the object (fruits).  
- Execution time increased with the number of hyperparameter combinations, highlighting the computational trade-offs.  

---

## Evaluation Metrics
Model performance was evaluated using:
- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**
- **Confusion Matrices** (for class-level analysis)

---

## Conclusions
- The combination of **HOG + SVM** provided the best overall performance.  
- Gradient Boosted Trees achieved competitive results with shorter training time compared to SVM.  
- Performance on Fruits-360 was limited mainly by the chosen feature extractors and dataset complexity.
  
---

## References
- [Fashion-MNIST Dataset](https://github.com/zalandoresearch/fashion-mnist)
- [Fruits-360 Dataset](https://www.kaggle.com/moltean/fruits)
