# 📊 Load Test – Performance Test Cases

---

> ⚠️ **Note**: These test cases simulate typical user load to evaluate system responsiveness and stability.

---

## 📄 Table of Contents

- TC-LOAD-101 – Homepage load time under normal conditions
- TC-LOAD-102 – Concurrent login sessions
- TC-LOAD-103 – Search query under moderate traffic
- TC-LOAD-104 – Dashboard rendering with sample data
- TC-LOAD-105 – Form submission with multiple users

---

## 🏠 TC-LOAD-101 – Homepage load time under normal conditions

**Title:** Measure homepage load time  
**Type:** Performance  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Network stable, cache cleared  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open homepage       | Page loads within 2 seconds  |

**Postconditions:**  
No visual delays

**Expected Result:**  
Homepage loads promptly

---

## 👥 TC-LOAD-102 – Concurrent login sessions

**Title:** Simulate multiple users logging in  
**Type:** Performance  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Multiple browser instances or devices  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Login from 3+ sessions | All logins succeed quickly |

**Postconditions:**  
No session conflicts

**Expected Result:**  
System handles concurrent logins smoothly

---

## 🔍 TC-LOAD-103 – Search query under moderate traffic

**Title:** Execute search during simulated traffic  
**Type:** Performance  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Multiple tabs or users active  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Perform search query | Results appear within 3 sec |

**Postconditions:**  
No timeout or crash

**Expected Result:**  
Search remains responsive

---

## 📊 TC-LOAD-104 – Dashboard rendering with sample data

**Title:** Load dashboard with populated widgets  
**Type:** Performance  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Dashboard contains sample data  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open dashboard      | Widgets render within 2 sec  |

**Postconditions:**  
No layout lag

**Expected Result:**  
Dashboard loads efficiently

---

## 📝 TC-LOAD-105 – Form submission with multiple users

**Title:** Submit form from multiple sessions  
**Type:** Performance  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Form accessible to all users  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Submit form from 3+ tabs | All submissions succeed |

**Postconditions:**  
No duplicate or lost data

**Expected Result:**  
System handles simultaneous submissions