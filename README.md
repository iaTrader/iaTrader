# iaTrader

iaTrader Shop, Stock and Strategy Analytics with Tester
## Shop Analytics
<img width="1024" height="588" alt="Shop Analytics" src="https://github.com/user-attachments/assets/03800ffe-0409-4bf1-b01d-d3a442f3c95c" />

## Stock Analytics
<img width="1024" height="588" alt="Stock Analytics" src="https://github.com/user-attachments/assets/c018bb4c-f538-4c7b-a776-343a2221bbb1" />

## Shop Analytics with Strategy Tester

### Shop Analytics Tester
<img width="1024" height="588" alt="image" src="https://github.com/user-attachments/assets/eca66206-a140-43c1-88ba-2f3d163292c8" />

### Strategy Tester Statistics
<img width="1024" height="588" alt="image" src="https://github.com/user-attachments/assets/052e8f3a-e3a8-4848-a7f2-20897dade584" />

### Shop Analytics & Strategy with Tester Enable
<img width="1576" height="876" alt="iaTrader Shop Analytics & Strategy" src="https://github.com/user-attachments/assets/3f8e91c8-be25-4e45-a4c4-b5d533c0143b" />

#### Key stats
<img width="1570" height="488" alt="image" src="https://github.com/user-attachments/assets/0033e3b8-f95a-4043-9c4d-3ebc967ee218" />

#### Return details
<img width="1570" height="415" alt="image" src="https://github.com/user-attachments/assets/9e35958d-d4e7-4051-9eef-e0cfe5509a7e" />

#### Trades analysis - Overview
<img width="1570" height="408" alt="image" src="https://github.com/user-attachments/assets/d4c9c70c-ec20-4ff2-8fba-ce541488fb23" />

#### Trades analysis - Details
<img width="1570" height="492" alt="image" src="https://github.com/user-attachments/assets/46441c03-8355-400a-9d8c-3b5dc99c5dcf" />

#### Equity run-ups and drawndowns
<img width="1570" height="415" alt="image" src="https://github.com/user-attachments/assets/aaf62a8e-96e0-4675-b1e9-8cbb55ad6d23" />

#### Capital efficiency - Overview
<img width="1570" height="133" alt="image" src="https://github.com/user-attachments/assets/0ed15a34-dd79-4890-ab02-7193399e0450" />

#### Capital efficiency - Capital usage
<img width="1570" height="365" alt="image" src="https://github.com/user-attachments/assets/606f9e98-0a15-40be-a1ab-c422eff55e8a" />


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
