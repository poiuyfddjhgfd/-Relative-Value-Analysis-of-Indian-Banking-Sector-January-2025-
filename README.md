#  Cell 1: Environment & Imports
Sets up the Python environment and imports necessary libraries:

Standard libraries: os, datetime, json, warnings

Data manipulation: numpy, pandas

Visualization: matplotlib

Machine learning: RandomForestRegressor, TimeSeriesSplit, cross_val_score, mean_squared_error, r2_score, joblib

Output directory: /mnt/data

# Cell 2: Data Generation/Loading
Defines generate_synthetic_bank() to create synthetic daily and quarterly financial data (prices, EPS, BVPS, NIM, GNPA, etc.) for banks.

Attempts to load real CSV data from /mnt/data for tickers: ['HDFC', 'ICICI', 'SBI', 'KOTAK', 'AXIS'].

If CSVs are missing, synthetic data is generated.

Combines all data into a single DataFrame (all_df) with 4,025 rows × 10 columns.

# Cell 3: Exploratory Data Analysis (EDA)
Group data by ticker and calculate summary statistics:

Close price: first, last, mean, std

EPS & BVPS: first and last values

NIM & GNPA: mean values

Displays a summary table for each bank.

# Cell 4: Feature Engineering
Creates new features from the raw data:

Returns: Return_1d, LogRet_1d

Rolling metrics: Ret20_mean, Ret60_mean, Ret20_std, MA20, MA60

Valuation multiples: P_E, P_B, P_ABV

Fundamental diffs: NIM_diff, GNPA_diff

Lagged prices: Close_lag_1, Close_lag_5, Close_lag_20

Saves the feature-engineered dataset (features_combined.csv) with 4,025 rows × 25 columns.

# Cell 5: Z-Score Visualization
Plots the Z-score of the P/B spread between two selected banks.

Includes horizontal lines for entry (long/short) and exit signals.

Used for pairs trading strategy visualization.

# Key Insights
Synthetic Data Used: No real CSVs were found, so the notebook generated synthetic bank data.

Dataset Size: 4,025 daily observations across 5 banks.

Feature Engineering: Expanded from 10 to 25 features for modeling.

Trading Signals: Includes visual Z-score analysis for pairs trading.

Model-Ready: The dataset is prepared for time-series machine learning (Random Forest) and cross-validation.


This notebook is a complete pipeline for relative value analysis—from data generation to feature engineering and preliminary strategy visualization
