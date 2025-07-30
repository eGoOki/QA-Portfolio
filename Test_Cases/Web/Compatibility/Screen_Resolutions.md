# 🖥️ Screen Resolutions – Compatibility Test Cases

---

> ⚠️ **Note**: These test cases verify that the application layout adapts correctly to various screen sizes and resolutions.

---

## 📐 Screen Resolutions

### 🖥️ Desktop

- 2560×1440 (QHD)
- 1920×1080 (Full HD)
- 1366×768
- 1280×720

### 📱 Mobile

- 375×667 – iPhone SE (2nd Gen)
- 412×915 – mid-range Android (e.g. Pixel 6)
- unfolded: 812×1792 – Galaxy Z Fold 4/5/7 (approx)

---

## 📄 Table of Contents

- TC-SCR-101 – Layout on 2560×1440 (QHD)
- TC-SCR-102 – Layout on 1920×1080 (Full HD)
- TC-SCR-103 – Layout on 1366×768
- TC-SCR-104 – Layout on 1280×720
- TC-SCR-105 – Layout on 375×667 (iPhone SE)
- TC-SCR-106 – Layout on 412×915 (Pixel 6)
- TC-SCR-107 – Layout on 812×1792 (Galaxy Z Fold)

---

## 🖼️ TC-SCR-101 – Layout on 2560×1440 (QHD)

**Title:** Verify layout on QHD screen  
**Type:** Compatibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Screen resolution set to 2560×1440  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open homepage       | Layout scales proportionally |

**Postconditions:**  
No excessive whitespace

**Expected Result:**  
Design remains centered and readable

---

## 🧭 TC-SCR-102 – Layout on 1920×1080 (Full HD)

**Title:** Verify layout on Full HD screen  
**Type:** Compatibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Resolution set to 1920×1080  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open homepage       | Layout fills screen properly |

**Postconditions:**  
No overflow or clipping

**Expected Result:**  
Design scales to full HD

---

## 🧮 TC-SCR-103 – Layout on 1366×768

**Title:** Verify layout on legacy laptop screen  
**Type:** Compatibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Resolution set to 1366×768  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open dashboard      | Layout adjusts correctly     |

**Postconditions:**  
No horizontal scroll

**Expected Result:**  
Content fits within screen width

---

## 🧾 TC-SCR-104 – Layout on 1280×720

**Title:** Verify layout on small desktop screen  
**Type:** Compatibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Resolution set to 1280×720  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open site           | Layout remains usable        |

**Postconditions:**  
No broken elements

**Expected Result:**  
Design adapts gracefully

---

## 📱 TC-SCR-105 – Layout on 375×667 (iPhone SE)

**Title:** Verify layout on iPhone SE screen  
**Type:** Compatibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Mobile viewport active  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open site on iPhone SE | Layout stacks vertically |

**Postconditions:**  
Mobile experience is smooth

**Expected Result:**  
Responsive design adapts to small screen

---

## 📲 TC-SCR-106 – Layout on 412×915 (Pixel 6)

**Title:** Verify layout on mid-range Android screen  
**Type:** Compatibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Mobile viewport active  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open site on Pixel 6 | Layout is readable and responsive |

**Postconditions:**  
No layout issues

**Expected Result:**  
Design fits screen dimensions

---

## 📐 TC-SCR-107 – Layout on 812×1792 (Galaxy Z Fold – unfolded)

**Title:** Verify layout on unfolded foldable screen  
**Type:** Compatibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Foldable device in unfolded mode  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open site on Galaxy Z Fold | Layout spans full width |

**Postconditions:**  
No broken grid or stretched elements

**Expected Result:**  
Design adapts to large mobile viewport