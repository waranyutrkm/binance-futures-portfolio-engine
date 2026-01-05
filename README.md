# Binance Futures Portfolio Engine (Quant)

A **fully client-side quantitative portfolio backtesting engine** for **Binance Futures**, built for researching **multi-asset momentum strategies, risk-based allocation, and parameter sensitivity** — all executed directly in the browser using JavaScript.

> ⚠️ **For research and educational purposes only**  
> This project does **NOT** execute real trades and does **NOT** constitute financial advice.

---

## 🚀 Core Capabilities

### 📊 Multi-Asset Futures Backtesting
- Cross-sectional portfolio construction across Binance Futures pairs
- Daily-resolution backtests suitable for medium–long horizon strategies
- Forward-filled price alignment to ensure continuous time series

### 🧠 Quantitative Strategy Framework

Supported allocation models:

**Momentum-Based**
- Top-K (Equal-weighted / Rank-weighted)
- Top 50% of the universe
- Absolute Momentum (trend filter)
- Dual Momentum (Relative + Absolute)

**Risk-Based**
- Inverse Volatility (Risk Parity–style weighting)

**Baseline**
- Equal Weight (1/N)
- Rank All

---

### 🔁 Batch Parameter Optimization
- Simultaneous sweeping across:
  - Lookback windows
  - Rebalance frequencies
- Automatic ranking by risk-adjusted performance
- Interactive **3D parameter surface visualization**

---

### 📈 Performance & Risk Metrics
- CAGR
- Sharpe Ratio
- Sortino Ratio
- Max Drawdown
- Calmar Ratio
- Daily Win Rate
- Portfolio turnover & transaction cost impact

---

### 🔍 Diagnostics & Transparency
- Built-in data inspection
  - Detects missing, partial, or broken symbols
- Full rebalance & allocation logs
- Strategy vs benchmark comparison per run

---

### 🌐 100% Client-Side Execution
- No backend
- No database
- No API keys required
- Runs entirely in a modern browser

---

## 🧠 Strategy Summary

| Strategy            | Category        | Allocation Logic                                                                 |
|---------------------|-----------------|----------------------------------------------------------------------------------|
| Equal Weight        | Baseline        | Allocate equally across all assets (1/N), ignoring relative performance          |
| Rank All            | Momentum        | Allocate across entire universe, weighted by momentum rank                        |
| Top 3 Equal         | Momentum        | Select top 3 momentum assets, equal weight (≈33% each)                            |
| Top 3 Rank          | Momentum        | Select top 3 momentum assets, weighted by rank (e.g. 50% / 33% / 17%)             |
| Top 50% Universe    | Momentum Filter | Select top half of assets by momentum, equal-weighted                             |
| Absolute Momentum   | Trend Filter    | Invest only in assets with positive momentum; otherwise hold cash                |
| Dual Momentum       | Momentum + Trend| Relative momentum selection with absolute (trend) filter                          |
| Inverse Volatility  | Risk-Based      | Allocate inversely proportional to volatility (lower risk → higher weight)       |


---

### Signal Definitions
- **Momentum**: Lookback return over a configurable window
- **Volatility**: Rolling standard deviation of daily returns (annualized)

### Rebalancing Logic
- Periodic portfolio reweighting
- Turnover-based transaction cost applied at each rebalance

### Leverage
- Applied multiplicatively to daily portfolio returns

---

## 📊 Data Source

- **Binance Futures API (FAPI)**
- Timeframe: **Daily (1D)**
- Price reference: **Close**
- Missing data handling: **Forward-fill**

  GET https://fapi.binance.com/fapi/v1/klines



## 🖥 Usage

### Option 1: Run Locally
1. Clone or download this repository
2. Open `index.html` in a modern browser (Chrome recommended)
3. Configure:
   - Strategy
   - Asset universe
   - Lookback window(s)
   - Rebalance frequency
4. Click **Run Engine**

### Option 2: GitHub Pages
1. Fork this repository
2. Enable GitHub Pages  
   `Settings → Pages → Deploy from branch`
3. Launch the engine directly from your browser

---

## 📈 Outputs & Visualization

- **Batch Leaderboard**
  - Ranked by Sharpe Ratio (default)
- **Equity Curve**
  - Log-scale portfolio growth
  - Strategy vs benchmark comparison
- **Parameter Surface**
  - 3D visualization across (Lookback × Rebalance)
- **Allocation Logs**
  - Historical weights and turnover per rebalance

---

## ⚠️ Important Considerations

- This engine is designed strictly for **strategy research**, not production trading
- Results are highly sensitive to:
  - Lookback window
  - Rebalance frequency
  - Asset universe selection
  - Transaction cost assumptions
- Crypto futures trading involves **significant risk**, including liquidation risk when leverage is used

---

## 📄 License

Released under the **MIT License**.  
You are free to use, modify, and distribute this software.

---

## 🧪 Disclaimer

This software is provided **“as is”**, without warranty of any kind.  
The author assumes **no responsibility** for financial losses resulting from the use of this software.

**Use at your own risk.**

---

## ⭐ Acknowledgements

Inspired by:
- Cross-sectional momentum research
- Dual Momentum (Gary Antonacci)
- Portfolio theory & risk parity concepts
- Quantitative backtesting methodologies

