# ✅ WCAG Checks – Accessibility Test Cases

---

> ⚠️ **Note**: These test cases verify compliance with WCAG 2.1 Level AA guidelines.

---

## 📄 Table of Contents

- TC-WCAG-101 – Text contrast ratio
- TC-WCAG-102 – Keyboard navigation
- TC-WCAG-103 – Focus visibility
- TC-WCAG-104 – Alt text for images
- TC-WCAG-105 – Form label association

---

## 🎨 TC-WCAG-101 – Text contrast ratio

**Title:** Verify text contrast meets WCAG standards  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Page must contain text elements  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Inspect text color vs background | Contrast ratio ≥ 4.5:1 |

**Postconditions:**  
Text remains readable

**Expected Result:**  
All text meets minimum contrast requirements

---

## ⌨️ TC-WCAG-102 – Keyboard navigation

**Title:** Verify all interactive elements are keyboard accessible  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Page must contain buttons, links, inputs  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Use Tab key to navigate | Focus moves logically     |

**Postconditions:**  
No elements skipped

**Expected Result:**  
All controls reachable via keyboard

---

## 🔦 TC-WCAG-103 – Focus visibility

**Title:** Verify visible focus indicator  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Interactive elements present  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Tab through elements | Focus outline is visible    |

**Postconditions:**  
Focus remains visible

**Expected Result:**  
User can track focus position

---

## 🖼️ TC-WCAG-104 – Alt text for images

**Title:** Verify all images have descriptive alt text  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Page contains images  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Inspect image markup | `alt` attribute is present  |

**Postconditions:**  
Screen readers can describe images

**Expected Result:**  
All images have meaningful alt text

---

## 📝 TC-WCAG-105 – Form label association

**Title:** Verify form inputs are associated with labels  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Page contains forms  

| Step | Action              | Expected Result             |
|------|---------------------|------------------------------|
| 1    | Inspect input elements | Each has associated `<label>` |

**Postconditions:**  
Forms are screen reader friendly

**Expected Result:**  
Labels are correctly linked to inputs