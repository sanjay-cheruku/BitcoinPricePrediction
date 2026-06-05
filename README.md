# 📈 Bitcoin Price Prediction

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-Machine%20Learning-blue?style=for-the-badge)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)

**A machine learning pipeline to forecast daily Bitcoin price movements using market history and Wikipedia sentiment data.**

</div>

## 🌟 Overview

This project explores the fascinating intersection of **market data** and **public sentiment** to predict the future price of Bitcoin. By combining historical trading prices (via Yahoo Finance) with Wikipedia edit history and sentiment analysis (via HuggingFace Transformers), we build a robust predictive model.

We start with a baseline Random Forest classifier and iteratively improve our feature engineering before switching to a highly optimized XGBoost model for greater accuracy. 

### 🎯 Key Features
- **Data Pipeline**: Automated merging of Yahoo Finance market data and Wikipedia page edit telemetry.
- **Sentiment Analysis**: NLP processing on Wikipedia edits to gauge public sentiment toward Bitcoin.
- **Machine Learning**: Random Forest and XGBoost predictive modeling.
- **Backtesting Engine**: A custom, robust backtesting framework with targeted error metrics for financial forecasting.

---

## 🗂️ Repository Structure

- `prediction.ipynb` — The primary Jupyter Notebook for data cleaning, feature engineering, backtesting, and model evaluation.
- `sentiment.ipynb` — The NLP and web-scraping notebook responsible for querying the Wikipedia API and generating the sentiment dataset.
- `btc.csv` *(or dynamically generated)* — The dataset combining prices and edit counts.

---

## 🚀 Quick Start

### 1. Prerequisites
Ensure you have Python 3.8+ installed, along with JupyterLab.

### 2. Installation
Install the required Python packages:

```bash
pip install pandas yfinance scikit-learn xgboost mwclient transformers jupyterlab
```

### 3. Running the Pipeline

1. **Generate the Sentiment Data**  
   Open and run `sentiment.ipynb` from top to bottom. This will query Wikipedia for the latest edits and perform sentiment analysis, bringing the dataset completely up to date.

2. **Train & Backtest the Model**  
   Open `prediction.ipynb`. By default, this notebook can run using a cached `btc.csv` file. To ensure you have the absolute newest trading data, remove the caching step so it dynamically pulls the latest prices from Yahoo Finance before training.

---

## 💡 Future Extensions
The backtesting framework and feature pipeline are designed to be highly modular. You can easily extend this architecture to predict price movements for other cryptocurrencies (e.g., Ethereum, Solana) by adjusting the Wikipedia page targets and Yahoo Finance ticker symbols!
