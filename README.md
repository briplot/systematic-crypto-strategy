# Crypto Momentum and Mean Reversion Strategies

This project implements and evaluates systematic trading strategies using historical cryptocurrency data. The strategies include momentum-based approaches, volatility filtering, and mean reversion via residual returns. The goal is to assess whether alpha can be extracted from regime-aware applications of simple statistical signals.

📅 **Author**: Brian Plotnik  
📘 **Date**: October 2024  
🧠 **Focus**: Strategy research, alpha generation, signal design, risk-adjusted return evaluation

---

## 🧠 Project Overview

Cryptocurrency markets are volatile and relatively inefficient compared to traditional markets. This project investigates whether classic systematic momentum and mean reversion strategies can consistently generate excess returns.

Strategies implemented:
- **Z-Score Momentum Strategy**
- **Volatility-Filtered Momentum Strategy**
- **Z-Score Mean Reversion using Residual Returns (BTC-Neutral)**
- **Preliminary Regime-Aware Strategy Switching Logic**

Performance is measured using Sharpe ratio, return-volatility profiles, and visualization of equity curves.

---

## 📊 Methodology

### Data Source
- Historical daily cryptocurrency prices sourced from public APIs (e.g., Binance API)
- Universe includes top-liquid cryptos with sufficient history since 2017

### Strategy 1: Z-Score Momentum
- Signal: z-score of short-term vs long-term return window
- Entry: Go long top-ranked coins, short bottom-ranked
- Parameters: optimized using Bayesian optimization
- Portfolio normalized across assets

### Strategy 2: Volatility Filtered Momentum
- Enhances momentum by trading only during low-volatility periods
- Uses rolling volatility threshold to filter trades

### Strategy 3: Mean Reversion using Residual Returns
- Removes BTC factor using rolling regression to isolate idiosyncratic returns
- Applies z-score thresholding on residuals to capture reversal effects
- Portfolios are normalized and fully invested (long and short)

### Analysis
- Strategy backtests are run over multiple years
- Sharpe ratios are computed pre- and post-cost
- Rolling performance visualizations and cumulative returns plotted
- Regime-dependency noted in performance (e.g., momentum working pre-2021, mean reversion post-2021)

---

## 📈 Results Summary

| Strategy                          | Sharpe Ratio (net-cost) | Notes                                |
|----------------------------------|--------------------------|--------------------------------------|
| Momentum (Z-score)               | ~1.2                     | Strong performance before 2021       |
| Momentum w/ Volatility Filter    | ~1.2                     | Slightly improved Sharpe ratio       |
| Mean Reversion (Residual Z)      | ~1.7                     | Stronger post-2021                   |

---

## 🧪 Tools & Libraries

- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `scipy`, `sklearn`, `statsmodels`
- `bayesian-optimization`
- `binance.client` (for data collection)
- Jupyter Notebook

---

## 📁 File Structure
crypto-strategy-project/
├── cleaned_crypto_project_brianplotnik.ipynb # Full strategy implementation
├── requirements.txt # Python dependencies
├── README.md # This file


---

## ▶️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/crypto-strategy-project.git
   cd crypto-strategy-project

