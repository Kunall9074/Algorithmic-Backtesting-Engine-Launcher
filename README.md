
# 🚀 Algorithmic Backtesting Engine

A **professional Python backtesting framework** for high-performance strategy testing, analysis, and simulation of real-world trading scenarios.

---

## 🏗️ Core Architecture

Built with an **Event-Driven Design**, this engine mimics real trading environments by processing each price update sequentially. This prevents **look-ahead bias** and ensures strategies only use information available at that point in time.

### Key Components

* **DataLoader** – Load historical data from CSV or Yahoo Finance.
* **Backtest Engine** – The “heart” of the system, iterates through market data while tracking cash, positions, and trades.
* **Portfolio** – Manages balances, calculates commissions, and monitors open positions.
* **Metrics** – Computes advanced risk and performance indicators such as **Sharpe Ratio**, **Max Drawdown**, and **Value at Risk (VaR)**.

---

## 🛠️ Installation & Setup

1. **Clone the Repository**:

   ```bash
   git clone <repo_url>
   cd backtesting_engine
   ```
2. **Install Dependencies**:

   ```bash
   pip install -r requirements.txt
   ```
3. **Run the Interactive Dashboard**:

   ```bash
   streamlit run dashboard.py
   ```

---

## 📈 Supported Trading Strategies

### 1. SMA Crossover (Trend Following)

* **Logic**: Compares Fast & Slow Moving Averages.
* **Buy Signal**: Fast SMA crosses **above** Slow SMA (Golden Cross).
* **Sell Signal**: Fast SMA crosses **below** Slow SMA (Death Cross).
* **Best For**: Trending markets.

### 2. RSI Mean Reversion (Momentum)

* **Logic**: Measures speed and change of price movements.
* **Buy Signal**: RSI < 30 (Oversold).
* **Sell Signal**: RSI > 70 (Overbought).
* **Best For**: Ranging/Sideways markets.

### 3. MACD (Trend + Momentum)

* **Logic**: Uses difference between two EMAs and a signal line.
* **Buy Signal**: MACD crosses **above** Signal line.
* **Sell Signal**: MACD crosses **below** Signal line.

---

## 🤖 Machine Learning Integration

Located in `ml/predictor.py`, this module uses **Scikit-Learn** to forecast price movements.

* **Model**: Linear Regression
* **Features**: Last 5 days’ closing prices (lags) to predict the next day
* **Usage**: Train on historical data to filter out low-probability trades and improve strategy accuracy.

---

## 📊 Performance Metrics

| Metric           | Meaning                                         | Ideal Value      |
| ---------------- | ----------------------------------------------- | ---------------- |
| **Sharpe Ratio** | Risk-adjusted returns                           | > 1.0            |
| **Max Drawdown** | Largest peak-to-trough drop                     | Lower is better  |
| **Win Rate**     | Percentage of profitable trades                 | Higher is better |
| **VaR (95%)**    | Maximum expected daily loss with 95% confidence | Lower is safer   |

---

## 🚀 How to Run

* **Interactive Dashboard**:

  ```bash
  streamlit run dashboard.py
  ```
* **Run Full Test Suite**:

  ```bash
  python test_all.py
  ```
* **Compare Strategies**:

  ```bash
  python main.py --compare
  ```
* **Backtest with Yahoo Finance Data**:

  ```bash
  python main.py --yahoo --symbol RELIANCE.NS
  ```

---

## 📁 Project Structure

```
backtesting_engine/
├─ data/           # Data ingestion
├─ engine/         # Backtesting core logic
├─ strategies/     # Technical strategy implementations
├─ visualization/  # Plotting (Plotly/Matplotlib)
├─ ml/             # Predictive ML models
├─ dashboard.py    # Interactive dashboard
├─ main.py         # Run backtests
```

---



