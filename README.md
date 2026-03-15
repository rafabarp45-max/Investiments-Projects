# 📈 Investment Tools — Python Finance Toolkit

A personal collection of Python tools for analyzing the US stock market, tracking dividends, and supporting data-driven investment decisions. Built progressively — starting with dashboards and growing into a broader set of financial analysis tools over time.

---

## 🗂️ Repository Structure

```
investment-tools/
│
├── portfolio_dashboard.ipynb    # Portfolio Analysis Dashboard
├── dividendos_dashboard.ipynb   # Dividend Tracker Dashboard
└── README.md
```

---

## 📊 Dashboards

### 1. Portfolio Dashboard (`portfolio_dashboard.ipynb`)

A comprehensive dashboard for monitoring your US stock portfolio performance using real-time and historical market data.

**Features:**
- 📦 Portfolio summary — total invested, current value, profit/loss
- 📈 Historical portfolio value evolution with cost basis reference line
- 🥧 Portfolio composition by current value (pie chart)
- 📊 Total return per stock (%)
- 📉 Normalized price comparison across all assets (base 100)
- 🔥 Daily returns correlation heatmap for diversification analysis
- 📋 Detailed table with per-ticker metrics and color-coded performance
- 💾 CSV export with timestamp

**Key Metrics Calculated:**
- Current price, average cost, shares held
- Total invested vs. current value per ticker
- Absolute and percentage profit/loss
- Daily price change (%)
- Pairwise asset correlations

**Main Libraries:**
- `yfinance` — real-time and historical market data
- `pandas` — data manipulation
- `plotly` — interactive charts

**Quick Usage:**
```python
# Edit the PORTFOLIO dict in Cell 2 with your own holdings
PORTFOLIO = {
    "AAPL": {"shares": 1.013, "avg_price": 198.03},
    "KO":   {"shares": 2,     "avg_price": 72.38},
    # ... add your tickers
}

PERIODO = "1y"  # options: 1mo, 3mo, 6mo, 1y, 2y, 5y

# Then run all cells in order
```

---

### 2. Dividend Dashboard (`dividendos_dashboard.ipynb`)

A focused tool for tracking, visualizing, and projecting dividend income from your portfolio.

**Features:**
- 📋 Full dividend history per asset (filtered by configurable time window)
- 📅 Monthly dividend income calendar (bar chart)
- 🥧 Dividend distribution by asset (donut chart)
- 📊 Current dividend yield per ticker (horizontal bar)
- 🔮 10-year income projection (flat vs. 5% annual growth scenario)
- 📆 Dividend per share history over time (multi-line chart)
- 💾 CSV export for history and per-ticker summary

**Key Metrics Calculated:**
- Dividends received per payment (dividend/share × your shares)
- Forward dividend yield per ticker
- Annual and monthly income projection
- Total received in the previous year per asset

**Main Libraries:**
- `yfinance` — dividend history and forward dividend rate
- `pandas` / `numpy` — data processing
- `plotly` — interactive charts

**Quick Usage:**
```python
# Edit the PORTFOLIO dict in Cell 2 (same format as portfolio_dashboard)
PORTFOLIO = {
    "JNJ": {"shares": 1,   "avg_price": 157.94},
    "KO":  {"shares": 2,   "avg_price": 72.38},
    "O":   {"shares": 5,   "avg_price": 57.57},
    # ...
}

ANOS_HISTORICO = 3  # years of dividend history to fetch

# Then run all cells in order
```

---

## 🚀 Getting Started

### Requirements

- Python 3.8+
- Jupyter Notebook or JupyterLab

### Installation

```bash
git clone https://github.com/your-username/investment-tools.git
cd investment-tools
pip install yfinance pandas numpy plotly
```

### Running

```bash
jupyter notebook
```

Open either `.ipynb` file and run the cells in order. Edit the `PORTFOLIO` dictionary in **Cell 2** with your own tickers, share quantities, and average purchase prices.

---

## 🔭 Roadmap

This repository is continuously evolving. New tools will be added over time to support smarter and more data-driven investment decisions. Planned additions include:

- **Portfolio Tracker CLI** — command-line version for quick portfolio snapshots
- **Sector & Geography Allocation** — visualize diversification by sector and region
- **Backtesting Engine** — test investment strategies against historical data
- **Earnings Calendar Tool** — track upcoming earnings reports for watchlist stocks
- **Stock Screener** — filter stocks based on custom fundamental and technical criteria
- **Risk Metrics Dashboard** — Sharpe ratio, beta, max drawdown, and more
- **Rebalancing Assistant** — suggestions to bring portfolio back to target allocation

> New tools will be documented here as they are added to the repository.

---

## 📝 Notes

- All market data is sourced from **Yahoo Finance** via the `yfinance` library (free, no API key required).
- Portfolios are configured directly in the notebook — no external files needed.
- Focused on the **US stock market**, with support for London Stock Exchange tickers (e.g. `CSPX.L`, `VWRA.L`).
- This project is for **educational and personal use only** — not financial advice.

---

## 📄 License

MIT License — feel free to use, modify, and share.
