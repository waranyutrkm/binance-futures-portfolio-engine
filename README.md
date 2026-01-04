# Binance Futures Portfolio Engine (Quant)

A **fully client-side quantitative portfolio backtesting engine** for **Binance Futures**, designed to research **multi-asset momentum strategies, risk-based allocation, and parameter optimization surfaces** — all executed directly in the browser using JavaScript.

> ⚠️ This project is intended **strictly for research and educational purposes**.
> It does **NOT** execute real trades and does **NOT** constitute financial advice.

---

## 🚀 Core Capabilities

### 📊 Multi-Asset Futures Backtesting

* Cross-sectional portfolio construction on Binance Futures pairs
* Daily-resolution backtests suitable for medium–long horizon strategies
* Forward-filled price alignment to ensure continuity

### 🧠 Quantitative Strategy Framework

Supported allocation models include:

* **Momentum-based**

  * Top-K (Equal / Rank-weighted)
  * Top 50% universe
  * Absolute Momentum (trend filter)
  * Dual Momentum (Relative + Absolute)
* **Risk-based**

  * Inverse Volatility (Risk Parity–style)
* **Baseline**

  * Equal Weight
  * Rank All

### 🔁 Batch Parameter Optimization

* Simultaneous sweeping across:

  * Lookback windows
  * Rebalance frequencies
* Automatic ranking by risk-adjusted performance
* Interactive **3D parameter surface visualization**

### 📈 Performance & Risk Metrics

* CAGR
* Sharpe Ratio
* Sortino Ratio
* Max Drawdown
* Calmar Ratio
* Win Rate (daily)
* Portfolio turnover & transaction cost impact

### 🔍 Diagnostics & Transparency

* Built-in **Data Inspector**

  * Detects missing, partial, or broken symbols
* Full **rebalance & allocation logs**
* Benchmark comparison per run

### 🌐 100% Client-Side Execution

* No backend
* No database
* No API keys required
* Runs entirely in a modern browser

---

## 🧠 Strategy Summary

| Strategy           | Allocation Logic                           |
| ------------------ | ------------------------------------------ |
| Top 3 Equal        | Select top 3 momentum assets, equal weight |
| Top 3 Rank         | Select top 3, weight by momentum rank      |
| Rank All           | Allocate across entire universe by rank    |
| Equal Weight       | Uniform 1/N allocation                     |
| Dual Momentum      | Relative momentum + positive trend filter  |
| Inverse Volatility | Lower volatility → higher weight           |

### Signal Definition

* **Momentum**: Lookback return over a configurable window
* **Volatility**: Rolling standard deviation of daily returns (annualized)

### Rebalancing

* Periodic portfolio reweighting
* Turnover-based transaction cost applied at each rebalance

### Leverage

* Applied multiplicatively to daily portfolio returns

---

## 📊 Data Source

* **Binance Futures API (FAPI)**
* Timeframe: **Daily (1D)**
* Price reference: **Close**
* Missing data handling: **Forward-fill**

```
GET https://fapi.binance.com/fapi/v1/klines
```

> The daily timeframe is intentionally chosen to enable multi-year backtests (≈2–5 years) while remaining feasible within browser memory constraints.

---

## 🖥 Usage

### Option 1: Run Locally

1. Clone or download this repository
2. Open `index.html` in a modern browser (Chrome recommended)
3. Configure:

   * Strategy
   * Asset universe
   * Lookback window(s)
   * Rebalance frequency
4. Click **Run Engine**

### Option 2: GitHub Pages

1. Fork this repository
2. Enable GitHub Pages
   `Settings → Pages → Deploy from branch`
3. Launch the engine directly from your browser

---

## 📈 Outputs & Visualization

* **Batch Leaderboard**

  * Ranked by Sharpe Ratio (default)
* **Equity Curve**

  * Log-scale portfolio growth
  * Strategy vs benchmark comparison
* **Parameter Surface**

  * 3D visualization of performance across (Lookback × Rebalance)
* **Allocation Logs**

  * Historical weights and turnover per rebalance

---

## ⚠️ Important Considerations

* This engine is designed for **strategy research**, not production trading
* Results are highly sensitive to:

  * Lookback window
  * Rebalance frequency
  * Asset universe selection
  * Transaction cost assumptions
* Crypto futures trading involves **significant risk**, including liquidation risk when leverage is used

---

## 📄 License

Released under the **MIT License**.
You are free to use, modify, and distribute this software.

---

## 🧪 Disclaimer

This software is provided **“as is”**, without warranty of any kind.
The author assumes **no responsibility** for financial losses resulting from the use of this software.

Use at your own risk.

---

## ⭐ Acknowledgements

Inspired by:

* Cross-sectional momentum research
* Dual Momentum (Gary Antonacci)
* Portfolio theory & risk parity concepts
* Quantitative backtesting methodologies
