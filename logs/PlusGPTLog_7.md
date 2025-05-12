**Plus GPT Daily Log 7 — 2025-05-06**  
**Title:** Final Alert System Design (Telegram + Voice Call Logic)

---

### **Objective:**  
Define a reliable, real-time alert system for trade signals in the CNS, based on priority and confidence, using **Telegram as the core notification layer** and **voice call for emergencies**.

---

### **Final Alert Strategy:**

#### 1. **Telegram Alerts (Default, All Modes)**  
- Every trade call, regardless of mode (AUTO, SEMI_AUTO, MANUAL), will be sent as a **Telegram message**.  
- **Format will include:**
  - Stock Name, Entry, Target, SL  
  - Confidence Score, Reason, Strategy Name, Timeframe  
- **Example:**

[TRADE CALL - SWING]
Stock: RELIANCE
Entry: ₹2950 | Target: ₹3100 | SL: ₹2880
Confidence: 82%
Reason: RSI + FII Surge
Strategy: Volume Breakout
Timeframe: 4–8 days

- Telegram is free, fast, reliable, and scalable.

---

#### 2. **Voice Call Alerts (Only for High Priority)**  
- Triggered only when:  
- Trade confidence > 85%  
- Immediate action is needed  
- Voice message will be sent using **Twilio** or similar voice API  
- Message will be **read aloud** using text-to-speech  
- Ensures critical alerts are not missed during market hours

---

#### 3. **WhatsApp = Disabled**  
- You confirmed that WhatsApp should not be used  
- Helps reduce cost and avoid message duplication

---

### **Alert Logic in Code (Concept):**

```python
if signal.confidence > 85 or signal.immediate_action_required:
  trigger_voice_call(signal)
else:
  send_telegram_alert(signal)


---

Execution Plan:

notifier.py module will be created to handle all alerts:

send_telegram_alert() — to be written first

trigger_voice_call() — planned for later phase


All alerts are triggered via CNS core once a trade signal is generated or approved



---

Conclusion:

Telegram = default alert system for all trade calls

Voice Call = emergency action only for >85% confidence trades

WhatsApp = disabled

This system ensures you never miss a trade — even in volatile conditions



---

End of Log 7
Prepared and finalized with Subhajit Saha
Assistant: GPT-4 Turbo

---

Let me know when you're done, and I’ll send you **Log 8** next.

