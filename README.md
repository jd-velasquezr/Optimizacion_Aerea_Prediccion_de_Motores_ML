# ✈️ Aerial Optimization: Aircraft Engine Prediction Using Machine Learning

## 🔍 Introduction

Welcome to the Artificial Intelligence Certification Project repository: **“Aerial Optimization: Aircraft Engine Prediction Using Machine Learning.”** This initiative focuses on evaluating aircraft performance to determine their suitability for specific missions. Aircraft performance is a critical factor in aviation, and this project leverages AI techniques to analyze and predict the type of engine based on flight specifications.

---

## 📊 Dataset

The dataset comprises information on **861 aircraft**, including various characteristics such as maximum speed, cruising speed, and range. However, the dataset presents certain challenges, including missing values, inconsistent data formats, and varied units across features.

---

## 📌 Features

The dataset contains numerous features, including:

* Aircraft model
* Manufacturer name
* Engine type
* Shaft horsepower
* Maximum speed
* Stall speed under adverse conditions
* Fuel capacity
* ...and more.

---

## ⚙️ Development Process

The project begins with **data cleaning**, eliminating irrelevant columns for engine classification. Engine type labels are then **converted to numeric values**, and the cleaned dataset is saved as `Aircraft_Handbook.csv`.

The dataset is split into **80% for training** and **20% for validation**, with stratified sampling based on engine type to maintain balance.

A **Principal Component Analysis (PCA)** is used to reduce feature dimensionality, followed by performance evaluation using **five different classifiers**. Metrics such as **Accuracy, F1-Score, Recall**, and **Matthews Correlation Coefficient (MCC)** are used to assess performance.

---

## 🤖 Machine Learning Models

### 🔹 Logistic Regression

Explored various hyperparameters including penalty norms and regularization strength.

### 🔹 Support Vector Machines (SVM)

Tested different kernel functions, regularization parameters, and OvA/OvO classification strategies.

### 🔹 K-Nearest Neighbors (KNN)

Evaluated number of neighbors, leaf size, and distance metrics.

### 🔹 Gaussian Naive Bayes

Tested with default configurations for baseline comparison.

### 🔹 Neural Networks (Multilayer Perceptron)

Tuned hidden layer sizes, activation functions, solvers, regularization alpha, and learning rates.

---

## 📈 Results

The models were fine-tuned using **GridSearchCV**. Below are the final results per model:

* **Logistic Regression**
  ![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/regresion%20logistica%20p.PNG)

* **Support Vector Machines (SVM)**
  ![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/maquinas%20de%20sop%20vec%20p.PNG)

* **K-Nearest Neighbors (KNN)**
  ![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/KNN%20P.PNG)

* **Gaussian Naive Bayes**
  ![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/naive%20bayes%20p.PNG)

* **Neural Networks (MLP Classifier)**
  ![](https://github.com/NathaliaRivadeneira/Proyecto-inteligencia-artificial/blob/main/Imagenes/perceptron%20mp.PNG)

---

## 🧾 Conclusions

* Among the five classifiers, **SVM and Neural Networks** performed the best, achieving **Matthews Correlation Coefficients of 0.9341 and 0.9352**, respectively. Both are strong candidates for engine classification tasks.

* All classifiers achieved over **86% accuracy**, with **Gaussian Naive Bayes** scoring the lowest at **87.1%**, still making it a viable option with only a \~6% difference compared to top performers.

* During PCA, dimensionality was reduced from 16 to 14 features without major loss in explained variance. Reducing further to 13 or fewer dropped total explained variance below **90%**, confirming the dataset contains highly independent and informative features.

* While **Neural Networks (MLPC)** achieved the highest score, it also had the **longest runtime**, taking over **3 minutes for grid search** and around **248.57 seconds for training**. Thus, although powerful, it may not be suitable for environments with limited hardware and should be tested accordingly.

---

This project presents a detailed application of machine learning techniques for classifying aircraft engine types and aims to be a valuable contribution to both the **AI** and **aeronautics** communities.

---
