# Portfolio Hedging & Risk Management Analysis

A quantitative financial modeling project evaluating downside risk mitigation strategies for high-net-worth equity holdings using derivative instruments (Futures and Options) on the National Stock Exchange (NSE).

---

## Executive Summary

This repository presents a capstone project analysis on hedging a long equity spot portfolio valued at ₹16,80,000. The underlying holdings consist of large-cap equity positions in Ashok Leyland and Larsen & Toubro (L&T).

The project compares two primary derivative hedging methodologies:
1. **Futures Hedge (Short Futures):** Fully neutralizes directional market exposure by locking in payout values, eliminating downside risk while capping upside potential[cite: 2].
2. **Options Hedge (Protective Put):** Functions as portfolio downside insurance by capping maximum capital losses to the premium paid while preserving unlimited upside profit participation[cite: 2].

---

## Portfolio Composition

| Asset | Position Size | Entry Price (₹) | Contract Lot Size | Total Capital Invested (₹) |
| :--- | :---: | :---: | :---: | :---: |
| **Ashok Leyland** | 5,000 shares | ₹180.00 | 7,000 | ₹9,00,000 |
| **Larsen & Toubro (L&T)** | 300 shares | ₹2,600.00 | 300 | ₹7,80,000 |
| **Total Portfolio** | — | — | — | **₹16,80,000** |

---

## Hedging Strategy Execution

### 1. Short Futures Strategy
* **Ashok Leyland:** Sell 1 Futures Lot (7,000 shares) @ ₹182[cite: 2].
  * *Note:* Results in a slight over-hedge due to standardized NSE contract lot sizes (7,000 contract units vs. 5,000 spot shares held)[cite: 2].
* **Larsen & Toubro (L&T):** Sell 1 Futures Lot (300 shares) @ ₹2,620[cite: 2].
  * *Note:* Exact 1:1 match against underlying spot position[cite: 2].

### 2. Protective Put Strategy
* **Ashok Leyland:** Purchase 1 Put Option Lot (Strike $K = \text{₹}180$, Premium $P = \text{₹}4/\text{share}$, Total Cost = ₹28,000)[cite: 2].
* **Larsen & Toubro (L&T):** Purchase 1 Put Option Lot (Strike $K = \text{₹}2,600$, Premium $P = \text{₹}70/\text{share}$, Total Cost = ₹21,000)[cite: 2].

---

## Mathematical Formulations & Payoff Models

### Breakeven Formulation
For a Protective Put strategy, the breakeven spot price ($S_{BE}$) at expiration is defined as:

$$S_{BE} = K + P$$

Where:
* $K$ = Option Strike Price
* $P$ = Premium Paid per share

### Net Payoff Equations
* **Spot Position Payoff:** $\Pi_{\text{spot}} = S_T - S_0$
* **Put Option Payoff:** $\Pi_{\text{put}} = \max(K - S_T, 0) - P$
* **Combined Protective Put Net Payoff:**

$$\Pi_{\text{net}} = (S_T - S_0) + \max(K - S_T, 0) - P$$

---

## Risk & Payoff Metrics

| Asset | Strike Price ($K$) | Premium Cost | Breakeven Price ($S_{BE}$) | Max Downside Risk | Upside Potential |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Ashok Leyland** | ₹180 | ₹28,000 (₹4/sh) | **₹184.00** | ₹28,000 | Unlimited |
| **Larsen & Toubro (L&T)** | ₹2,600 | ₹21,000 (₹70/sh) | **₹2,670.00** | ₹21,000 | Unlimited |

### Scenario Analysis Matrix

#### 1. Ashok Leyland (5,000 shares @ ₹180 | Put Strike: ₹180 | Premium: ₹28,000)[cite: 2]
* **Bearish Scenario ($S_T = \text{₹}160$):** Spot Loss = -₹1,00,000 | Put Gain = +₹1,40,000 | **Net Result = +₹12,000 Profit** *(slight net profit driven by 7,000 contract lot over-hedge)*[cite: 2].
* **At-the-Money Scenario ($S_T = \text{₹}180$):** Spot Change = ₹0 | Put Gain = ₹0 | **Net Result = -₹28,000 Loss** *(capped at premium paid)*[cite: 2].
* **Bullish Scenario ($S_T = \text{₹}190$):** Spot Gain = +₹50,000 | Put Gain = ₹0 | **Net Result = +₹22,000 Profit**[cite: 2].

#### 2. Larsen & Toubro (300 shares @ ₹2,600 | Put Strike: ₹2,600 | Premium: ₹21,000)[cite: 2]
* **Bearish Scenario ($S_T = \text{₹}2,500$):** Spot Loss = -₹30,000 | Put Gain = +₹30,000 | **Net Result = -₹21,000 Loss** *(strictly capped at total premium)*[cite: 2].
* **At-the-Money Scenario ($S_T = \text{₹}2,600$):** Spot Change = ₹0 | Put Gain = ₹0 | **Net Result = -₹21,000 Loss**[cite: 2].
* **Bullish Scenario ($S_T = \text{₹}2,700$):** Spot Gain = +₹30,000 | Put Gain = ₹0 | **Net Result = +₹9,000 Profit**[cite: 2].

---

## Repository Structure

```text
├── Hedging_Calculations_MrA.xlsx   # Interactive financial model with payoff tables & sensitivity analysis
├── Intellipaat Capstone.pdf        # Detailed project write-up and analytical solution
├── payoff diagram.pdf               # Payoff curve visual models (Futures vs. Protective Put)
└── README.md                       # Project documentation
