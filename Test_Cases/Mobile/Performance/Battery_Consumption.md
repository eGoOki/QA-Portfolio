✅ Mobile Performance – Battery Consumption Test Cases

⚠️ Note: These test cases are examples. Actual implementation may vary based on project structure, monitoring tools, and device lab setup.

---

🎯 Scope  
These mobile test cases cover:  
- 🔋 Battery impact of foreground and background usage  
- 📺 Media playback energy drain  
- 🔄 Data sync and wake lock behavior  
- 🔕 Idle state energy validation  
- 🧮 Cross-device comparison of power profiles

⛔ Out of Scope  
- CPU/memory load – see [Load_Test.md](./Load_Test.md)  
- Crash scenarios – part of Stability test suite  
- Thermal throttling – covered under Device_Stress.md

---

🧪 Testing Tips

- Use native battery profiling tools: Battery Historian (Android), Energy Gauge (iOS Instruments)  
- Avoid testing while device is charging  
- Repeat on low-end and flagship devices for comparison  
- Include logs of background events and wake locks

---

🧪 Test Cases

---

🌙 TC-PERF-BATT-001 – Idle battery impact  
**Title:** App left idle for extended duration  
**Section:** Battery_Idle_State  
**Template:** Steps + Results  
**Type:** Performance  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 30m  
**References:** REQ-PERF-BATT-001  
**Preconditions:** App installed and logged in; screen off; not charging  
**Steps and Results:**  
| Step | Action | Expected Result |  
|------|--------|------------------|  
| 1 | Record battery % (initial) | Battery logged in test report |  
| 2 | Leave app idle for 30 minutes | App remains in background; no activity spikes |  
| 3 | Record battery % (final) | ≤ 2% battery drop |  

**Postconditions:** App remains inactive  
**General Expected Result:** App shows minimal idle battery usage

---

📺 TC-PERF-BATT-002 – Video playback usage  
**Title:** Power drain during video stream  
**Section:** Media_Consumption  
**Template:** Steps + Results  
**Type:** Performance  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 20m  
**References:** REQ-PERF-BATT-002  
**Preconditions:** Stable internet connection; video feature available  
**Steps and Results:**  
| Step | Action | Expected Result |  
|------|--------|------------------|  
| 1 | Record battery before test | Logged to report |  
| 2 | Play 20-minute HD video in-app | Playback proceeds smoothly |  
| 3 | Record battery after test | ≤ 8% drop for mid-tier device |  

**Postconditions:** Video stops; app remains open  
**General Expected Result:** Video playback efficiency remains acceptable

---

🔄 TC-PERF-BATT-003 – Background sync impact  
**Title:** Battery usage during background data sync  
**Section:** Background_Services  
**Template:** Steps + Results  
**Type:** Performance  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 1h  
**References:** REQ-PERF-BATT-003  
**Preconditions:** App logged in; sync scheduled; device idle  
**Steps and Results:**  
| Step | Action | Expected Result |  
|------|--------|------------------|  
| 1 | Trigger sync task in-app | Sync begins in background |  
| 2 | Minimize app and lock screen | App enters idle state |  
| 3 | Record battery after 1 hour | ≤ 5% drop; no unauthorized wake locks |  

**Postconditions:** Data successfully synced  
**General Expected Result:** Sync handled efficiently without power spikes

---
