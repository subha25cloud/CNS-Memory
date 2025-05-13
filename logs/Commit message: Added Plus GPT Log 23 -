
**PLUS GPT LOG 24: SMART STOCK UNIVERSE FILTER & DYNAMIC WATCHLIST SYSTEM**  
**Title:** Intelligent Filtering, Trade-Type Matching & Morning Auto-Scheduler  
**Log ID:** PlusGPTLog_24  
**Date:** 10 May 2025  
**Prepared by:** GPT-4 Turbo for Subhajit Saha

### SECTION A: PURPOSE
Create a dynamic stock selection layer that filters the tradeable universe daily based on logic, ML inputs, sentiment data, and user constraints. The goal is to:
- Match stocks with suitable trade types (intraday, swing, options, long-term)
- Boost trade confidence, eliminate noise
- Finish all filtering before market open (8:45–9:15 AM)

### SECTION B: CORE MODULE FUNCTION
- Filter stocks from full Indian market (~7000 stocks) into prime buckets:
  - Intraday trades  
  - Swing opportunities  
  - Options-ready setups  
  - Long-term undervalued stocks  

- Segment filters:
  - Large Cap (Top 500)  
  - Mid Cap (Next 500)  
  - Small Cap + IPOs  
  - NSE F&O list  

### SECTION C: CNS + ML FILTER CHAIN
**Filters applied in this order:**

1. **Static Filters:**
   - Volume > 10L  
   - Delivery % > 35%  
   - Sector strength  
   - Volatility Rank  

2. **Smart Filters (ML-controlled):**
   - ML1: Chart pattern scan  
   - ML2: Smart money flow  
   - ML3: Sentiment from news  
   - ML4: Price behavior risk correction  
   - ML5: Confidence scoring  

3. **Custom Strategy Filters:**
   - Strategy-specific preferences (e.g., no swing trades on earnings week)

4. **Final Scoring & Segmentation:**
   - Each stock scored 0–100 by ML5  
   - Routed to appropriate `/watchlist/` bucket

### SECTION D: STRATEGY-SPECIFIC EXAMPLES

strategy_name: Intraday_CPR_Volume
use_on: intraday
volume_min: 12L
volatility_zone: high
exclude_days: [Tuesday]

strategy_name: ValueBuy
use_on: long_term
pe_range: [0, 20]
pb_range: [0, 3.5]
exclude_if: overbought_zone

### SECTION E: SCHEDULED DAILY WORKFLOW
**Time: 8:45 AM – 9:15 AM**

1. CNS collects:
   - NSE stats, bulk/block data  
   - Pre-market movers  
   - Smart money + volume surge  
   - Sector strength and FIIs/DIIs  

2. ML filters apply per trade category

3. Sorted output saved into:

/watchlist/intraday.csv
/watchlist/swing.csv
/watchlist/options.csv
/watchlist/longterm.csv

### SECTION F: USER INTERACTION COMMANDS
- "Show intraday stocks for today."  
- "Why isn’t Tata Steel in swing list?"  
- "Force add Reliance to long-term filter."  
- "Show option-ready stocks only."

### SECTION G: ML RESPONSIBILITY SPLIT
| Trade Type  | ML Modules Involved        |
|-------------|-----------------------------|
| Intraday    | ML1, ML2, ML5               |
| Swing       | ML1, ML3, ML5               |
| Options/Fut.| ML2, ML4, ML5               |
| Long-Term   | ML2, ML3, ML4 (value logic) |

### SECTION H: FUTURE EXTENSIONS
- Weekly sector rotation tracking  
- User lock-ins (manual override list)  
- Filter backtesting engine  
- Auto alerts when a stock enters multiple lists  

**End of Log 24 – Smart Universe Filtering Logic**

