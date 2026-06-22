# iaTrader

iaTrader Shop, Stock and Strategy Analytics with Tester
<img width="1024" height="588" alt="image" src="https://github.com/user-attachments/assets/14310f52-603f-48f2-a77f-63ab4e3eb0ad" />

## Overview

iaTrader is a suite of Pine Script® indicators and strategies for TradingView, designed to provide comprehensive market analytics, buy/sell signals, and automated strategy backtesting.

## Modules & Features

- **Shop Analytics** (`shop/`): A custom adaptive indicator that tracks price volatility using an efficiency ratio. It generates precise long and short signals with custom chart labels and alert conditions.
- **Stock Analytics** (`stock/`): An oscillator-based indicator that visualizes overbought and oversold levels, trend direction histograms, and moving average crossovers for momentum trading.
- **Strategy Tester** (`strategy/`): A complete trading strategy combining the core analytics with EMA 200 trend filtering, ADX filtering, ATR-based risk management (Stop Loss / Take Profit), and a real-time statistics panel showing win rate, profit factor, and net profit.

## Submodules

After cloning this repo, initialize the submodules to fetch the indicator scripts:

```bash
git submodule update --init --recursive
```
