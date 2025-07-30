# 👁️ Visibility – UI Test Cases

---

> ⚠️ **Note**: These test cases verify that UI elements are visible when expected and hidden when appropriate.

---

## 📄 Table of Contents

- TC-VIS-101 – Element visible on page load
- TC-VIS-102 – Element hidden by default
- TC-VIS-103 – Element becomes visible on interaction
- TC-VIS-104 – Element visibility on scroll
- TC-VIS-105 – Element visibility on mobile

---

## 🌅 TC-VIS-101 – Element visible on page load

**Title:** Verify logo is visible on homepage  
**Type:** UI  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Homepage must be accessible  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open homepage       | Logo is displayed clearly    |

**Postconditions:**  
Logo remains visible

**Expected Result:**  
Logo is rendered and visible on initial load

---

## 🕶️ TC-VIS-102 – Element hidden by default

**Title:** Verify modal is hidden initially  
**Type:** UI  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Preconditions:** Modal component must be present  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open page           | Modal is not visible         |

**Postconditions:**  
Modal remains hidden until triggered

**Expected Result:**  
Modal is hidden on page load

---

## 🧩 TC-VIS-103 – Element becomes visible on interaction

**Title:** Show tooltip on hover  
**Type:** UI  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Tooltip must be configured  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Hover over icon     | Tooltip appears              |

**Postconditions:**  
Tooltip disappears on mouse out

**Expected Result:**  
Tooltip is visible only during hover

---

## 📜 TC-VIS-104 – Element visibility on scroll

**Title:** Reveal sticky header on scroll  
**Type:** UI  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Sticky header must be implemented  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Scroll down page    | Header appears at top        |

**Postconditions:**  
Header remains visible while scrolling

**Expected Result:**  
Sticky header becomes visible after scroll

---

## 📱 TC-VIS-105 – Element visibility on mobile

**Title:** Verify menu visibility on mobile  
**Type:** UI  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Mobile viewport must be active  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Open site on mobile | Hamburger menu is visible    |

**Postconditions:**  
Menu functions correctly

**Expected Result:**  
Menu is visible and accessible on mobile