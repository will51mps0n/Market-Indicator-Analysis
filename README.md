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

Used a `RandomForestClassifier` to:

- Predict whether a row is a **2-hour high** (or low)
- Rank features by importance for classification
- Visualize how top features behave before highs/lows

## Extra Info

This project is helpful for day trading and understanding signals of confounding variables and how they affect price. This insight can be used to learn and apply these concepts in the market, but it takes really looking at data and understanding what the signals mean to be useful. When looking at these strategies, I typically look at stocks that are volatile pre market movers, and wait for price to intersect with VWAP to start watching for positive signals based on EMA differences and RSI signals that correlate with positive changes when backtesting. 

I used an example date and stock for the data, but this can be done with any stock thanks to the alpaca API - its very powerful for backtesting and understanding historical data. 

I utilized genAI and chat gpt for code comments, to help clarify what each does for anyone wanting to use or learn from this code. 
