**PLUS GPT LOG 19: BEHAVIORAL BLUEPRINT FOR INTRADAY BOT SYSTEM**  
**Title:** PulseBot IntraDay – Internal & External Behavioral Design Blueprint  
**Log ID:** PlusGPTLog_19  
**Date:** 9 May 2025  

---

### **SECTION A: BOT PHILOSOPHY & VISION**
PulseBot is not just a tool — it acts like a logical, disciplined trader:
- Thinks before acting  
- Responds to time, news, sentiment, volatility  
- Prioritizes capital safety  
- Avoids blind triggers or overconfidence

---

### **SECTION B: EXECUTION ENVIRONMENT**

#### **1. Command Input**
- CNS is the only source of authority  
- User can override via chat  
- Strategy rules and risk model sent with command  

#### **2. Supported Modes**
- Manual  
- Semi-Auto  
- Full Auto *(recommended)*  

#### **3. Execution Engine**
Trade is only executed when:
- Time condition is valid  
- Strategy logic passes  
- CNS + ML modules approve it  

---

### **SECTION C: STRATEGY-SCOPED RULE LAYER**
Each strategy holds its **own internal rule config**:

Example (3PM Breakout):
```yaml
rules:
  active_days: ["Monday", "Wednesday", "Friday"]
  avoid_days: ["Thursday"]
  entry_time: "15:00"
  exit_by: "15:18"
  confidence_score: ">70"
  volume_required: true
```

---

### **SECTION D: CNS-LEVEL GLOBAL BOT RULES**

- Must have a stop loss  
- Max 3 trades per day  
- No trades below 60% confidence  
- Exit before 3:15 PM unless overridden  

---

### **SECTION E: SMART FILTER LAYER**

- Avoid low-volume stocks  
- Avoid trades on news spikes  
- Use ML3 (sentiment) & ML2 (smart money flow)  
- Strategy-based day filters (e.g., avoid Tuesday)

---

### **SECTION F: CNS–ML FLOWCHAIN**

1. Bot scans assigned stocks  
2. Strategy time/rules validated  
3. ML1 validates chart setup  
4. ML2 confirms smart money movement  
5. ML3 confirms sentiment  
6. ML5 returns confidence  
7. CNS decides  
8. Bot executes and logs

---

### **SECTION G: USER CONTROLS**

User can:
- Switch modes  
- Turn on/off strategies  
- Paste new logic  
- Chat with GPT to modify config  
- View logs or performance summaries  

---

### **SECTION H: ADAPTIVE LEARNING**

- All trades saved in `/bot_logs/`  
- ML models retrain from outcomes  
- CNS monitors strategy performance  
- Failing strategies are paused or re-weighted  
- Daily summaries can be sent to user

---

### **SECTION I: ADDED STRATEGY – OI + PRE-MARKET + SECTOR LOGIC**

**Logic Summary:**
- Wake up 9:00 AM  
- Focus on stocks with >2% pre-market move  
- Confirm if sector is dominant  
- At 9:30 AM, check OI > 7%  
- If yes → trade setup = VALID

**Strategy ID:** `S_INTRADAY_OI_PREMARKET_COMBO`

**Custom Rule Snippet:**
```yaml
rules:
  entry_window: "09:30–10:00"
  min_oi_spike: ">7%"
  premarket_movement: ">2%"
  sector_confirmation: true
  skip_trading_before: "09:30"
  allowed_days: ["Monday", "Tuesday", "Wednesday", "Friday"]
  avoid_days: ["Thursday"]
```

---

**End of Log 19**  
This blueprint defines PulseBot’s mental framework: rules, logic, boundaries, and behavior.  
Finalized by Subhajit Saha & GPT-4 Turbo
