
# Pair Trading Backtester

This repository contains two Jupyter notebooks implementing a **Pair Trading Backtester** using Python. The notebooks demonstrate how to:

- Download and process historical stock data with `yfinance`.
- Test for cointegration between pairs of assets.
- Generate trading signals based on z-score thresholds.
- Optimise entry and exit thresholds for the strategy.
- Calculate returns, transaction costs, and leverage dynamically using the Kelly criterion.
- Evaluate strategy performance with Sharpe ratio, drawdown, and total return.
- Visualise cumulative returns on training and test datasets.

---

## Contents

- `backtest_pair.ipynb` â Basic implementation of the pair trading backtester with key methods and a demonstration on a sample pair.
- `batch_backtester.ipynb` â Enhanced version with additional features including print control, silent mode, and testing multiple pairs.

---

## Features

- **Data Handling:** Uses Yahoo Finance via `yfinance` to download historical adjusted close prices.
- **Cointegration Testing:** Statistical test to validate the mean-reverting relationship between pairs.
- **Dynamic Position Sizing:** Leverages the Kelly criterion for position sizing with a cap on maximum leverage.
- **Threshold Optimisation:** Grid search for optimal entry and exit z-score thresholds to maximize Sharpe ratio.
- **Performance Metrics:** Calculates Sharpe ratio, maximum drawdown, and total cumulative return.
- **Plotting:** Visualisation of cumulative returns for both training and testing periods.

---

## Requirements

- Python 3.7+
- Jupyter Notebook or JupyterLab
- Libraries:
  - `yfinance`
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `statsmodels`

You can install the dependencies using:

```bash
pip install yfinance pandas numpy matplotlib statsmodels
```

---

## Usage

1. Clone the repository:

```bash
git clone https://github.com/RoryMcTeague/mean-reversion-backtester.git
cd mean-reversion-backtester
```

2. Open either notebook with Jupyter:

```bash
jupyter notebook backtest_pair.ipynb
# or
jupyter notebook batch_backtester.ipynb
```

3. Modify the parameters (tickers, dates, window sizes) and run cells to backtest your desired pairs.

---

## Example

The notebooks demonstrate a sample backtest on the pair `["PH", "EMR"]` with a training/testing split date of `2023-01-01`. The backtester outputs cointegration test results, optimised thresholds, performance metrics, and plots cumulative returns.

---

## License

This project is open-source and available under the [MIT License](LICENSE).

---

## Contact

For questions or feedback, please open an issue or contact me at [rorymcteague@btinternet.com].

---

[LinkedIn](https://www.linkedin.com/in/rory-mcteague-b78637161/)
[Github](https://github.com/RoryMcTeague)

