# 💥 Stress Test – Performance Test Cases

---

> ⚠️ **Note**: These test cases simulate extreme conditions to observe system behavior under stress.

---

## 📄 Table of Contents

- TC-STRESS-101 – Rapid page reloads
- TC-STRESS-102 – Bulk data entry in form
- TC-STRESS-103 – Multiple dashboard refreshes
- TC-STRESS-104 – Long session duration
- TC-STRESS-105 – Simultaneous file uploads

---

## 🔁 TC-STRESS-101 – Rapid page reloads

**Title:** Reload homepage repeatedly  
**Type:** Performance  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Homepage accessible  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Reload page 10x in 30 sec | No crash or slowdown   |

**Postconditions:**  
System remains stable

**Expected Result:**  
No memory leaks or performance drop

---

## 📥 TC-STRESS-102 – Bulk data entry in form

**Title:** Enter large payload in form fields  
**Type:** Performance  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Form allows long input  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Paste 10k+ characters | Form accepts or limits input |

**Postconditions:**  
No crash or freeze

**Expected Result:**  
System handles large input gracefully

---

## 🔄 TC-STRESS-103 – Multiple dashboard refreshes

**Title:** Refresh dashboard repeatedly  
**Type:** Performance  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Dashboard active  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Refresh dashboard 5x in 1 min | No rendering issues |

**Postconditions:**  
Widgets remain functional

**Expected Result:**  
Dashboard remains responsive

---

## ⏳ TC-STRESS-104 – Long session duration

**Title:** Keep session active for 2+ hours  
**Type:** Performance  
**Priority:** Low  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Session timeout disabled  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Stay logged in for 2 hours | Session remains stable |

**Postconditions:**  
No logout or memory issues

**Expected Result:**  
System handles prolonged usage

---

## 📤 TC-STRESS-105 – Simultaneous file uploads

**Title:** Upload multiple files at once  
**Type:** Performance  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Upload feature enabled  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Upload 3+ files simultaneously | All uploads succeed |

**Postconditions:**  
No server error

**Expected Result:**  
System handles parallel uploads