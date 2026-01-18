# Intrusion Detection System (IDS) using UNSW-NB15

This project implements a supervised Machine Learning–based Intrusion Detection System (IDS) to classify network traffic as **Normal (0)** or **Attack (1)** using the **UNSW-NB15** dataset. Multiple classifiers are trained and compared, including **Decision Tree**, **Random Forest**, **Linear SVM**, and a **Neural Network (MLP)**. The project was developed and executed in **Google Colab**.

---

## Project Overview

Traditional security mechanisms (e.g., firewalls and access control) are primarily preventive and may not identify malicious activity once an attack is already in progress. IDS solutions monitor traffic patterns to detect suspicious behaviour. This project uses supervised ML to learn attack patterns from labelled traffic data and evaluate model effectiveness using common metrics and visualisations.

---

## Dataset

- **Dataset Name:** UNSW-NB15  
- **Source:** Australian Centre for Cyber Security (ACCS), UNSW Canberra  
- **Task Type:** Binary Classification (Normal vs Attack)  
- **Label Column:** `label` (0 = Normal, 1 = Attack)  
- **Optional Column:** `attack_cat` (attack category; not used for binary target)

Dataset link: https://research.unsw.edu.au/projects/unsw-nb15-dataset

---

## Models Implemented

- Decision Tree Classifier  
- Random Forest Classifier  
- Linear Support Vector Machine (LinearSVC)  
- Neural Network (MLPClassifier)

---

## Preprocessing Steps

1. Load training and testing CSV files (or merge multiple CSV parts if required)  
2. Remove non-informative columns (e.g., `id`, and any `Unnamed:*` columns)  
3. Separate features (**X**) and target (**y = label**)  
4. Handle missing values  
   - Numeric: median imputation  
   - Categorical: mode imputation  
5. Encode categorical features (`proto`, `service`, `state`) using one-hot encoding  
6. Scale features for models that require it (SVM, Neural Network)

---

## Evaluation

Each model is evaluated using:
- Accuracy, Precision, Recall, F1-score
- Confusion Matrix
- ROC Curve (DT, RF, and SVM using decision scores)
- Feature Importance (DT & RF)
- “Models in Action” prediction comparison table (same samples across all models)



