# Mean Reversion Strategy Backtester

This project implements a mean reversion trading strategy using cointegrated stock pairs.

## 📌 Overview

- **`pair_backtester.ipynb`**: Backtests a single pair of stocks passed in by the user.
- **`batch_backtester.ipynb`**: Takes a list of stock pairs, tests each for cointegration, backtests the cointegrated ones, and ranks them by Sharpe ratio.

## 🔍 Methodology

- Cointegration tested via Engle-Granger test (ADF)
- Entry/exit signals generated using z-score of residuals
- Thresholds optimized on training set
- Strategy performance evaluated via Sharpe ratio, drawdown, and total return

## 📂 Folder Structure

- `results/`: Output CSVs (e.g. `sharpe_rankings.csv`) and equity curve plots
- `notebooks/`: Exploratory or development notebooks

## ⏱️ Runtime

- `batch_backtester.ipynb` may take ~10 minutes to run on 200 pairs
- A smaller subset or “quick mode” can be implemented for faster runs

## 💡 Example Result (PH/EMR)

- Cointegration p-value: 0.046  
- Optimized entry: 1.50 | exit: 0.90  
- **Training Sharpe**: 0.61 | **Test Sharpe**: 0.75  
- **Test Total Return**: 29.4% | **Max Drawdown**: 8.3%

## ⚙️ Requirements

Install required packages with:

```bash
pip install -r requirements.txt
