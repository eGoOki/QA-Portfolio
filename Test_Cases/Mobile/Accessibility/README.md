# ♿ Mobile Accessibility – QA Module

This module contains manual test cases and structured checklists focused on mobile accessibility, including Android TalkBack and iOS VoiceOver support. The materials help validate screen reader compatibility, element focus behavior, and semantic design for users with assistive technologies.

---

## 🎯 Scope

This accessibility module covers:

- ✅ Screen reader support for Android (TalkBack) and iOS (VoiceOver)  
- 🔊 Announcements for buttons, inputs, labels, and error messages  
- 🧩 Modal dialogs, images, checkboxes, and custom components  
- 🧭 Logical focus order and gesture navigation  
- 🧠 Semantic hierarchy and accessibility labeling  
- 📐 Visual accessibility (color contrast – in separate module)

---

### ⛔ Out of Scope

- **Web accessibility validation** – not included in this module  
- **Desktop keyboard navigation** – not applicable to mobile platforms  

---

## 📄 Files

| 📂 File Name                                 | 📱 Platform     | 📑 Type       | 🔍 Description                                         |
|---------------------------------------------|-----------------|---------------|--------------------------------------------------------|
| [`TalkBack_Checks.md`](./TalkBack_Checks.md) | Android         | Test Cases    | Screen reader validation for TalkBack (Android)        |
| [`VoiceOver_Checks.md`](./VoiceOver_Checks.md) | iOS            | Test Cases    | Screen reader validation for VoiceOver (iOS)           |
| [`Color_Contrast_Visual_Design.md`](./Color_Contrast_Visual_Design.md) | Cross-platform | Test Cases    | Visual contrast checks for readable UI design          |


> All test cases use a standardized format aligned with the rest of the QA Portfolio, including metadata, execution steps, and postconditions.

---

## ✅ Best Practices Covered

- Ensure every interactive element is reachable via screen reader  
- Provide descriptive labels and hints for all inputs and buttons  
- Announce validation errors through accessible feedback  
- Maintain logical focus navigation across all screens  
- Avoid color-only indicators — support text and symbols  
- Test modals, drawers, and system messages for accessibility  

---

## 🛠️ Usage

These assets are intended for manual execution during accessibility QA runs.  
Each case can be tracked individually or integrated into release regression flows.

---
