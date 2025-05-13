
**Plus GPT Log 23 – Intraday Scalping Strategy (JMA + ADX Framework)**  
**Tag**: Intraday Bot, Strategy, ML-enhanced Execution  
**Status**: Final

### 1. Strategy Concept
This scalping strategy focuses on high-precision, fast-trade execution using a triple moving average system combined with ADX-based trend filtering. Designed for volatile, liquid products (Bank Nifty, Crude, Silver, Fin Nifty), the system offers entry/exit clarity and adaptable psychology fit for AI-based bots.

### 2. Timeframe Discipline
| Trader Type | Candle TF   | MA Length Guide | Use For              |
|-------------|-------------|------------------|----------------------|
| Scalper     | 30s – 5m    | MA 12–20         | Ultra-short moves    |
| Intraday    | 15m – 30m   | MA 20–50         | Session trend bias   |
| Swing       | 1hr – 4hr   | MA 50–100        | Multi-day momentum   |
| Positional  | Daily–Weekly| MA 100–250       | Macro trend capture  |

ML should enforce timeframe consistency: bots must only operate inside their allocated TFs.

### 3. Core Indicators
- **JMA (Jurik MA)** – Fastest (leading)
- **EMA** – Medium speed
- **SMA** – Slowest (lagging)
- **ADX (Average Directional Index)** – Trend strength filter

### 4. Trade Setup Rules
**Buy Signal:**
- JMA > EMA > SMA  
- ADX > 25  
- Entry: Breakout of candle that meets above condition

**Sell Signal:**
- JMA < EMA < SMA  
- ADX > 25  
- Entry: Breakdown of candle that meets above condition

### 5. Exit Logic
- Use **Heikin Ashi candles** for trailing stop-loss  
- Exit when 2 opposite Heikin Ashi candles form and **high/low is breached**  
- Alternatively, target 1.0–1.5 RR and book 60–70% capital; trail the rest

### 6. Psychology + Behavior Rules (ML Use)
- FOMC behavior modeling: switching time frames during live trade = weak logic  
- ML penalizes strategies with excessive reactivity  
- Score psychological fitness based on:
  - Entry/exit discipline  
  - Matching time frame with trading style  
  - Loss tolerance and overreaction  

### 7. Backtesting & Training Requirements
- Minimum 300–500 trades should be tested  
- Data analyzed manually/semi-automatically to understand:
  - Risk/Reward distribution  
  - Drawdown sequences  
  - Strategy fatigue  

### 8. Asset Selection Criteria
Only run this scalping model on:
- Highly **liquid** assets (Index futures, MCX metals)
- **Volatile** assets (Bank Nifty > Nifty, Silver > Gold, Crude Oil)
- Avoid flat, range-bound, or illiquid instruments

### 9. Integration into CNS System
- This strategy becomes a **plug-in module for Intraday Bot**
- CNS will decide activation based on:
  - Volatility readings  
  - ADX filter match  
  - Liquidity check  
  - Risk profile match  
- ML layer ranks this strategy in live run alongside other intraday logics

### Plus GPT Log Naming Convention Note:
This and all future logs will carry the **"Plus GPT Log #"** naming format to separate the new-gen system logs from legacy notes or manually maintained logs.

**Next Steps:** Prepare code structure for this strategy or integrate into Bot Builder pipeline.
