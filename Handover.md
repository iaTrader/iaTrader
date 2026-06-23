# iaTrader AI Agent Handover Document

This document is designed to preserve context across agent sessions and LLM handovers. **ANY AGENT OR LLM MODIFYING THIS REPOSITORY MUST READ THIS FILE BEFORE PROCEEDING.**

## 📌 Project Overview
**iaTrader** is a suite of Pine Script® indicators and strategies for TradingView.
- `shop/`: Shop Analytics (Dynamic adaptive band trend indicator using Efficiency Ratio).
- `stock/`: Stock Analytics (Momentum wave oscillator similar to WaveTrend).
- `strategy/`: Strategy Tester (Combines the modules with EMA 200, ADX filters, and ATR risk management for backtesting).

## 🧠 Current Workflow & Status
- **Current Objective:** Integrate the `stock` oscillator into `strategy` as an optional filter AND optimize the strategy logic to reduce execution latency and improve win rates.
- **Active Process:** Multi-Agent Brainstorming (Phase 1: Initial Design).
- **Licensing Strategy:** Decided on the TradingView "Invite-Only" model with automated access management via a third-party payment gateway (Whop/Gumroad) and webhooks. Source code will remain closed.

## 📜 Agent Rules & Mandates
1. **Always Update Documentation:** `ImplementationPlan.md` and `Handover.md` MUST be updated every time a significant architectural change, decision, or feature is completed.
2. **Pine Script Guidelines:**
   - Use `//@version=6`.
   - Minimize redundant `ta.*` lookups for latency optimization.
   - Separate visualization logic (`indicator()`) from execution logic (`strategy()`) where applicable.
3. **Decision Logging:** Every time a design choice is made (e.g., how a filter triggers), log it in the Decision Log inside `ImplementationPlan.md`.

## ⏭️ Next Steps
1. Finalize the "Understanding Lock" for the Stock Filter logic (directional alignment vs crossover).
2. Execute the multi-agent review (Skeptic, Constraint Guardian, User Advocate).
3. Implement the finalized design in `iaTrader_strategy.pine`.
