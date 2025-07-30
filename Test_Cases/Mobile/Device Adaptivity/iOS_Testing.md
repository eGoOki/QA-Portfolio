# ✅ Device Adaptivity – iOS Test Cases

---

> ⚠️ **Note**: These test cases are examples. Real-world implementations may differ by device matrix, OS version, or QA workflow.

---

## 🎯 Scope

These iOS test cases cover:

- 📐 Layout responsiveness across iPhone and iPad models  
- 🧠 Dynamic Type scaling and accessibility modes  
- 🧭 Safe area and notch-aware design  
- 🔄 Split-view multitasking and external display behavior  
- 🌙 Dark mode and high-contrast UI validation

---

### ⛔ Out of Scope

- **Android-specific layout behavior** – see [Android_Testing.md](./Android_Testing.md)  
- **Login flow adaptivity** – see [Login_Edge_Cases_Mobile.md](../Login_Form/Login_Edge_Cases_Mobile.md)

---

## 🍏 TC-ADAPT-IOS-001 – Layout on various iOS screen sizes

**Title:** Layout rendering on iPhone SE, iPhone 14 Pro Max, and iPad  
**Section:** Device Adaptivity – iOS  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ADAPT-010  
**Preconditions:** App installed; default display settings

**Steps and Results:**

| Step | Action                            | Expected Result                               |
|------|-----------------------------------|-----------------------------------------------|
| 1    | Launch app on iPhone SE           | Layout fits screen without scroll or cutoff   |
| 2    | Launch app on iPhone 14 Pro Max   | Layout scales proportionally and centers      |
| 3    | Launch app on iPad (landscape)    | UI adapts with proper spacing and alignment   |

**Postconditions:** Layout verified across iOS device matrix  
**General Expected Result:** Responsive UI across screen sizes

---

## 🍏 TC-ADAPT-IOS-002 – Dynamic Type scaling support

**Title:** Verify layout responsiveness with Dynamic Type enabled  
**Section:** Device Adaptivity – iOS  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ADAPT-011  
**Preconditions:** Dynamic Type enabled in Settings; app launched

**Steps and Results:**

| Step | Action                                         | Expected Result                                      |
|------|------------------------------------------------|------------------------------------------------------|
| 1    | Enable Dynamic Type in system settings         | System font size increases                          |
| 2    | Launch the app on iPhone 14 Pro Max            | Layout adjusts and remains readable                 |
| 3    | Navigate through main views and subviews       | No cutoff or layout breakage across scaled text     |

**Postconditions:** UI adapts to enlarged fonts  
**General Expected Result:** Text remains legible without layout issues

---

## 🍏 TC-ADAPT-IOS-003 – Safe area and notch handling

**Title:** Validate layout within safe areas and notch zones  
**Section:** Device Adaptivity – iOS  
**Template:** Steps + Results  
**Type:** Compatibility  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ADAPT-012  
**Preconditions:** App launched on notch-enabled device

**Steps and Results:**

| Step | Action                                | Expected Result                                 |
|------|---------------------------------------|-------------------------------------------------|
| 1    | Launch app on iPhone 14 Pro           | Layout avoids notch and gesture areas           |
| 2    | Interact with top navigation bar      | No overlap with notch or status indicators      |
| 3    | Scroll through content                | Content respects safe area margins              |

**Postconditions:** Layout respects safe area constraints  
**General Expected Result:** UI remains usable and visually consistent

---

## 🍏 TC-ADAPT-IOS-004 – Split-view multitasking behavior

**Title:** Validate layout in split-view multitasking  
**Section:** Device Adaptivity – iOS  
**Template:** Steps + Results  
**Type:** Usability  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ADAPT-013  
**Preconditions:** App launched on iPad; multitasking enabled

**Steps and Results:**

| Step | Action                                | Expected Result                                 |
|------|---------------------------------------|-------------------------------------------------|
| 1    | Open app in full-screen mode          | Layout renders normally                         |
| 2    | Enter split-view with another app     | Layout adjusts to reduced width                 |
| 3    | Interact with app in split mode       | UI remains functional and readable              |

**Postconditions:** App remains usable in multitasking mode  
**General Expected Result:** UI adapts to split-view constraints

---

## 🍏 TC-ADAPT-IOS-005 – External display layout via AirPlay

**Title:** Validate layout on external display via AirPlay  
**Section:** Device Adaptivity – iOS  
**Template:** Steps + Results  
**Type:** Compatibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-ADAPT-014  
**Preconditions:** AirPlay connection established; app launched

**Steps and Results:**

| Step | Action                                | Expected Result                                 |
|------|---------------------------------------|-------------------------------------------------|
| 1    | Connect device to external display    | Screen mirrors or extends                       |
| 2    | Launch app                            | Layout adapts to external resolution            |
| 3    | Interact with app                     | UI remains responsive and visually consistent   |

**Postconditions:** Layout verified on external display  
**General Expected Result:** App functions properly via AirPlay

---

## 🍏 TC-ADAPT-IOS-006 – Dark mode and contrast validation

**Title:** Validate UI in dark mode and high contrast  
**Section:** Device Adaptivity – iOS  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-ADAPT-015  
**Preconditions:** Dark mode and contrast settings enabled

**Steps and Results:**

| Step | Action                          | Expected Result                                 |
|------|---------------------------------|-------------------------------------------------|
| 1    | Enable dark mode                | System switches to dark theme                   |
| 2    | Launch app                      | UI elements adapt to dark background            |
| 3    | Enable increased contrast       | Text and icons remain visible and readable      |

**Postconditions:** UI remains accessible in dark/high-contrast modes  
**General Expected Result:** Visual clarity preserved across themes