# Portfolio Hedging & Risk Management Analysis

A comprehensive financial analysis and modeling project evaluating portfolio risk mitigation strategies for High Net Worth Individuals (HNIs). This repository models hedging strategies for equity spot holdings using **Futures Contracts** and **Protective Put Options** on Indian equity markets (NSE).

---

## 📌 Executive Summary

This project analyzes a long portfolio position holding two major stocks—**Ashok Leyland** and **Larsen & Toubro (L&T)**—and evaluates downside risk protection using derivative instruments:

1. **Futures Hedge (Short Futures):** Lock in positions to fully eliminate market directional risk (zero net exposure / locked payout).
2. **Options Hedge (Protective Put):** Establish a floor on downside risk while retaining unlimited upside profit potential, subject to premium costs.

---

## 📊 Portfolio Overview

| Asset | Holding Units | Spot/Purchase Price | Total Portfolio Exposure |
| :--- | :--- | :--- | :--- |
| **Ashok Leyland** | 5,000 shares | ₹180.00 | ₹9,00,000 |
| **L&T** | 300 shares | ₹2,600.00 | ₹7,80,000 |
| **Total Portfolio Value** | — | — | **₹16,80,000** |

---

## ⚙️ Hedging Parameters & Execution

### 1. Futures Hedging Strategy
* **Ashok Leyland:** Sold 1 Futures Lot (Lot Size: 7,000 @ ₹182). *Note: Provides a slight over-hedge against the 5,000 spot units.*
* **L&T:** Sold 1 Futures Lot (Lot Size: 300 @ ₹2,620). *Perfect 1:1 hedge against spot holdings.*

### 2. Options Hedging Strategy (Protective Put)
* **Ashok Leyland:** Purchased 1 Put Option Lot (Strike: ₹180, Premium: ₹4/share, Total Premium: ₹28,000).
* **L&T:** Purchased 1 Put Option Lot (Strike: ₹2,600, Premium: ₹70/share, Total Premium: ₹21,000).

---

## 📈 Payoff & Breakeven Metrics
