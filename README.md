# 📉 Mean Reversion Pairs Trading Bot

A quantitative finance project that identifies and trades cointegrated stock pairs using statistical arbitrage.

## 🚀 Project Overview
This bot scans the market for pairs of stocks that are mathematically linked (Cointegrated). When the "spread" between them diverges significantly from the mean (Z-Score > 2.0), the bot executes a market-neutral trade, betting on convergence.

## 🛠️ Tech Stack
* **Python 3.10+**
* **Statsmodels:** For ADF Tests (Stationarity) and OLS Regression (Hedge Ratios).
* **Pandas/NumPy:** For vectorised backtesting and data manipulation.
* **YFinance:** For fetching historical market data.

## 📊 Strategy Mechanics
1.  **The Hunter:** Scans a universe of tickers (e.g., Tech Sector) to find pairs with p-value < 0.05 (Cointegrated).
2.  **The Signal:** Calculates the Z-Score of the spread using a 30-day rolling window to avoid look-ahead bias.
3.  **Risk Management:** Implements a "Circuit Breaker" (Stop Loss) if the spread diverges beyond 4.0 standard deviations.
4.  **Friction:** Accounts for 0.1% transaction costs per trade to ensure realistic PnL.

## 📈 Performance (Backtest: 2022-2025)
* **Pair:** AMZN vs META
* **Sharpe Ratio:** 0.46
* **Max Drawdown:** -0.42%
* **Net Profit:** Profitable after fees.

## 📥 How to Run
1.  Clone the repo:
    ```bash
    git clone [https://github.com/YOUR_USERNAME/algo-pairs-trader.git](https://github.com/YOUR_USERNAME/algo-pairs-trader.git)
    ```
2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3.  Run the notebook `Pairs_Trading_Bot.ipynb` in Jupyter.

## 📜 License
MIT License