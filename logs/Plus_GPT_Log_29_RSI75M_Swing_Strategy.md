**PLUS GPT LOG 29: RSI75M STRATEGY**  
**Title:** RSI-Based Swing Trading Plug-In Strategy for Futures  
**Log ID:** PlusGPTLog_29  
**Date:** 10 May 2025  
**Prepared by:** GPT-4 Turbo for Subhajit Saha

### SECTION A: PURPOSE  
Integrate a rule-based RSI strategy on a **75-minute timeframe** into CNS to support **swing trading bots** (especially PositionBot) on Nifty/BankNifty futures for positional trades lasting 1–5 days.

### SECTION B: STRATEGY OVERVIEW

- **Timeframe:** 75-minute  
- **Instrument:** Index Futures (far-month preferred)  
- **Hedging:** ATM Options from current month  
- **Indicators:**
  - RSI
  - Entry: RSI closes above 50
  - Exit: RSI >75–80 (profit) or <50 (SL)

**Entry (Long):**  
- RSI > 50  
- Buy far-month futures  
- Hedge with ATM Put

**Exit (Long):**  
- RSI > 75–80 (profit)  
- RSI < 50 (SL)

**Entry (Short):**  
- RSI < 50  
- Sell far-month futures  
- Hedge with ATM Call

**Exit (Short):**  
- RSI < 20–25 (profit)  
- RSI > 50 (SL)

### SECTION C: CNS AND BOT INTEGRATION

- **Assigned Bot:** PositionBot  
- **Mode:** Semi-Auto (user approves futures trade)  
- CNS + ML combo handles signal validation

**ML Roles:**
| ML | Role |
|----|------|
| ML1 | Detect RSI, trend, candle close |
| ML5 | Confidence scoring |
| ML6 | Trap/spoof detection pre-entry |

### SECTION D: STRATEGY BEHAVIOR & LIMITS

- Only for swing cycles  
- Runs **Fridays or strong-trend days only**  
- Disabled on high-risk event days

### SECTION E: TRAINING DATASET & LEARNING

- ML1: 1–5 year RSI pattern learning  
- ML5: RSI signal success rate calibration  
- ML6: Traps/fakeouts detection using LOB/option data  
- Weekly retraining

### SECTION F: COST & FEED REQUIREMENTS

- Uses Dhan/Kite data  
- No extra feed required  
- LOB optional only for ML6 use

### Final Note  
This strategy is a **slow, trend-confirming plug-in** for PositionBot. Pairs well with fast bots like PulseBot and enhances diversity in CNS logic.

**End of Log 29**
