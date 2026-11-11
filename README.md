# CAC 40 Markowitz Portfolio — Risk and Performance

## Overview

Construction and evaluation of a daily-rebalanced Markowitz portfolio using ten CAC 40 stocks across September 2022–March 2023. Minute-level OHLC prices are aggregated into daily returns, with lag-one autocorrelation estimates providing simple next-day return forecasts for unconstrained mean–variance allocation.

## Methodology

- **Market data:** Aggregate intraday closing prices into aligned daily return series for ten equities across multiple sectors.
- **Return and risk estimation:** Calculate lag-one autocorrelations, covariance and correlation matrices, and AR(1)-style return projections.
- **Portfolio optimization:** Compute fully invested Markowitz weights with unrestricted short positions and rebalance them daily.
- **Performance assessment:** Evaluate ex-ante and ex-post Sharpe ratios, upside potential ratio, maximum drawdown, and asset-level volatility contributions through Euler decomposition.

## Main Findings

All ten return series exhibit negative lag-one sample autocorrelation, providing a weak mean-reversion signal. The reported daily Sharpe ratios are **−0.0561 ex-ante** and **0.0296 ex-post**, indicating little risk-adjusted performance. Unconstrained weights can become extremely leveraged, producing a reported maximum drawdown of **1.4765** (147.65% of prior peak portfolio value).

These are **in-sample** results: the covariance matrix and autocorrelations are estimated using the complete sample. The analysis therefore has look-ahead bias and excludes trading and financing costs. 
