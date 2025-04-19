
# 🧠 7088CEM: Artificial Neural Networks

This repository contains the implementation and analysis of artificial neural network models used to predict emissions from gas turbines. The models were evaluated on their ability to forecast carbon monoxide (CO) and nitrogen oxides (NOx) based on turbine operating conditions. The project explores two ANN approaches: a Scikit-learn-based Multi-Layer Perceptron (MLP) and a Keras Sequential model, including hyperparameter optimization.

---

## 📁 Repository Structure

| File/Folder       | Description                                                  |
|-------------------|--------------------------------------------------------------|
| `ANN.ipynb`       | Full notebook with data preprocessing, modeling, evaluation, and visualizations |
| `data/`           | Gas turbine emissions dataset from UCI (2011–2015) |

---

## 🎯 Project Objective

To build and evaluate neural network models that forecast CO and NOx emissions using turbine sensor data.

---

## 🔬 Dataset

- **Source:** UCI Machine Learning Repository ([link](https://archive.ics.uci.edu/dataset/551/gas+turbine+co+and+nox+emission+data+set))
- **Records:** 36,733 hourly records (2011–2015)
- **Features:** 9 input features (e.g., temperature, pressure) + 2 targets (CO, NOx)
- **Preprocessing:** Yeo-Johnson transformation, PCA, chronological train/test split

---

## 🧠 Models

### 1. Multi-Layer Perceptron (Scikit-learn)
- Hidden Layers: (128, 64)
- Activation: ReLU
- Solver: Adam with early stopping
- Regularization: L2

### 2. Keras Sequential Model
- Optimizer: Adam (learning rate: 0.001 or 0.0005)
- Layers: Tuned from (64, 32) to (128, 64, 32)
- Dropout: 0.1–0.2
- Early stopping enabled

---

## 📊 Results Summary

### CO Prediction

| Model | MSE    | R²    |
|-------|--------|-------|
| MLP   | 1.9752 | 0.588 |
| Keras | 1.9809 | 0.587 |

> Both models achieved moderate accuracy with R² ≈ 0.58

### NOx Prediction

| Model           | MSE    | R²      |
|------------------|--------|---------|
| MLP              | 187.18 | -0.67   |
| Keras (baseline) | 192.64 | -0.72   |
| Keras (tuned)    | 184.26 | -0.65   |

> NOx proved significantly harder to predict; optimized model showed improvement but remains limited.

---

## 🔧 Future Work

- Incorporate external features (e.g., weather, fuel mix)
- Explore LSTM or ensemble models for NOx
- Apply interpretability tools (e.g., SHAP)
- Test noise reduction and advanced feature engineering

---

## 🧑‍💻 Author

**Itorobong Akpan**  
MSc Data Science & Computational Intelligence  
Coventry University, UK  
📧 akpani4@uni.coventry.ac.uk  
🔗 [GitHub Profile](https://github.com/akpanitorobong)

---
