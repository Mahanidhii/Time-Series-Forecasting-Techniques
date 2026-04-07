# USD to INR Exchange Rate Forecasting using 
This project focuses on forecasting the daily exchange rate between the US Dollar (USD) and the Indian Rupee (INR) using an Autoregressive Integrated Moving Average (ARIMA) model. The analysis is conducted in a Jupyter Notebook (`USD_to_INR_Analysis.ipynb`).

## Project Overview
The primary goal is to build a time series model that can predict future USD/INR exchange rates. The project involves several key stages of time series analysis:

1.  **Data Acquisition**: Historical exchange rate data is downloaded from the Yahoo Finance API.
2.  **Exploratory Data Analysis (EDA)**: The data is visualized to identify trends, and moving averages (Simple and Exponential) are analyzed.
3.  **Stationarity Testing**: The Augmented Dickey-Fuller (ADF) test is used to check if the time series is stationary. First-order differencing is applied to transform the data into a stationary series.
4.  **Model Selection**: An optimal ARIMA model order (p, d, q) is determined by evaluating multiple candidates and selecting the one with the lowest Akaike Information Criterion (AIC) on the training data.
5.  **Model Training and Evaluation**: The model is evaluated using a walk-forward validation approach on a test set. Performance is measured using Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R-squared (R²).
6.  **Forecasting**: The final model, retrained on the entire dataset, is used to forecast the exchange rate into the future.

## Getting Started

### Prerequisites
Ensure you have Python installed. This project uses a virtual environment to manage dependencies.

### Installation
1.  Clone the repository or download the project files.
2.  Create and activate a virtual environment. For example, using `venv`:
    ```bash
    python -m venv .venv
    # On Windows
    .\.venv\Scripts\Activate.ps1
    # On macOS/Linux
    source .venv/bin/activate
    ```
3.  Install the required packages from `requirements.txt`:
    ```bash
    pip install -r requirements.txt
    ```

### Usage
Open and run the Jupyter Notebook to see the complete analysis and forecasting results:

```bash
jupyter notebook notebooks/USD_to_INR_Analysis.ipynb
```

## Dependencies
The project relies on the following Python libraries:

*   `yfinance`: For downloading financial data.
*   `pandas`: For data manipulation and analysis.
*   `numpy`: For numerical operations.
*   `matplotlib`: For data visualization.
*   `statsmodels`: For time series analysis, including the ARIMA model and ADF test.
*   `scikit-learn`: For model evaluation metrics.
*   `jupyter`: For running the notebook.
