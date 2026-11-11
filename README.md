# CAC 40 Markowitz Portfolio — Risk and Performance

**Python | Portfolio Optimization | Quantitative Finance**

## Overview

Construction and evaluation of a daily-rebalanced Markowitz portfolio using ten CAC 40 stocks across September 2022–March 2023. Minute-level OHLC prices are aggregated into daily returns, with lag-one autocorrelation estimates providing simple next-day return forecasts for unconstrained mean–variance allocation.

## Methodology

- **Market data:** Aggregate intraday closing prices into aligned daily return series for ten equities across multiple sectors.
- **Return and risk estimation:** Calculate lag-one autocorrelations, covariance and correlation matrices, and AR(1)-style return projections.
- **Portfolio optimization:** Compute fully invested Markowitz weights with unrestricted short positions and rebalance them daily.
- **Performance assessment:** Evaluate ex-ante and ex-post Sharpe ratios, upside potential ratio, maximum drawdown, and asset-level volatility contributions through Euler decomposition.

## Main Findings

All ten return series exhibit negative lag-one sample autocorrelation, providing a weak mean-reversion signal. The reported daily Sharpe ratios are **−0.0561 ex-ante** and **0.0296 ex-post**, indicating little risk-adjusted performance. Unconstrained weights can become extremely leveraged, producing a reported maximum drawdown of **1.4765** (147.65% of prior peak portfolio value).

These are **in-sample** results: the covariance matrix and autocorrelations are estimated using the complete sample. The analysis therefore has look-ahead bias and excludes trading and financing costs. It should not be interpreted as a live or out-of-sample backtest.

## Repository Contents

- `markowitz_portfolio.ipynb` — Data processing, portfolio construction, visualization, and risk attribution.
- `report.pdf` — Mathematical formulation, results, and discussion of methodological limitations.
- `requirements.txt` — Python dependencies.

## Running the Analysis

Install the dependencies:

```bash
pip install -r requirements.txt
```

Place the ten original OHLC spreadsheets in a local `data/` folder, using the names `MC_Prices.xlsx`, `RMS_Prices.xlsx`, `OR_Prices.xlsx`, `AIR_Prices.xlsx`, `SU_Prices.xlsx`, `SAF_Prices.xlsx`, `TTE_Prices.xlsx`, `BNP_Prices.xlsx`, `AI_Prices.xlsx`, and `SAN_Prices.xlsx`. Each Excel file should contain `Dates` and `Close` columns with one introductory header row. Then run `markowitz_portfolio.ipynb` from top to bottom.

The source spreadsheets are not distributed in this repository.
