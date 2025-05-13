**PLUS GPT LOG 28: ROLLING STRADDLE VWAP STRATEGY (FRIDAY INTRADAY OPTIONS SELLING)**  
**Title:** Friday-Only VWAP-Based Rolling Straddle Strategy for Option Selling  
**Log ID:** PlusGPTLog_28  
**Date:** 11 May 2025  
**Prepared by:** GPT-4 Turbo for Subhajit Saha

### SECTION A: STRATEGY PURPOSE  
Low-risk, rule-based intraday option selling system designed for **Fridays**. Uses **rolling straddle premium** and **VWAP** to generate weekly returns of 0.5–2%, compounding to **24–30% annually**.

### SECTION B: STRATEGY SETUP

| Component         | Value/Logic |
|------------------|-------------|
| Timeframe         | 5-Minute    |
| Entry Day         | Friday only |
| Instrument        | Nifty Weekly Options |
| Indicators        | Rolling Straddle Premium, VWAP |
| Entry Type        | ATM Strangle (0.1 Delta CE + PE Sell + Hedge) |
| Hedge Type        | Buy OTM options (~2–3 premium) |
| Platform Needed   | Stock.in / Sensibull / Broker API |

### SECTION C: ENTRY CONDITIONS

**Standard Entry:**  
- ATM CE + PE straddle closes **below VWAP** on 5-min chart.  
- Enter strangle position with hedge.

**Gap Down Direct Entry:**  
- If open is already below VWAP, **enter at 9:21 AM**.

### SECTION D: STRIKE SELECTION

- Pick 0.1 delta CE + PE with **premium > ₹10–15**.  
- Hedge 300–500 points OTM with ₹2–3 premium.

### SECTION E: EXIT CONDITIONS

- **Exit 1: VWAP Breach:** If straddle closes **above VWAP**, exit fully.  
- **Exit 2: Target Profit:** 0.5% profit on capital = book.  
- **Exit 3: SL Hit:** Exit on 0.5% loss.

**Re-entry Logic:**  
- If re-closes below VWAP after VWAP breach, **re-enter** new strangle.

### SECTION F: BACKTEST DATA

- **Period:** Jan 2025 – May 2025  
- **Trades:** 14  
- **Win Rate:** 86%  
- **Avg Profit:** ₹5,877  
- **Avg Loss:** ₹5,167  
- **RR:** Slightly above 1:1  

### SECTION G: BOT & ML INTEGRATION

- **PulseBot:** Executes in Auto/Semi mode  
- **ML6:** Required for spoofing/VWAP accuracy  
- **ML5:** Ranks confidence  
- **ML1:** Not involved (no pattern logic needed)

### SECTION H: ADVANTAGES & LIMITATIONS

**Pros:**  
- No charts/patterns needed  
- Weekly passive income  
- Fully hedged  
- Simple execution  

**Cons:**  
- Friday-only  
- Needs precise LTP/VWAP feed  
- Misses trades on low volatility days  

### SECTION I: COST ESTIMATES

| Component                | Monthly Cost |
|-------------------------|--------------|
| Rolling Straddle Feed   | ₹500–800     |
| Option Chain Data       | ₹500–1,000   |
| Broker API              | ₹0–₹300      |

**Total Monthly:** ₹1,000–₹1,500  

### NEXT STEPS

- Build YAML template for CNS  
- Backtest via engine + ML6 guard  
- Load into PulseBot as **Friday-only module**

**End of Log 28 – Rolling Straddle VWAP Intraday Strategy**
