# Stock Indicator Analysis

This project is an exploratory analysis of stock price movement using technical indicators and machine learning. The primary focus is on evaluating which features — such as EMA slopes, RSI, MACD, VWAP distance, etc. — are most predictive of short-term extremes (2-hour highs/lows) to inform potential buy/sell signals.

## Features Analyzed

Engineered dozens of indicators on intraday data, including:

- EMA slopes (e.g. `ema_slope_9`, `ema_slope_20`)
- Distance from EMA (e.g. `price_ema9_dist`)
- RSI, Stochastic RSI, Williams %R, MFI
- MACD and MACD Signal Line
- VWAP, OBV
- Candlestick features (body, wick sizes)
- Historical lags of price, volume, RSI, MACD

All features were derived from ~30-minute stock price data.

---

## Objectives

- Label timestamps where 2-hour highs and lows occurred
- Use classification to identify indicator patterns before extremes
- Plot top predictive indicators to visualize patterns
- (In progress) Predict ideal **buy** timestamps using top features

---

## Machine Learning

We used a `RandomForestClassifier` to:

- Predict whether a row is a **2-hour high** (or low)
- Rank features by importance for classification
- Visualize how top features behave before highs/lows

Due to limited data, results are preliminary but promising:
