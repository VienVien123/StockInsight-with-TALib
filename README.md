# StockInsight with TALib

## Table of Contents

1. [Introduction](#introduction)
2. [Technologies Used](#technologies-used)
3. [Introduction to the TA-Lib Library](#introduction-to-the-ta-lib-library)
   - [RSI (Relative Strength Index)](#rsi-relative-strength-index)
   - [ATR (Average True Range)](#atr-average-true-range)
   - [Bollinger Bands (BB)](#bollinger-bands-bb)
4. [TA-Lib Installation Guide](#ta-lib-installation-guide)

---

## Introduction

**StockInsight-with-TALib** is a tool for analyzing financial indicators based on stock price data using the **TA-Lib** library.

Input data includes:
- Opening price (Open)
- Highest price (High)
- Lowest price (Low)
- Closing price (Close)
- Trading volume (Volume)

---

## Technologies Used

- **Programming Language**: Python
- **Development Environment**: Jupyter Notebook (`.ipynb`)
- **Python Version**: 3.8 or higher
- **Supported Operating Systems**: Windows, Linux, and macOS

---

## Introduction to the TA-Lib Library

**TA-Lib** (Technical Analysis Library) is a powerful library for technical analysis in financial markets. Some indicators used in this project include:

### RSI (Relative Strength Index)
```python
df['RSI'] = talib.RSI(df['Close'], timeperiod=14)
```
- **Meaning**: RSI measures price strength over a period (typically 14 days) to assess whether a stock is in an overbought or oversold condition.
- **General Rules**:
  - RSI > 70: Overbought (price may decrease).
  - RSI < 30: Oversold (price may increase).

### ATR (Average True Range)
```python
df['ATR'] = talib.ATR(df['High'], df['Low'], df['Close'], timeperiod=14)
```
- **Meaning**: ATR measures the price volatility of a stock over a 14-day period. It evaluates the risk level of the stock.
- **General Rules**:
  - High ATR: High volatility, high risk.
  - Low ATR: Low volatility, stable market.

### Bollinger Bands (BBands)
```python
upper, middle, lower = talib.BBANDS(df['Close'], timeperiod=20)
df['BB_upper'] = upper
df['BB_middle'] = middle
df['BB_lower'] = lower
```
- **Meaning**: Bollinger Bands create three bands to evaluate price volatility:
  - **BB_upper**: Upper band (price exceeds normal levels).
  - **BB_middle**: Middle line (simple moving average).
  - **BB_lower**: Lower band (price drops below normal levels).
- **General Rules**:
  - When the price touches or exceeds BB_upper: A downward adjustment may occur.
  - When the price touches or falls below BB_lower: An upward recovery may occur.

---

## TA-Lib Installation Guide

### Step 1: Install TA-Lib
Open the terminal in VSCode and run the following commands:
```bash
conda install -c conda-forge ta-lib
conda install -c conda-forge libta-lib
```

### Step 2: Import TA-Lib into the Code
After successful installation, you can import TA-Lib as follows:
```python
import talib
```

--- 
