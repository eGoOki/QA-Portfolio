# 🎨 Color Contrast & Visual Design – Mobile QA Test Cases

This section focuses on verifying that mobile applications use accessible color combinations and visual design patterns that support readability, usability, and inclusivity for users with visual impairments or cognitive challenges.

---

## 🎯 Scope

These test cases cover:

- 🌈 WCAG-compliant color contrast ratios  
- 🧠 Visual hierarchy and layout clarity  
- 🧪 Color-blindness simulation and validation  
- 📱 Theme consistency (light/dark modes)  
- 🧭 Use of color-independent cues (icons, labels)

---

### ⛔ Out of Scope

- [**TalkBack testing for Android devices**](../Accessibility/TalkBack_Checks.md)  
- [**VoiceOver testing for iOS devices**](../Accessibility/VoiceOver_Checks.md)  

---

## 🎨 TC-VISUAL-001 – Text contrast ratio validation

**Title:** Verify contrast ratio between text and background  
**Section:** Color_Contrast_Visual_Design  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Critical  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Accessibility QA  
**Estimate:** 3m  
**References:** WCAG 2.1 – SC 1.4.3  
**Preconditions:** App screen with text elements

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Use contrast checker on text    | Ratio ≥ 4.5:1 for normal text            |
| 2    | Repeat for large text           | Ratio ≥ 3:1 for large text               |

**Postconditions:** Text readable in all modes  
**General Expected Result:** All text must meet WCAG contrast ratios

---

## 🎨 TC-VISUAL-002 – Color-only indicators

**Title:** Validate that color is not the sole indicator  
**Section:** Color_Contrast_Visual_Design  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Accessibility QA  
**Estimate:** 2m  
**References:** WCAG 2.1 – SC 1.4.1  
**Preconditions:** App uses color to convey status

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Identify color-coded elements   | Icons or labels supplement color cues    |
| 2    | Simulate color-blindness        | Meaning remains clear without color      |

**Postconditions:** Color-independent feedback  
**General Expected Result:** Color must be supplemented with symbols or text

---

## 🎨 TC-VISUAL-003 – Dark mode contrast validation

**Title:** Ensure sufficient contrast in dark theme  
**Section:** Color_Contrast_Visual_Design  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Accessibility QA  
**Estimate:** 3m  
**References:** WCAG 2.1 – SC 1.4.3  
**Preconditions:** App supports dark mode

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Enable dark mode                | Text remains readable                    |
| 2    | Measure contrast ratios         | Meets WCAG thresholds                    |

**Postconditions:** Dark mode is accessible  
**General Expected Result:** Contrast must be preserved across themes

---

## 🎨 TC-VISUAL-004 – Visual hierarchy validation

**Title:** Verify clarity of layout and element grouping  
**Section:** Color_Contrast_Visual_Design  
**Template:** Steps + Results  
**Type:** Usability  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** UX QA  
**Estimate:** 2m  
**References:** WCAG 2.1 – SC 1.3.1  
**Preconditions:** App screen with multiple sections

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Review layout visually          | Headings, buttons, and content are distinct |
| 2    | Check spacing and alignment     | Logical grouping and flow                |

**Postconditions:** Layout supports comprehension  
**General Expected Result:** Visual hierarchy must guide user attention

---

## 🎨 TC-VISUAL-005 – Color-blindness simulation

**Title:** Validate interface under color-blind conditions  
**Section:** Color_Contrast_Visual_Design  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Accessibility QA  
**Estimate:** 3m  
**References:** WCAG 2.1 – SC 1.4.1  
**Preconditions:** Color-blindness simulator available

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Simulate protanopia/deuteranopia| UI remains understandable                |
| 2    | Review key elements             | No loss of meaning due to color shift    |

**Postconditions:** Interface usable by color-blind users  
**General Expected Result:** Design must accommodate color vision deficiencies

---

## 🎨 TC-VISUAL-006 – High contrast mode support

**Title:** App respects OS-level high contrast settings  
**Section:** Color_Contrast_Visual_Design  
**Template:** Steps + Results  
**Type:** Accessibility  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Accessibility QA  
**Estimate:** 2m  
**References:** WCAG 2.1 – SC 1.4.6  
**Preconditions:** Device with high contrast mode enabled

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Enable high contrast mode       | App adjusts colors accordingly           |
| 2    | Review UI elements              | No loss of visibility or functionality   |

**Postconditions:** App adapts to system settings  
**General Expected Result:** High contrast mode must be respected