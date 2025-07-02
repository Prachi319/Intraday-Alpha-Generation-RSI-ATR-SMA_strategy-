# 📈 FinTraday Alpha Strategy – RSI + ATR + SMA + ML Signals

Welcome to the **FinTraday Alpha Strategy**, an advanced intraday trading strategy that blends traditional technical indicators—**RSI**, **ATR**, and **SMA**—with **machine learning classification models** to generate high-probability trade signals.

---

## 🚀 Project Highlights

* ✅ Uses **RSI, SMA (short & long), and ATR** to form technical features
* ✅ Applies **Random Forest Classifier** to predict trade signals
* ✅ Implements a **realistic trade simulator** with dynamic SL/TP based on ATR
* ✅ Calculates detailed **performance metrics** (Win Rate, R/R Ratio, Return %)
* ✅ Plots the **Equity Curve** of the strategy
* ✅ Supports multi-ticker backtesting

---

## 📚 Strategy Logic

### 📊 Indicators Used

* **RSI (Relative Strength Index)**: Momentum oscillator to detect oversold/overbought zones
* **ATR (Average True Range)**: Volatility-based dynamic SL/TP
* **SMA (Simple Moving Averages)**: Trend direction (short-term & long-term)

### 🧠 ML-Driven Signal Generation

* Features: `RSI`, `ATR`, `SMA_Short`, `SMA_Long`
* Label: Predicts price movement `n` bars ahead
* Model: `RandomForestClassifier` (tuned with GridSearch on one ticker)
* Output: Buy signal when `ML_Pred = 1`

### 🛒 Trade Execution Rules

* **Entry**: If `ML_Pred = 1` → Go long
* **Exit**:

  * Stop-loss = Entry − (ATR × multiplier)
  * Take-profit = Entry + (ATR × multiplier)
  * Or, exit after a fixed time horizon

---

## 📈 Example Metrics (Simulated)

* Total Trades: 42
* Win Rate: 59.5%
* Reward/Risk Ratio: 1.85
* Total Return: +12.3%
* Avg Win: ₹432.5
* Avg Loss: ₹233.6
* Final Equity: ₹11,230 (from ₹10,000 initial)

> ⚠️ These are sample results; actual performance depends on ticker, timeframe, and data.

---

## 🗂️ File Structure

```
RSI_ATR_SMA_Strategy/
├── RSI, ATR, SMA_Strategy.ipynb       # Main notebook
├── trade_log.csv                      # Logged trades from simulation
├── requirements.txt                   # Required packages
└── README.md                          # This file
```

---

## 🛠️ Setup Instructions

1. Clone the repository:

```bash
git clone https://github.com/yourusername/fintraday-alpha-strategy.git
cd fintraday-alpha-strategy
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open the notebook and run all cells:

```bash
jupyter notebook "RSI, ATR, SMA_Strategy.ipynb"
```

---

## 📊 Performance Reporting

At the end of the simulation:

* Individual ticker performance is shown
* A combined **overall portfolio performance** is reported
* Equity Curve is plotted using `matplotlib`

---

## 🧪 Future Enhancements

* Add more ML models (XGBoost, LSTM)
* Integrate live market data (via `yfinance`, `alpaca`, etc.)
* Deploy Streamlit dashboard for real-time interaction
* Include short-side logic (sell signals)

---

## 📢 Disclaimer

> This project is for **educational and research purposes only**.
> Trading in financial markets carries risk. Use this strategy at your own discretion.

---

