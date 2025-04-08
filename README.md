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
- [Conclusion](#-conclusion)
- [References](#-references)
- [Author](#-author)

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

## Environment Setup

To run this project, make sure you have the following installed:

### Python Version

- Python 3.8 or later




