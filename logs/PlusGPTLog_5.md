**Plus GPT Daily Log 5 — 2025-05-06**  
**Title:** Real Code Structure Blueprint (To Be Implemented in Google Colab, Later Synced to Replit/VPS)

---

### **Objective:**  
Lay the groundwork for building the real Python code structure for CNS + Bots with mode-switch logic, ready to run on Google Colab.

---

### **Folder Structure Plan:**

    /cns_project/
    ├── cns_core.py               # Main brain (mode logic, task distribution)
    ├── bot_intraday.py           # Bot 1 logic (Auto-capable)
    ├── bot_swing.py              # Bot 2 logic (Signal generator)
    ├── bot_options.py            # Bot 3 logic (Semi-auto / manual)
    ├── dhan_api.py               # Handles Dhan trade execution securely
    ├── notifier.py               # Telegram / Voice notification system
    ├── modes_config.json         # Stores mode for each bot (AUTO, SEMI_AUTO, MANUAL)
    ├── logs/                     # Stores trade calls, history, feedback
    └── run.py                    # Main entry point to execute the CNS system

---

### **Planned Code Modules:**

- `modes_config.json`: Stores execution mode state per bot (e.g., AUTO, SEMI_AUTO, MANUAL)  
- `cns_core.py`: Core logic to interpret trade signals, route actions based on bot mode  
- `notifier.py`: Notification handler (Telegram, voice alerts)  
- Each bot file (e.g., `bot_intraday.py`) handles scanning + signal generation for its strategy  
- `run.py`: Unified launcher to trigger CNS workflow from start to finish  

---

### **Execution Environment:**

- **Development & testing**: Google Colab  
- **Final runtime + storage**: Replit or self-hosted VPS (not Google Drive)  
- **File sync strategy**: Handled later using GitHub or direct API push to cloud host  

---

### **Next Steps:**

- Code writing begins inside Colab using `.ipynb` cells  
- Logs, mode states, and trade calls will be stored for sync to permanent server  
- Telegram will be used for default alerts  
- Voice call trigger will be integrated into `notifier.py` in later stages  

---

**End of Log 5**
