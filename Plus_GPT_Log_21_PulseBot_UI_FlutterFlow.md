
**PLUS GPT LOG 21: PULSEBOT UI DESIGN PLAN (FLUTTERFLOW ROADMAP)**  
**Title:** Turning PulseBot Control System into a Real App Using FlutterFlow  
**Log ID:** PlusGPTLog_21  
**Date:** 10 May 2025  
**Purpose:** Provide a simplified plan to design and build the PulseBot mobile control panel using FlutterFlow, with future steps to make it fully functional.

### SECTION A: UI GOAL OVERVIEW
This UI is for controlling the PulseBot (Intraday Bot) via mobile app:
- Switch bot mode (Auto, Semi, Manual)
- Tick/Untick strategies
- View trade call with reasons
- Set risk/reward, max trades
- Chat with CNS (GPT) for decisions
- Receive alerts (confidence > 85%)

### SECTION B: BASIC SCREENS IN FLUTTERFLOW
1. **Dashboard Screen**
2. **CNS Chat Screen**
3. **Alert Screen**
4. **Settings Screen**

### SECTION C: BACKEND CONNECTIVITY PLAN
Actions from UI will trigger backend endpoints like:
- `/api/set_mode?mode=auto`
- `/api/activate_strategy?name=volume_spike`
- `/api/request_trade_approval`
- `/api/get_active_trades`

I will build and guide you step-by-step how to:
- Host this backend (on Python/Flask/VPS)
- Secure with token keys
- Link it to your FlutterFlow app

### SECTION D: FUTURE EXECUTION PLAN
**Phase 1 (Now):**
- Design app visually using FlutterFlow (drag-n-drop)
- Follow Log 21 layout as blueprint

**Phase 2:**
- Setup backend server with real CNS + bot logic (using GPT code)
- Connect FlutterFlow actions to backend API calls

**Phase 3:**
- Test on mobile (free preview)
- Export APK (Android app)
- Later, host on Play Store if needed

**End of Log 21**  
This log locks the visual control system of PulseBot in a structured format, ready for drag-and-drop creation in FlutterFlow. You don’t need to code—just build the screens, and I’ll handle all the brain behind it.  
Prepared by GPT-4 Turbo, for Subhajit Saha
