# 🧩 ARIA Roles – Accessibility Test Cases

---

> ⚠️ **Note**: These test cases verify correct usage of ARIA roles and attributes to enhance accessibility.

---

## 📄 Table of Contents

- TC-ARIA-101 – Role="button" on custom element
- TC-ARIA-102 – ARIA-label for icon-only buttons
- TC-ARIA-103 – ARIA-live region for dynamic content
- TC-ARIA-104 – Role="dialog" for modal windows
- TC-ARIA-105 – ARIA-expanded for collapsible sections

---

## 🔘 TC-ARIA-101 – Role="button" on custom element

**Title:** Verify role="button" on non-native button  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Custom clickable element present  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Inspect element     | `role="button"` is defined   |

**Postconditions:**  
Element behaves like a button

**Expected Result:**  
Screen reader announces it as a button

---

## 🏷️ TC-ARIA-102 – ARIA-label for icon-only buttons

**Title:** Verify ARIA-label on icon-only buttons  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Icon-only buttons present  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Inspect button markup | `aria-label` is present   |

**Postconditions:**  
Button purpose is clear to screen reader

**Expected Result:**  
Label describes button function

---

## 📢 TC-ARIA-103 – ARIA-live region for dynamic content

**Title:** Verify ARIA-live for real-time updates  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Page updates content dynamically  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Inspect container   | `aria-live="polite"` or `assertive` present |

**Postconditions:**  
Updates announced by screen reader

**Expected Result:**  
Live content is accessible

---

## 🗨️ TC-ARIA-104 – Role="dialog" for modal windows

**Title:** Verify role="dialog" on modal  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Modal component present  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Inspect modal markup | `role="dialog"` is defined |

**Postconditions:**  
Modal is announced properly

**Expected Result:**  
Screen reader identifies dialog context

---

## 📂 TC-ARIA-105 – ARIA-expanded for collapsible sections

**Title:** Verify ARIA-expanded reflects state  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Collapsible UI elements present  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Toggle section      | `aria-expanded` updates      |

**Postconditions:**  
State is communicated to assistive tech

**Expected Result:**  
Attribute reflects open/closed state