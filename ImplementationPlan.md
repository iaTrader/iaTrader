# Goal Description

The objective is to integrate the Stock analytics module (WaveTrend-like oscillator) into the main `iaTrader_strategy.pine` script as an optional trading filter. Additionally, we must optimize the overall strategy logic to reduce execution latency and improve the backtest win rate.

This document serves as **Phase 1 (Single-Agent Design)** and the **Decision Log** for the `/multi-agent-brainstorming` process.

## Phase 1: Primary Designer's Initial Design

### 1. Integration of Stock Filter
- **What:** Add the `iaTrader_stock` oscillator logic (WaveTrend) to `iaTrader_strategy.pine`.
- **How:** 
  - Add input: `useStockFilter = input.bool(true, "Usar Filtro Stock")`
  - Include the `hlc3` based EMA calculations (`wt1` and `wt2`).
  - Update the `long` and `short` entry conditions. If `useStockFilter` is true, a `long` entry will require bullish momentum (`wt1 > wt2` or a recent bullish crossover), and a `short` entry will require bearish momentum (`wt1 < wt2`).

### 2. Optimizing Latency
- **What:** Reduce computational overhead in Pine Script.
- **How:** 
  - Avoid redundant `ta.ema` and `ta.stdev` recalculations. Consolidate variables.
  - Pine Script execution latency is largely driven by array operations or redundant historical lookbacks. The current ER calculation (`math.abs(ta.change(ds, p)) / math.sum(math.abs(ta.change(ds)), p)`) is already standard, but we can ensure variables aren't re-evaluated needlessly.
  - We will use `var` declarations for constants where applicable, though most are dynamic.

### 3. Optimizing Win Rate
- **What:** Improve the profitability and win rate of the strategy.
- **How:** 
  - The combination of the ER Trend, EMA 200, ADX, and now the Stock Oscillator creates a highly filtered entry system. 
  - To prevent being *too* restrictive, we will use the Stock Oscillator as a *directional confirmation* (`wt1 > wt2` for Longs) rather than requiring an exact crossover on the same bar.
  - We can also optimize the ADX threshold or the ATR Multipliers (Stop Loss / Take Profit) to give trades more room to breathe, reducing premature stop-outs.

---

## Decision Log

| Decision | Alternatives Considered | Objections Raised (Reviewers) | Resolution & Rationale |
|----------|--------------------------|-------------------------------|------------------------|
| **1. Stock Filter Logic** | Require exact crossover vs. directional confirmation (`wt1 > wt2`). | *Pending* | Chose directional confirmation. Requiring an exact crossover on the exact same bar as the ER Trend change is too restrictive and will miss trades. |
| **2. Latency Optimization** | Rewrite ER to use custom loop vs. built-in `math.sum`. | *Pending* | Built-in functions (`math.sum`, `ta.stdev`) are C-compiled and much faster than Pine Script loops. We will stick to built-ins for latency. |

---

## Open Questions for Review

1. Should the "Stock Filter" require just directional alignment (`wt1 > wt2` for longs), or do you want it to only trigger if the Stock oscillator is also crossing out of the oversold/overbought zones?
2. For optimizing win rates, are you open to adjusting the default ADX threshold (currently 20) and ATR Multipliers (currently 1.5 SL / 3.0 TP)?

---

## Licensing & Monetization Strategy (Decided via Multi-Agent Audit)

Following a structured review of licensing models for TradingView Pine Script, the following strategy will be implemented for commercialization:

1.  **Access Control (The "License"):** Scripts will be published on TradingView exclusively as **Invite-Only**. This prevents source code theft and enforces licensing via TradingView's platform DRM.
2.  **Platform Requirements:** A TradingView Premium account is required to publish invite-only scripts.
3.  **Sales & Automation:** 
    *   Subscriptions will be sold via a third-party platform (e.g., Whop, Gumroad, Patreon).
    *   Access granting/revocation will be fully automated via webhooks (e.g., Make.com, Zapier, or native integrations) connecting the payment processor to the TradingView API.
4.  **EULA:** A Terms of Service agreement at checkout will explicitly state that purchases grant a non-transferable, revocable license to *use* the indicator, with no intellectual property rights transferred.
