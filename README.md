## USD to INR Time Series Analysis and Forecasting

### Overview
--------
This project analyzes daily USD to INR exchange rate data and builds ARIMA-based forecasts through 2026.
The notebook includes data collection, trend analysis, stationarity testing, forecasting, and model evaluation.

#### Main Notebook
-------------
notebooks/USD_to_INR_Analysis.ipynb

### What the Notebook Does
----------------------
1. Imports required libraries:
	yfinance, pandas, numpy, matplotlib, statsmodels, and scikit-learn metrics.

2. Downloads market data:
	- Ticker: INR=X
	- Start date: 2020-01-01
	- Keeps only the Close column and removes missing rows.

3. Performs base visualization:
	- Plots daily USD to INR exchange rate over time.

4. Runs moving average analysis:
	- 90-day Simple Moving Average (SMA_90)
	- 30-day Exponential Moving Average (EMA_30)
	- Compares raw series vs smoothed trend lines.

5. Tests stationarity using ADF:
	- Runs Augmented Dickey-Fuller test on original Close series.
	- Applies first-order differencing.
	- Re-runs ADF test on differenced series.
	- Plots differenced values.

6. Builds ARIMA forecast (baseline):
	- Train/test split using last 90 days as test.
	- ARIMA order: (5, 2, 0)
	- Forecasts roughly 195 business days into late 2026.

7. Builds ARIMA forecast (improved):
	- Train/test split using last 30 days.
	- Tests candidate ARIMA orders and selects best by train AIC.
	- Uses walk-forward one-step prediction on test data.
	- Retrains on full data and forecasts up to 2026-12-31.
	- Adds 95% confidence interval.

8. Evaluates model:
	- Mean Squared Error (MSE)
	- Root Mean Squared Error (RMSE)
	- R-squared (R2)

### Dependancies
------------
Install the Python packages used in the notebook using `pip install -r requirements.txt`

### How to Run
----------
1. Activate your virtual environment.
2. Open notebooks/USD_to_INR_Analysis.ipynb.
3. Run cells from top to bottom.
4. Review generated plots and printed metrics.
