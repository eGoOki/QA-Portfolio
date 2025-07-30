# 🈶 Localization & Internationalization Test Cases

---

> ⚠️ **Note**: These test cases validate both localized content and internationalization readiness. They ensure the application behaves correctly across different languages, regions, and cultural settings.

---

## 📄 Table of Contents

- [TC-L10N-001 – Localized error messages based on browser language](#tc-l10n-001--localized-error-messages-based-on-browser-language)  
- [TC-L10N-002 – RTL layout rendering](#tc-l10n-002--rtl-layout-rendering)  
- [TC-I18N-003 – Pseudolocalization string expansion](#tc-i18n-003--pseudolocalization-string-expansion)  
- [TC-I18N-004 – Unicode character support](#tc-i18n-004--unicode-character-support)  
- [TC-L10N-005 – Regional date/time formatting](#tc-l10n-005--regional-datetime-formatting)  
- [TC-L10N-006 – Currency symbol and placement](#tc-l10n-006--currency-symbol-and-placement)  

---

## 🌐 TC-L10N-001 – Localized error messages based on browser language

**Type:** Usability / Localization  
**Priority:** Medium  
**Status:** Draft  
**Estimate:** 2m  
**Preconditions:** Browser language is set to French  

| Step | Action                          | Expected Result                                      |
|------|----------------------------------|------------------------------------------------------|
| 1    | Open login page                 | UI adapts to French locale                          |
| 2    | Enter invalid credentials       | Error message appears in French                     |

**Postconditions:**  
Localized message is displayed based on browser language

**General Expected Result:**  
System detects browser language and shows translated error text

---

## 🧭 TC-L10N-002 – RTL layout rendering

**Type:** UI / Localization  
**Priority:** Low  
**Status:** Draft  
**Estimate:** 2m  
**Preconditions:** Browser language set to Arabic  

| Step | Action                          | Expected Result                                      |
|------|----------------------------------|------------------------------------------------------|
| 1    | Open login page                 | UI switches to RTL layout                           |
| 2    | Observe field alignment         | Labels and inputs are right-aligned                 |

**Postconditions:**  
Layout respects RTL formatting and directionality

**General Expected Result:**  
UI elements adapt to RTL languages without distortion

---

## 🧪 TC-I18N-003 – Pseudolocalization string expansion

**Type:** Internationalization / Visual  
**Priority:** Medium  
**Status:** Draft  
**Estimate:** 2m  
**Preconditions:** App is configured with pseudolocalized strings  

| Step | Action                          | Expected Result                                      |
|------|----------------------------------|------------------------------------------------------|
| 1    | Open login page                 | Strings appear with brackets and extra characters   |
| 2    | Observe layout                  | No truncation or overflow occurs                    |

**Postconditions:**  
UI accommodates longer strings without breaking layout

**General Expected Result:**  
App handles string expansion gracefully across components

---

## 🧬 TC-I18N-004 – Unicode character support

**Type:** Functional / Compatibility  
**Priority:** High  
**Status:** Draft  
**Estimate:** 2m  
**Preconditions:** Input fields accept Unicode  

| Step | Action                          | Expected Result                                      |
|------|----------------------------------|------------------------------------------------------|
| 1    | Enter name in Japanese (e.g., 山田太郎) | Input accepted and stored correctly         |
| 2    | Submit form                     | Data is saved and displayed without corruption      |

**Postconditions:**  
Unicode characters are stored and rendered correctly

**General Expected Result:**  
System supports multilingual input and output

---

## 📅 TC-L10N-005 – Regional date/time formatting

**Type:** Localization / Formatting  
**Priority:** Medium  
**Status:** Draft  
**Estimate:** 2m  
**Preconditions:** User locale is set to Germany  

| Step | Action                          | Expected Result                                      |
|------|----------------------------------|------------------------------------------------------|
| 1    | View date field                 | Format is DD.MM.YYYY                                |
| 2    | View time field                 | Format is 24-hour (e.g., 14:30)                      |

**Postconditions:**  
Date/time formats match regional expectations

**General Expected Result:**  
System formats date/time based on locale settings

---

## 💰 TC-L10N-006 – Currency symbol and placement

**Type:** Localization / Formatting  
**Priority:** Medium  
**Status:** Draft  
**Estimate:** 2m  
**Preconditions:** Locale set to Japan  

| Step | Action                          | Expected Result                                      |
|------|----------------------------------|------------------------------------------------------|
| 1    | View product price              | Format is ¥1,200                                     |
| 2    | Switch to US locale             | Format changes to $12.00                            |

**Postconditions:**  
Currency symbol and placement adapt to locale

**General Expected Result:**  
System displays currency correctly for each region