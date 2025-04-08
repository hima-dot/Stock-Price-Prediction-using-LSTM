# Stock-Price-Prediction-using-LSTM
A LSTM model trained on Apple stock prices.
# 📈 Stock Price Prediction using Deep Learning (LSTM)

This project uses a deep learning model to predict the stock price of Apple Inc. using **Long Short-Term Memory (LSTM)** networks. Since stock prices depend heavily on past values, LSTM networks are ideal for modeling such time series data due to their ability to retain long-term dependencies.

---

## Table of Contents

- [Overview](#-project-overview)
- [Tech Stack](#-tech-stack)
- [Dataset](#-dataset)
- [Data Preprocessing](#-data-preprocessing)
- [Model Architecture](#-model-architecture)
- [Training & Evaluation](#-results)
-

---

##  Project Overview

The project aims to:

- Predict the closing price of Apple stock using historical data.
- Utilize LSTM layers to model the sequential dependency in time series data.
- Minimize prediction error using Root Mean Squared Error (RMSE).

**Why LSTM?**

- Handles vanishing gradient problems better than vanilla RNNs.
- Retains long-term dependencies with cell state and gating mechanisms.
- Suitable for financial time-series where predictions depend on past trends.

---

## 🛠Tech Stack

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- TensorFlow / Keras

---

## Dataset

- **Source**: [Yahoo Finance](https://finance.yahoo.com/)
- **Company**: Apple Inc. (AAPL)
- **Features Used**: Only `Close` prices.
- **Time Period**: Custom date range

---

## Data Preprocessing

1. **Missing Values**: Replaced `NaN` with mean values.
2. **Scaling**: Data normalized using `MinMaxScaler` to avoid saturation.
3. **Sequence Creation**: For each time `t`, the model takes the previous 60 closing prices as input and predicts the `t+1` price.

 ---

4. **Train/Test Split**: Data split into training and testing sets after scaling and reshaping.

---

## 🧱 Model Architecture

Input Shape: (60, 1)
↓
LSTM Layer (50 units, return_sequences=True)
↓
LSTM Layer (50 units)
↓
Dense Layer (25 units)
↓
Dense Layer (1 unit)
↓
Unscaled to original price

---

## 🏋️ Training & Evaluation

The model is trained using the **Adam optimizer** and **Mean Squared Error (MSE)** loss function over a number of epochs. Here's an overview of the process:

### ✅ Training Steps

1. **Input**: Sequences of 60 consecutive closing prices.
2. **Target**: The closing price on the 61st day.
3. **Model Fit**:
   - Epochs: Customizable (default used in the project)
   - Batch Size: Tuned based on dataset size
4. **Training Time**: Relatively fast due to the small size of input features.

### 📈 Evaluation Metric

- **Root Mean Squared Error (RMSE)** is used to evaluate prediction accuracy:
  
  \[
  \text{RMSE} = \sqrt{\frac{1}{n} \sum_{i=1}^n (\hat{y}_i - y_i)^2}
  \]

- The **lower** the RMSE, the **better** the model performance.

### 📊 Performance

- **RMSE on test data**: `0.0485`
- **Visual Evaluation**: The predicted closing prices closely follow the actual prices on the test set, showing the model has captured the stock trend effectively.

### 🛠️ Tips to Improve Performance

- Increase the number of epochs
- Use more lagged values (e.g., past 90 or 120 days)
- Add additional LSTM layers or bidirectional LSTM
- Incorporate more features (e.g., open, high, low, volume)
- Apply regularization or dropout to prevent overfitting

---


## Environment Setup

To run this project, make sure you have the following installed:

### Python Version

- Python 3.8 or later




