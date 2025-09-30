# US-Building-Permits-Forecasting

**Project Overview**

This project focuses on forecasting U.S. building permits for 2025-2049 period using multiple time series models. The data (from 1959 to 2024) was retrieved from the U.S. Census Bureau API and scraped with BeautifulSoup for validation and enrichment. The goal was to evaluate different forecasting methods, compare their performance and generate insights about future building activity.

**Data Source**

U.S. Census Bureau (API + BeautifulSoup scraping). Data: Historical U.S. building permits (1959–2024). Format: Stored in permits_cust.xlsx.

🔧 **Methods Used**
1. ARIMA (AutoRegressive Integrated Moving Average)

Baseline statistical model. Used grid search/manual tuning to find best (p, d, q) parameters. Evaluated with RMSE and MSE.

2. SARIMA (Seasonal ARIMA)

Extended ARIMA with seasonal components (P, D, Q, s). Tested different seasonal periods (annual, multi-year cycles). Chosen model based on AIC and validation RMSE.

3. LSTM (Long Short-Term Memory Neural Network)

Deep learning approach for sequential data. Scaled and windowed the data into sequences. Tuned architecture with keras-tuner (units, layers, etc.). Evaluated on original scale with MSE, RMSE and MAE.

4. Prophet (Facebook Prophet)

Additive model for time series. Captured long-term trend + seasonality.  Evaluated with RMSE and MSE. 

📈 **Model Evaluation**

Each model was evaluated on a train-test split (80/20 or 90/10 depending on method).

Metrics used: RMSE (Root Mean Squared Error); MSE (Mean Squared Error); MAE (Mean Absolute Error).


🚀 **Results & Insights**
The performance of four models - ARIMA, SARIMA, LSTM and Prophet - was compared in terms of forecast accuracy. The forecasts for the next 25 years (2025–2049) are based on the model that achieved the best results.
