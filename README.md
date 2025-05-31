# 📈 Financial Survival Analysis with DeepSurv

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

> A deep learning-based survival model to predict **time until a profitable stock event** using **DeepSurv**, blending financial data and survival analysis.

---

## 📌 Project Overview

This project explores the use of **DeepSurv**, a deep learning extension of the classical **Cox Proportional Hazards (CoxPH)** model, applied to financial data to **predict time-to-profitability** of stock prices. By replacing linear assumptions with a neural network, DeepSurv captures complex market patterns and risk factors.

---

## 🔍 Application

- 📊 **Domain**: Stock Price Movement Prediction  
- 🎯 **Objective**: Predict the time until a significant positive movement in stock price occurs (e.g., buy signal).

---

## 📁 Dataset

- **Source**: Custom-processed stock dataset (e.g., AMD stock)
- **Features**: Technical indicators, lag features, volume, candlestick patterns
- **Target**: Time-to-event (profit) and censoring indicator (if profit not yet occurred)

---

## 🧠 Model Architecture

- **Input Layer**: Engineered financial features  
- **Hidden Layers**: Fully connected layers (ReLU activations)  
- **Output**: Risk score → used in Cox Partial Likelihood loss  
- **Loss**: Negative Log Partial Likelihood

![Architecture](./images/architecture.png)

---

## ⚙️ Hyperparameters

| Parameter         | Value        |
|------------------|--------------|
| Hidden Layers     | [128, 64, 32]|
| Activation        | ReLU         |
| Optimizer         | Adam         |
| Learning Rate     | 0.001        |
| Epochs            | 100          |
| Batch Size        | 64           |

---

## 📈 Evaluation Metrics

- **Concordance Index (C-index)**  
- **Integrated Brier Score**  
- **Log-Rank Test**  
- **Survival Curves Visualization**

---

## 📊 Results Summary

- ✅ DeepSurv outperformed traditional CoxPH in all metrics  
- 🔁 Captured non-linear patterns between market conditions and profitability  
- 📈 C-index improved from **0.61 (CoxPH)** → **0.74 (DeepSurv)**

---

## 🛠️ How to Run

```bash
# Clone the repository
git clone https://github.com/yourusername/DeepSurv-Financial-Survival.git
cd DeepSurv-Financial-Survival

# (Optional) Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate

# Install requirements
pip install -r requirements.txt

# Run training script
python train.py
