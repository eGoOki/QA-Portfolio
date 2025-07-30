# 🕷️ XSS Attack – Security Test Cases

---

> ⚠️ **Note**: These test cases simulate cross-site scripting attempts to verify that the system properly escapes and sanitizes user input.

---

## 📄 Table of Contents

- TC-XSS-101 – XSS in comment field
- TC-XSS-102 – XSS in profile name
- TC-XSS-103 – XSS via URL fragment
- TC-XSS-104 – Stored XSS in dashboard widget
- TC-XSS-105 – DOM-based XSS attempt

---

## 💬 TC-XSS-101 – XSS in comment field

**Title:** Inject `<script>` into comment  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Preconditions:** Comment field must render HTML  

| Step | Action                          | Expected Result                          |
|------|----------------------------------|-------------------------------------------|
| 1    | Open comment form               | Field is visible                          |
| 2    | Enter `<script>alert('XSS')</script>` | Input rejected or escaped         |
| 3    | Submit comment                  | Script not executed                       |

**Postconditions:**  
No script execution

**Expected Result:**  
System escapes HTML tags and prevents XSS

---

## 🧑‍💼 TC-XSS-102 – XSS in profile name

**Title:** Inject script into user profile  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Profile name is displayed on dashboard  

| Step | Action                          | Expected Result                          |
|------|----------------------------------|-------------------------------------------|
| 1    | Edit profile name               | Input accepted                            |
| 2    | Enter `<img src=x onerror=alert(1)>` | Input sanitized                    |
| 3    | Save and view dashboard         | No script executed                        |

**Postconditions:**  
Dashboard remains safe

**Expected Result:**  
System escapes dangerous attributes

---

## 🔗 TC-XSS-103 – XSS via URL fragment

**Title:** Inject script in URL hash  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Page reads URL fragment  

| Step | Action                          | Expected Result                          |
|------|----------------------------------|-------------------------------------------|
| 1    | Navigate to `#<script>alert(1)</script>` | Page loads normally               |

**Postconditions:**  
No script execution

**Expected Result:**  
System ignores or escapes URL fragments

---

## 📊 TC-XSS-104 – Stored XSS in dashboard widget

**Title:** Persistent script injection  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Preconditions:** Widget content is stored and rendered  

| Step | Action                          | Expected Result                          |
|------|----------------------------------|-------------------------------------------|
| 1    | Add widget with `<script>` tag  | Input rejected or escaped                 |
| 2    | Reload dashboard                 | No script executed                        |

**Postconditions:**  
No persistent XSS

**Expected Result:**  
System sanitizes stored content

---

## 🧬 TC-XSS-105 – DOM-based XSS attempt

**Title:** Inject script via client-side manipulation  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Page uses client-side rendering  

| Step | Action                          | Expected Result                          |
|------|----------------------------------|-------------------------------------------|
| 1    | Inject payload via browser console | Page remains unaffected               |

**Postconditions:**  
DOM remains secure

**Expected Result:**  
Client-side scripts do not execute injected code