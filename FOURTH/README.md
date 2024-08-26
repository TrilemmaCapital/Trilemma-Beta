# Forecaste Bitcoin weekly ROI

This project is about forecasting the weekly Return on Investment (ROI) of Bitcoin. I was attracted to work on this project since it was one of the [Trilemma Capital Tournaments](https://www.trilemmacapital.com/tournament).
The main question they were seeking to answer was:

*Given the Bitcoin price at 1 PM Pacific Time (8 PM GMT) on each Monday, what will the ROI be at 1 PM Pacific Time (8 PM GMT) on the next Monday?*

Their reference rate for the spot price of Bitcoin was the CoinDesk Bitcoin Price Index (CDIXBX). Since I could not find an API or Python library to provide such data, 
I used the Crypto Coin Comparison Aggregated Index (CCCAGG) provided by the CryptoCompare platform. I had three reasons to use this index:

- I could easily get Bitcoin price data using the `cryptocompare` Python library.
- The methodology used for computing this index is based on a 24-hour volume-weighted average calculation, a time-penalty factor, and an outlier methodology (for more information see [CCCAGG Index Methodology](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://www.cryptocompare.com/media/37746014/cccagg_index_methodology_2021_02.pdf)). This makes it a good estimation of BTC across various indices.
- In this project, we did not explicitly need the exact Bitcoin rate. Actually, we were interested in the weekly ROI metric, which is based on the difference between two BTC prices. Thus, it does not really matter which indices we use.

In this project, we tried various methods including statistical models, deep learning models, and gradient-boosting methods to forecast this metric. 
The final model performance is promising, as it outperformed the baseline model with a benchmark MAE < 3.


This repository contains five notebooks, each with detailed descriptions and explanations of the approaches and techniques used.

1. Analysis_Statistical_Models:
In this notebook, we downloaded Bitcoin price data, calculated ROI, and explained the datasets used in the project. We also trained and evaluated statistical models.

2. DL_Models_4h:
Here, we implemented deep learning models, primarily sequence models, on weekly ROI data extracted every four hours (12 am, 4 am, 8 am, 12 pm, 4 pm, and 8 pm). The reasoning behind using this data is explained in the Analysis_Statistical_Models notebook.

3. DL_Models_8h:
This notebook follows the same approach as DL_Models_4h, but uses weekly ROI data extracted every eight hours (4 am, 12 pm, and 8 pm) for each weekday.

4. Gradient_Boosting_Models_with_Darts:
We used the Darts package, which is designed for time series analysis and forecasting, to apply gradient-boosting models like XGBoost and LightGBM. You can find more info about this package in [this repo](https://github.com/solmazkh114/TimeSeriesAnalysisForecasting).

5. Inference:
In this notebook, we aim to answer a question similar to the tournament's question: "Given the Bitcoin price at 1 PM Pacific Time (8 PM GMT) on Monday, July 29th, 2024, what will the ROI be at 1 PM Pacific Time (8 PM GMT) on Monday, August 5th, 2024?" We used the high-performing models trained in other notebooks to forecast the future value. The 50_runs_results directory contains CSV files with model results, which will help determine the final target value.

   
