# ♿️ VoiceOver Accessibility – iOS Test Cases

---

> ⚠️ **Note**: These test cases verify mobile screen reader compatibility using iOS VoiceOver. Actual implementation may vary by app design, component library, and QA workflow.

---

## 🎯 Scope

These VoiceOver test cases cover:

- 📱 Label announcements for standard and custom UI elements  
- ✅ State feedback for buttons, checkboxes, and inputs  
- 🚨 Validation errors and accessibility of error messaging  
- 🧭 Logical navigation order and focus management  
- 📷 Accessibility of visual elements (e.g. icons, images)  
- 🧩 Modal dialogs, navigation drawers, and toast messages  
- 🧑‍💻 Keyboard focus sync and interaction support  

---

### ⛔ Out of Scope

- **TalkBack testing for Android devices** – see [TalkBack_TestCases.md](./TalkBack_TestCases.md)  
- **Functional feature testing** – see feature-specific files  
- **Accessibility audits beyond VoiceOver screen reader**

---

## ♿️ TC-ACCESS-VO-001 – Button label is announced by VoiceOver

**Title:** Button label is announced by VoiceOver  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-IOS-001  
**Preconditions:** VoiceOver enabled; app is installed and launched

**Steps and Results:**

| Step | Action                    | Expected Result                            |
|------|---------------------------|--------------------------------------------|
| 1    | Navigate to login screen  | Login screen is displayed                  |
| 2    | Focus on login button     | Button label is announced aloud by VoiceOver |

**Postconditions:** Button label confirmed as accessible  
**General Expected Result:** Button is properly announced by screen reader

---

## ♿️ TC-ACCESS-VO-002 – Checkbox state is announced

**Title:** Checkbox state announced by VoiceOver  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-IOS-002  
**Preconditions:** VoiceOver enabled; checkbox is visible

**Steps and Results:**

| Step | Action                            | Expected Result                                 |
|------|-----------------------------------|-------------------------------------------------|
| 1    | Focus on terms agreement checkbox | Label and current state (checked/unchecked) are announced |

**Postconditions:** Checkbox confirmed accessible  
**General Expected Result:** VoiceOver reads full state and purpose

---

## ♿️ TC-ACCESS-VO-003 – Hint text is announced for input fields

**Title:** Input field hint is announced by VoiceOver  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-IOS-003  
**Preconditions:** VoiceOver enabled; input field includes hint text

**Steps and Results:**

| Step | Action                     | Expected Result                                       |
|------|----------------------------|-------------------------------------------------------|
| 1    | Focus on email input field | VoiceOver announces label followed by hint (“Enter your email”) |

**Postconditions:** Input field confirmed accessible  
**General Expected Result:** Field provides helpful guidance via screen reader

---

## ♿️ TC-ACCESS-VO-004 – Error message is announced after invalid input

**Title:** Validation error message is announced by VoiceOver  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ACCESS-IOS-004  
**Preconditions:** Form contains validation rules; VoiceOver enabled

**Steps and Results:**

| Step | Action                         | Expected Result                               |
|------|--------------------------------|-----------------------------------------------|
| 1    | Submit form with invalid data  | Error message is displayed                    |
| 2    | Focus on the field with error  | VoiceOver reads the error message aloud       |

**Postconditions:** Validation confirmed accessible  
**General Expected Result:** Screen reader reads error details after invalid action

---

## ♿️ TC-ACCESS-VO-005 – Modal content is announced correctly

**Title:** Modal content is read by VoiceOver in correct order  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ACCESS-IOS-005  
**Preconditions:** Modal dialog is accessible in the app

**Steps and Results:**

| Step | Action                  | Expected Result                              |
|------|-------------------------|----------------------------------------------|
| 1    | Open modal dialog       | Modal appears with content                   |
| 2    | Swipe through elements  | VoiceOver announces all modal items in sequence |

**Postconditions:** Modal confirmed screen reader-friendly  
**General Expected Result:** No items are skipped; full accessibility ensured

---

## ♿️ TC-ACCESS-VO-006 – Focus order follows logical sequence

**Title:** UI focus is announced in logical visual order  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-IOS-006  
**Preconditions:** VoiceOver enabled; all screen elements rendered

**Steps and Results:**

| Step | Action                     | Expected Result                                     |
|------|----------------------------|-----------------------------------------------------|
| 1    | Swipe through the screen   | VoiceOver announces elements from top to bottom, left to right |

**Postconditions:** Logical reading order confirmed  
**General Expected Result:** No jumps or confusion in screen reader navigation

---

## ♿️ TC-ACCESS-VO-007 – Custom components have accessibility labels

**Title:** Custom components are labeled and announced correctly  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ACCESS-IOS-007  
**Preconditions:** VoiceOver enabled; custom UI elements displayed

**Steps and Results:**

| Step | Action                     | Expected Result                                       |
|------|----------------------------|-------------------------------------------------------|
| 1    | Focus on custom toggle     | VoiceOver announces label and current state           |
| 2    | Focus on custom slider     | VoiceOver announces label, current value, and range   |

**Postconditions:** Custom controls confirmed accessible  
**General Expected Result:** Non-standard elements provide clear audio feedback

---

## ♿️ TC-ACCESS-VO-008 – Image views have descriptive content description

**Title:** Images are announced with alternative text  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-IOS-008  
**Preconditions:** Image has an accessibility label or description

**Steps and Results:**

| Step | Action                  | Expected Result                             |
|------|-------------------------|---------------------------------------------|
| 1    | Focus on image          | VoiceOver announces the image's description |

**Postconditions:** Image verified accessible  
**General Expected Result:** Visual elements provide meaningful text description

---

## ♿️ TC-ACCESS-VO-009 – All interactive elements are reachable

**Title:** Screen reader can reach all interactive items  
**Section:** Accessibility_VoiceOver  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ACCESS-IOS-009  
**Preconditions:** VoiceOver enabled; screen contains multiple components

**Steps and Results:**

| Step | Action                     | Expected Result                                   |
|------|----------------------------|---------------------------------------------------|
| 1    | Swipe through entire screen | VoiceOver reaches all buttons, inputs, and toggles |

**Postconditions:** Interactive UI verified reachable  
**General Expected Result:** No elements skipped or unreachable

---
