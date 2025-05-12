**Plus GPT Log 14 – Intraday Bot Core Blueprint**  
**Tag:** Intraday Bot, CNS-Bot Communication, ML Integration, Modular Design  
**Status:** Final  

---

### **1. Core Objective**
This log defines the **modular architecture** and **communication pipeline** of the Intraday Bot. It is designed as a plug-and-play unit in the CNS system, supporting strategy injection, ML filters, and logging.

---

### **2. Bot Role in the CNS Ecosystem**
- Executes tactical trades based on 1m–15m TFs  
- Operates under CNS control  
- Logs every decision, success, or failure  
- Supports real-time strategy activation/deactivation

---

### **3. Modular Design (Plug-n-Play Framework)**

| Layer            | Functionality Description                                          |
|------------------|---------------------------------------------------------------------|
| Entry Logic      | Detects signal + triggers trade                                     |
| Exit Logic       | Books profit or trails per logic                                    |
| ML Filter        | Filters low-quality signals (optional)                              |
| Rule Engine      | Applies time, volatility, capital constraints                       |
| Alert Layer      | Sends trade alerts (Telegram/Voice)                                 |
| Logging Layer    | Stores triggers, actions, errors                                    |
| Strategy Library | Holds all pluggable strategies as `.py` or `.yaml`                  |

---

### **4. Supported Strategy Types (Sample Table)**

| Strategy Name             | Type        | ML Enabled | Coding Format         |
|---------------------------|-------------|------------|------------------------|
| Breakout + Pullback       | Momentum    | Yes        | Template: Yes         |
| RSI + MACD Reversal       | Mean Revert | Yes        | Template: Yes         |
| Opening Range             | Volatility  | No         | Built-in              |
| VWAP Bounce               | Liquidity   | Yes        | User patchable        |
| 3PM Options Scalping      | Precision   | Yes        | Pre-Coded (Log 23)    |
| Candle Logic v1           | Price Action| No         | DIY (copy-paste)      |

---

### **5. Strategy Snippet Template**
```python
if price > resistance and volume > avg_volume_5min:
    trigger_buy()
    stop_loss = support_level
    target = resistance + (resistance - support_level)
```

---

### **6. CNS–Bot Communication Protocol**
CNS sends a task packet:
```json
{
  "bot": "intraday",
  "task": "scan_and_trade",
  "strategy": "breakout_v1",
  "capital": 25000,
  "confidence_required": 65
}
```

Bot responds with execution packet:
```json
{
  "status": "trade_executed",
  "symbol": "BANKNIFTY",
  "entry": 49720,
  "exit": 49860,
  "confidence": 71,
  "r_r": 1.2
}
```

---

### **7. ML + Bot Synergy**
- ML1–ML5 validate pattern, smart money, sentiment  
- If confidence fails, bot skips unless CNS overrides  
- High confidence triggers voice alert

---

### **8. Bot Logging Format**
| Field         | Example     |
|---------------|-------------|
| Strategy      | breakout_v1 |
| Symbol        | BANKNIFTY   |
| Entry Time    | 09:21       |
| Entry Price   | 49720       |
| Exit Price    | 49860       |
| Result        | Profit      |
| Confidence    | 71%         |
| Exit Reason   | Target Hit  |

---

### **9. Strategy Additions & Updates**
Future strategies can be added via:
- User paste
- GPT-generated logic
- UI patch  
CNS activates it after validation.

---

**Next Step:**  
Begin coding strategy files and wire bot → CNS communication → ML filter port.

---

**End of Log 14**  
Approved by Subhajit Saha  
Documented by GPT-4 Turbo
