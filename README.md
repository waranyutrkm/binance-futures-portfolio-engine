# Binance Futures Portfolio Engine (Quant)

A **browser-based quantitative portfolio backtesting engine** for **Binance Futures**, designed for **multi-asset momentum strategies, risk-based allocation, and batch strategy comparison**, implemented entirely in client-side JavaScript.

> ⚠️ This project is intended for **research and educational purposes only**.
> It does **NOT** place real trades and does **NOT** constitute financial advice.

---

## 🚀 Key Features

* 📊 **Multi-Asset Futures Portfolio Backtesting**
* 🧠 **Quantitative Strategy Support**

  * Momentum (Top-K, Rank-weighted)
  * Dual Momentum (Relative + Absolute)
  * Inverse Volatility (Risk-based allocation)
  * Equal Weight / Rank All
* 🔁 **Batch Parameter Sweeping**

  * Multiple lookback windows
  * Multiple rebalance frequencies
* 📈 **Performance Metrics**

  * CAGR
  * Sharpe Ratio
  * Max Drawdown
  * Portfolio Turnover
* 🧪 **Rolling Horizon Analysis**

  * Best / Worst / Average returns
  * Win probability by holding period
* 📉 **Benchmark Comparison**

  * BTC
  * ETH
  * Equal-weight universe
* 🔍 **Built-in Data Inspector**

  * Detect missing or broken symbols
* 🌐 **100% Client-side Execution**

  * No backend
  * No API keys required

---

## 🧠 Strategy Overview

| Strategy           | Description                                    |
| ------------------ | ---------------------------------------------- |
| Top3 Equal         | Select top 3 assets by momentum, equal weight  |
| Top3 Rank          | Select top 3 assets, weighted by momentum rank |
| Rank All           | Allocate across all assets by momentum rank    |
| Equal Weight       | 1/N allocation across all assets               |
| Dual Momentum      | Absolute + Relative momentum filter            |
| Inverse Volatility | Lower volatility receives higher allocation    |

**Momentum Signal**

* Lookback return over a configurable window

**Rebalancing**

* Periodic portfolio weight adjustment

**Leverage**

* Applied directly to daily returns

**Transaction Cost**

* Applied based on portfolio turnover at each rebalance

---

## 📊 Data Source

* **Binance Futures API (FAPI)**
* Timeframe: **Daily (1D)**
* Price used: **Close price**
* Missing data handling: **Forward-fill**

```
Endpoint: https://fapi.binance.com/fapi/v1/klines
```

> The daily timeframe is intentionally chosen to support long-range backtesting (3–5 years) within browser memory constraints.

---

## 🖥 How to Use

### Option 1: Run Locally

1. Clone or download this repository
2. Open `index.html` in a modern browser (Chrome recommended)
3. Configure:

   * Strategy
   * Asset universe
   * Lookback window & rebalance frequency
4. Click **Run Engine**

### Option 2: GitHub Pages

1. Fork this repository
2. Enable GitHub Pages (Settings → Pages)
3. Run the engine directly from your browser

---

## 📈 Output & Analysis

* **Batch Comparison Table**

  * Automatically sorted by Sharpe Ratio
* **Equity Curve**

  * Log-scale portfolio growth vs benchmarks
* **Rolling Analysis**

  * Return distribution by holding period
  * Win probability (> 0%)
  * Expected annualized return
* **Rebalance Log**

  * Asset allocation history (single-run mode)

---

## ⚠️ Important Notes

* This engine is designed strictly for **strategy research**
* Results are highly sensitive to:

  * Lookback window
  * Rebalance frequency
  * Asset universe
  * Transaction cost assumptions
* Crypto futures trading involves **substantial risk**

---

## 📄 License

This project is released under the **MIT License**.
You are free to use, modify, and distribute this software.

---

## 🧪 Disclaimer

This software is provided **“as is”**, without any warranty.
The author assumes **no responsibility** for any financial losses incurred from its use.

Use at your own risk.

---

## ⭐ Acknowledgements

Inspired by:

* Quantitative momentum strategies
* Dual Momentum (Gary Antonacci)
* Portfolio theory and risk parity concepts


