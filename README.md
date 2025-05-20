
# Pair Trading Backtester

This repository contains a Python class for backtesting a pair trading strategy on historical stock data. The strategy is based on statistical arbitrage principles, primarily relying on cointegration between two assets.

## Overview

The `PairTradingBacktester` class performs the following:

- Downloads historical price data using Yahoo Finance.
- Splits data into training and testing periods.
- Tests for cointegration between the two assets.
- Optimises entry and exit thresholds to maximise the Sharpe ratio.
- Computes hedge ratios and trading signals using z-scores.
- Incorporates transaction costs and dynamic position sizing based on the Kelly criterion.
- Calculates returns, cumulative performance, and risk metrics.
- Plots cumulative returns for visual assessment.

## Requirements

- Python 3.7 or above
- `yfinance`
- `pandas`
- `numpy`
- `matplotlib`
- `statsmodels`

You can install the necessary packages using:

```bash
pip install yfinance pandas numpy matplotlib statsmodels
```

## Usage

1. Import the class and create an instance with your desired parameters:

```python
from pair_trading_backtester import PairTradingBacktester

tickers = ["AAPL", "MSFT"]
start_date = "2010-01-01"
end_date = "2023-01-01"

backtester = PairTradingBacktester(tickers, start_date, end_date)
```

2. Run the backtest by specifying a date to split training and testing data:

```python
split_date = "2020-01-01"
backtester.run(split_date)
```

3. Review printed output for performance metrics and view the plotted cumulative returns.

## Parameters

- `tickers`: List of two asset tickers.
- `start_date`: Start date for historical data in `YYYY-MM-DD` format.
- `end_date`: End date for data.
- `window`: Rolling window size for indicator calculations (default: 20).
- `entry_threshold`: Z-score threshold to enter a trade (auto-optimised if `None`).
- `exit_threshold`: Z-score threshold to exit a trade (auto-optimised if `None`).
- `cost_per_trade`: Transaction cost per unit traded (default: 0.001).
- `max_leverage`: Maximum allowable leverage (default: 2).
- `kelly_fraction`: Fraction of Kelly criterion to use for dynamic sizing (default: 0.5).
- `print_results`: Whether to print performance metrics and plot results (default: True).

## Notes

- The strategy assumes cointegration between the two selected assets. A cointegration test is performed and results are displayed.
- Thresholds for entering and exiting trades can be optimised automatically based on training data to maximise the Sharpe ratio.
- Transaction costs are factored into strategy returns.
- Leverage is dynamically adjusted according to the Kelly criterion to manage risk.
- Visualisations of cumulative returns are provided for both training and test periods.

## Licence

This project is released under the MIT Licence.
