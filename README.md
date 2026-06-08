# bitcoin-sentiment-trader-analysis

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas)
![License](https://img.shields.io/badge/License-MIT-green)
![Trades](https://img.shields.io/badge/Trades%20Analysed-211%2C224-orange)

> Analysing how Bitcoin market sentiment (Fear/Greed Index) influences
> the trading performance of 32 Hyperliquid perpetuals traders across
> a 2-year period (May 2023 – May 2025).

---

## Overview

This project merges two datasets:
- **Trader data** — 211,224 closed perpetual trades from 32 Hyperliquid accounts
- **Fear/Greed Index** — daily Bitcoin sentiment scores (0–100)

It answers three core questions:
1. Do traders perform differently during Fear vs Greed periods?
2. Is the sentiment–PnL relationship statistically significant?
3. Does a contrarian or momentum strategy produce better results?

---

## Key Findings

| Metric | Fear | Neutral | Greed |
|---|---|---|---|
| Trade Count | 83,237 | 37,692 | 90,295 |
| Total PnL | $4.10M | $1.34M | $4.87M |
| Avg PnL / Trade | $49.21 | $35.43 | $53.88 |
| Win Rate | 40.8% | 39.7% | 42.0% |

- **p = 0.32** — sentiment alone does NOT significantly predict trade outcome
- **Contrarian** trades avg $71.59/trade vs **Momentum** at $32.12/trade
- Top 5 traders generate **61.7%** of all PnL (concentrated performance)

---

## Project Structure

```
bitcoin-sentiment-trader-analysis/
│
├── data/
│   ├── trader_data.csv          # Raw trade records
│   └── fear_greed.csv           # Daily Fear/Greed Index values
│
├── notebooks/
│   └── DSAssignment.ipynb       # Full analysis notebook
│
├── outputs/
│   ├── summary_sentiment_pnl.csv
│   ├── top50_traders.csv
│   ├── strategy_comparison.csv
│   ├── chart1_sentiment_pnl.png
│   ├── chart2_pnl_distributions.png
│   ├── chart3_monthly_trend.png
│   ├── chart5_correlation.png
│   ├── chart6_contrarian_momentum.png
│   └── chart7_top_traders.png
│
├── report/
│   └── PrimeTrade_Report_with_Code.docx  # Full insights report
│
├── requirements.txt
└── README.md
```

---

## Setup

```bash
git clone https://github.com/YOUR_USERNAME/bitcoin-sentiment-trader-analysis.git
cd bitcoin-sentiment-trader-analysis
pip install -r requirements.txt
jupyter notebook notebooks/DSAssignment.ipynb
```

---

## Requirements

```
pandas
numpy
matplotlib
seaborn
scipy
jupyter
```

Or install directly:

```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

---

## Analysis Sections

### 1. Data Loading & Merging
Loads trader CSV and Fear/Greed CSV, normalises dates, and merges on date key.

### 2. Sentiment Bucketing
Classifies each trade into Fear / Neutral / Greed based on the daily FGI value.

### 3. PnL Summary by Sentiment
Aggregates total PnL, mean PnL, median PnL, trade count, and win rate per sentiment bucket.

### 4. Statistical Testing
Runs Welch's t-test and Mann-Whitney U test to check if Fear vs Greed PnL difference is significant.

### 5. Contrarian vs Momentum
Labels each trade as contrarian (against sentiment) or momentum (with sentiment) and compares outcomes.

### 6. Top Trader Analysis
Ranks all 32 traders by total PnL and visualises win rate vs trade count.

### 7. Visualisation
Generates 7 charts covering sentiment performance, PnL distributions, monthly trends, and correlation.

---

## Report

A full formatted Word report (`PrimeTrade_Report_with_Code.docx`) is included in `/report/`.
It contains all analysis, tables, insights, and the complete annotated code.

---

## Dataset Source

- Trader data: Hyperliquid perpetuals (private dataset, PrimeTrade.ai)
- Fear/Greed Index: [alternative.me/crypto/fear-and-greed-index](https://alternative.me/crypto/fear-and-greed-index/)

---

## License

MIT — free to use, modify, and distribute with attribution.

---

*Built as part of a Data Science assignment for PrimeTrade.ai — June 2025*
