# iaTrader

iaTrader Shop, Stock and Strategy Analytics with Tester
## Shop Analytics
<img width="1024" height="588" alt="Shop Analytics" src="https://github.com/user-attachments/assets/03800ffe-0409-4bf1-b01d-d3a442f3c95c" />

## Stock Analytics
<img width="1024" height="588" alt="Stock Analytics" src="https://github.com/user-attachments/assets/c018bb4c-f538-4c7b-a776-343a2221bbb1" />

## Shop Analytics with Strategy Tester

### Shop Analytics with Tester Enable
<img width="1024" height="588" alt="image" src="https://github.com/user-attachments/assets/eca66206-a140-43c1-88ba-2f3d163292c8" />

### Strategy Tester Statistics
<img width="1024" height="588" alt="image" src="https://github.com/user-attachments/assets/052e8f3a-e3a8-4848-a7f2-20897dade584" />

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
