# Bitcoin Price Prediction Model

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Data Sources](#data-sources)
- [Key Components](#key-components)
- [Output](#output)
- [License](#license)
- [Disclaimer](#disclaimer)

## Overview
This project implements an advanced ensemble model for predicting Bitcoin prices and 7-day Return on Investment (ROI). It combines multiple machine learning algorithms to provide accurate forecasts, incorporating sentiment analysis and dynamic ensemble weighting.

## Features
- Ensemble model using Gradient Boosting, XGBoost, LightGBM, LSTM, SARIMA, and Prophet
- Sentiment analysis from CryptoPanic API
- Advanced feature engineering and selection
- Dynamic weighting for ensemble predictions
- 7-day ROI forecasts with daily breakdowns
- Comprehensive performance evaluation and visualization

## Prerequisites
- Python 3.11.8
- Key packages and versions:
  - numpy==1.26.4
  - pandas==2.2.2
  - scikit-learn==1.5.1 (Note: This was listed as "Not installed or not found" in the environment check)
  - xgboost==2.1.0
  - lightgbm==4.4.0
  - tensorflow==2.17.0
  - keras==3.4.1
  - statsmodels==0.14.1 (Note: Environment shows 0.14.2)
  - pmdarima==2.0.4
  - yfinance==0.2.37
  - matplotlib==3.8.4
  - shap==0.46.0
  - optuna==3.6.1
  - requests==2.32.2
  - textblob==0.18.0.post0
  - ta==0.11.0
  - torch==2.3.1
  - transformers==4.42.3
  - gym==0.26.2
  - stable-baselines3==2.3.2

Note: fbprophet is not included in the default installation. Install separately if needed.

Additional important packages:
  - prophet==1.1.5
  - scikit-image==0.23.2
  - scipy==1.14.0
  - seaborn==0.13.2
  - plotly==5.20.0

System Information:
- Python implementation: CPython
- System: Darwin 24.1.0

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/bitcoin-price-prediction.git
   cd bitcoin-price-prediction
   ```

2. Create a virtual environment:
   ```bash
   python -m venv bitcoin_prediction_env
   ```

3. Activate the virtual environment:
   - On Windows:
     ```bash
     bitcoin_prediction_env\Scripts\activate
     ```
   - On macOS and Linux:
     ```bash
     source bitcoin_prediction_env/bin/activate
     ```

4. Install required packages:
   ```bash
   pip install numpy==1.26.4 pandas==2.2.2 scikit-learn==1.5.1 xgboost==2.1.0 lightgbm==4.4.0 tensorflow==2.17.0 keras==3.4.1 statsmodels==0.14.1 pmdarima==2.0.4 yfinance==0.2.37 matplotlib==3.8.4 shap==0.46.0 optuna==3.6.1 requests==2.32.2 textblob==0.18.0.post0 ta==0.11.0 torch==2.3.1 transformers==4.42.3 gym==0.26.2 stable-baselines3==2.3.2 prophet==1.1.5 scikit-image==0.23.2 scipy==1.14.0 seaborn==0.13.2 plotly==5.20.0
   ```

## Usage

To run the Bitcoin price prediction model:

1. Ensure you're in the virtual environment.
2. Execute the main script:
   ```bash
   python bitcoin_price_prediction.py
   ```

The script will:
1. Fetch historical Bitcoin data
2. Collect sentiment data
3. Preprocess and engineer features
4. Perform feature selection
5. Train and optimize models
6. Generate ensemble predictions
7. Evaluate and display results

## Data Sources
- Historical Bitcoin price data: Yahoo Finance & CryptoCompare (2015 to present)
- Sentiment data: CryptoPanic API

## Key Components
1. Data preprocessing and feature engineering
2. Advanced feature selection (RFECV, LASSO, Random Forest, Mutual Information)
3. Model training and optimization with Optuna
4. Ensemble prediction with dynamic weighting
5. Performance evaluation and visualization

## Output
The model generates:
- 7-day ROI forecast with daily predictions
- Performance metrics (MAE, RMSE, R-squared, MAPE)
- Feature importance analysis
- Visualizations:
  - Actual vs Predicted ROI plots
  - SHAP summary plot for feature importance

## License
This project is licensed under the MIT License - see the [LICENSE] file for details.

## Disclaimer
This model is for educational and research purposes only. Do not use it for financial decisions without consulting a qualified financial advisor. The creators and contributors are not responsible for any financial losses incurred from using this model.