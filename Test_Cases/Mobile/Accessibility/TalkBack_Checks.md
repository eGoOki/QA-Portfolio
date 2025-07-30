# ♿️ TalkBack Accessibility – Android Test Cases

---

> ⚠️ **Note**: These test cases verify mobile screen reader compatibility using Android TalkBack. Actual implementation may vary by app design, component library, and QA workflow.

---

## 🎯 Scope

These TalkBack test cases cover:

- 📱 Label announcements for standard and custom UI elements  
- ✅ State feedback for buttons, checkboxes, and inputs  
- 🚨 Validation errors and accessibility of error messaging  
- 🧭 Logical navigation order and focus management  
- 📷 Accessibility of visual elements (e.g. icons, images)  
- 🧩 Modal dialogs, navigation drawers, and toast messages  
- 🧑‍💻 Keyboard focus sync and interaction support  

---

### ⛔ Out of Scope

- **VoiceOver testing for iOS devices** – see [VoiceOver_TestCases.md](./VoiceOver_TestCases.md)  
- **Functional feature testing** – see feature-specific files  
- **Accessibility audits beyond TalkBack screen reader**

---

## ♿️ TC-ACCESS-TB-001 – Button label is announced by TalkBack

**Title:** Button label is announced by TalkBack  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-ANDROID-001  
**Preconditions:** TalkBack enabled; app is installed and launched

**Steps and Results:**

| Step | Action                    | Expected Result                            |
|------|---------------------------|--------------------------------------------|
| 1    | Navigate to login screen  | Login screen is displayed                  |
| 2    | Focus on login button     | Button label is announced aloud by TalkBack |

**Postconditions:** Button label confirmed as accessible  
**General Expected Result:** Button is properly announced by screen reader

---

## ♿️ TC-ACCESS-TB-002 – Checkbox state is announced

**Title:** Checkbox state announced by TalkBack  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-ANDROID-002  
**Preconditions:** TalkBack enabled; checkbox is visible

**Steps and Results:**

| Step | Action                            | Expected Result                                 |
|------|-----------------------------------|-------------------------------------------------|
| 1    | Focus on terms agreement checkbox | Label and current state (checked/unchecked) are announced |

**Postconditions:** Checkbox confirmed accessible  
**General Expected Result:** TalkBack reads full state and purpose

---

## ♿️ TC-ACCESS-TB-003 – Hint text is announced for input fields

**Title:** Input field hint is announced by TalkBack  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-ANDROID-003  
**Preconditions:** TalkBack enabled; input field includes hint text

**Steps and Results:**

| Step | Action                     | Expected Result                                       |
|------|----------------------------|-------------------------------------------------------|
| 1    | Focus on email input field | TalkBack announces label followed by hint (“Enter your email”) |

**Postconditions:** Input field confirmed accessible  
**General Expected Result:** Field provides helpful guidance via screen reader

---

## ♿️ TC-ACCESS-TB-004 – Error message is announced after invalid input

**Title:** Validation error message is announced by TalkBack  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ACCESS-ANDROID-004  
**Preconditions:** Form contains validation rules; TalkBack enabled

**Steps and Results:**

| Step | Action                         | Expected Result                               |
|------|--------------------------------|-----------------------------------------------|
| 1    | Submit form with invalid data  | Error message is displayed                    |
| 2    | Focus on the field with error  | TalkBack reads the error message aloud        |

**Postconditions:** Validation confirmed accessible  
**General Expected Result:** Screen reader reads error details after invalid action

---

## ♿️ TC-ACCESS-TB-005 – Modal content is announced correctly

**Title:** Modal content is read by TalkBack in correct order  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ACCESS-ANDROID-005  
**Preconditions:** Modal dialog is accessible in the app

**Steps and Results:**

| Step | Action                  | Expected Result                              |
|------|-------------------------|----------------------------------------------|
| 1    | Open modal dialog       | Modal appears with content                   |
| 2    | Swipe through elements  | TalkBack announces all modal items in sequence |

**Postconditions:** Modal confirmed screen reader-friendly  
**General Expected Result:** No items are skipped; full accessibility ensured

---

## ♿️ TC-ACCESS-TB-006 – Focus order follows logical sequence

**Title:** UI focus is announced in logical visual order  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-ANDROID-006  
**Preconditions:** TalkBack enabled; all screen elements rendered

**Steps and Results:**

| Step | Action                     | Expected Result                                     |
|------|----------------------------|-----------------------------------------------------|
| 1    | Swipe through the screen   | TalkBack announces elements from top to bottom, left to right |

**Postconditions:** Logical reading order confirmed  
**General Expected Result:** No jumps or confusion in screen reader navigation

---

## ♿️ TC-ACCESS-TB-007 – Custom components have accessibility labels

**Title:** Custom components are labeled and announced correctly  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ACCESS-ANDROID-007  
**Preconditions:** TalkBack enabled; custom UI elements displayed

**Steps and Results:**

| Step | Action                     | Expected Result                                       |
|------|----------------------------|-------------------------------------------------------|
| 1    | Focus on custom toggle     | TalkBack announces label and current state           |
| 2    | Focus on custom slider     | TalkBack announces label, current value, and range   |

**Postconditions:** Custom controls confirmed accessible  
**General Expected Result:** Non-standard elements provide clear audio feedback

---

## ♿️ TC-ACCESS-TB-008 – Image views have descriptive content description

**Title:** Images are announced with alternative text  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ACCESS-ANDROID-008  
**Preconditions:** Image has a contentDescription assigned

**Steps and Results:**

| Step | Action                  | Expected Result                             |
|------|-------------------------|---------------------------------------------|
| 1    | Focus on image          | TalkBack announces the image's description  |

**Postconditions:** Image verified accessible  
**General Expected Result:** Visual elements provide meaningful text description

---

## ♿️ TC-ACCESS-TB-009 – All interactive elements are reachable

**Title:** Screen reader can reach all interactive items  
**Section:** Accessibility_TalkBack  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Not run  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ACCESS-ANDROID-009  
**Preconditions:** TalkBack enabled; screen contains multiple components

**Steps and Results:**

| Step | Action                     | Expected Result                                   |
|------|----------------------------|---------------------------------------------------|
| 1    | Swipe through entire screen | TalkBack reaches all buttons, inputs, and toggles |

**Postconditions:** Interactive UI verified reachable  
**General Expected Result:** No elements skipped or unreachable

---

##