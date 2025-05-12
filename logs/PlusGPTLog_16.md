**PLUS GPT LOG 16: MOBILE UI CONTROL & COMMAND LAYER FOR CNS SYSTEM**  
**Title:** Backend Command Structure for Mobile Interaction  
**Log ID:** PlusGPTLog_16  
**Date:** 10 May 2025  
**Prepared by:** GPT-4 Turbo for Subhajit Saha  

---

### **SECTION A: PURPOSE**

Define how the CNS receives and applies user instructions from a mobile UI or chat interface — without needing code edits. Functions include:
- Mode switching (Manual, Semi-Auto, Auto)  
- Strategy toggling  
- Risk setting adjustment  
- Code pasting  
- Alert reception & confirmations  

---

### **SECTION B: MOBILE COMMAND STRUCTURE**

#### **1. Modes Toggle**
**Command:** `#mode auto`  
Internally: CNS updates bot status, PulseBot enters auto-execution.

#### **2. Strategy Management**
```
#add_strategy CPR_breakout
#deactivate RSI_surge
#show_strategies
```

#### **3. Risk Control**
```
#set max_trades 2
#change_sl_type ATR
#set_confidence_threshold 75
```

#### **4. Manual Switch**
```
#manual_control enable
```

---

### **SECTION C: GPT NATURAL LANGUAGE MAPPING**

Casual inputs like:  
“Hey PulseBot, go semi-auto today.”  
→ GPT maps to:
```
#mode semi_auto
```

Or:  
“Change CPR stoploss to 1.5x ATR.”  
→ GPT maps to:
```
#edit_strategy CPR -> stop_loss = 1.5x_ATR
```

---

### **SECTION D: UI TOGGLE BEHAVIOR (TO DESIGN LATER)**

- Mode: 3-button switch  
- Strategies: checkbox list  
- Risk: toggle blocks  

All changes emit backend command like:  
```
#toggle_strategy RSI_reversal off
```

---

### **SECTION E: CNS RESPONSE BEHAVIOR**

Each action:  
- Logged to `/ui_control_log/`  
- CNS validates logic  
- Sends warnings when logic breaks (e.g., no active strategy)  
- Suggests fixes or alternate strategies

---

### **SECTION F: ALERT HANDLING SYSTEM**

For trades >85% confidence:  
- App notification  
- Mobile alert box  
- Voice call trigger (if enabled)

---

### **SECTION G: STRATEGY CODE INPUT**

Paste full code or YAML using:
```
#load_custom_strategy
[pasted content]
```

System auto-validates and activates if safe.

---

### **SECTION H: FUTURE INTEGRATION**

- Telegram & App UI sync  
- Multi-language NLP  
- Dedicated UI/UX planning log to follow  

---

**End of Log 16**  
This log finalizes the mobile command layer that lets CNS think like a trader and obey like a servant — no coding needed.  
Finalized by Subhajit Saha & GPT-4 Turbo
