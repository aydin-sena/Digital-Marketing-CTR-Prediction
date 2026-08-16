#  Digital Marketing CTR (Click-Through Rate) Prediction

Welcome to the **Digital Marketing CTR Prediction** project! This repository contains a robust, production-ready machine learning pipeline designed to predict whether a user will click on a digital advertisement based on their demographics and browsing behavior.

## Project Overview
Millions of dollars are spent on digital advertising daily. However, serving ads to users suffering from "banner blindness" drains marketing budgets. This project addresses this business problem by leveraging statistical modeling and machine learning to optimize ad targeting. 

Unlike standard beginner projects, this pipeline is built with strict adherence to industry standards, specifically focusing on **preventing data leakage** and prioritizing **probability calibration (ROC-AUC)** over basic accuracy.

## Tech Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn
* **Algorithms:** Logistic Regression, K-Nearest Neighbors (KNN), Decision Trees

## Key Features & Methodology
* **Temporal Train/Test Split:** To simulate real-world data drift and prevent temporal data leakage, the dataset was split chronologically using the `Timestamp` feature rather than random sampling.
* **Leakage-Free Preprocessing:** Outliers were handled using the IQR Capping method, and feature scaling (`StandardScaler`) was strictly fitted only on the training set to maintain a completely isolated test environment.
* **Hyperparameter Tuning:** `GridSearchCV` and 5-Fold Cross Validation were utilized to find the optimal bias-variance tradeoff for KNN and Decision Tree models.
* **Explainable AI (XAI):** The Decision Tree was carefully pruned (`max_depth=3`, `min_samples_leaf=10`) to provide clear, actionable business rules without overfitting.

## Model Performances
The models were evaluated primarily on the **ROC-AUC** score to ensure highly calibrated probability predictions:

| Model | Accuracy | ROC-AUC Score | Key Insight |
| :--- | :---: | :---: | :--- |
| **Logistic Regression** | 97.50% | **0.9882** | Excellent probability separation; production-ready. |
| **Decision Tree (Pruned)** | 93.50% | **0.9799** | Highly explainable; revealed clear business rules. |
| **KNN (K=3)** | 95.00% | **0.9702** | Achieved a 0.97 Recall for the non-clicking class. |

## Business Insights
1. **Banner Blindness is Real:** The model confirms a strong negative correlation between heavy internet/site usage and ad clicks. 
2. **Budget Optimization:** Marketing budgets should be reallocated toward users with lower daily internet usage, as they demonstrate a significantly higher Return on Investment (ROI) and click probability.

##  Read the Full Article
For a deep dive into the exploratory data analysis (EDA), code explanations, and strategic business outcomes, check out my comprehensive article on Medium:
👉 **[Read the Medium Article Here](https://medium.com/@senaydnn122192/dijital-reklam-b%C3%BCt%C3%A7enizi-kim-%C3%A7%C3%B6pe-at%C4%B1yor-54b23cadc773)**

---
*Developed by Sena*
