# ✅ XSS Attack – Mobile QA Test Cases

This section focuses on identifying vulnerabilities where untrusted input is improperly handled and rendered in the browser, allowing attackers to inject and execute malicious scripts in the context of the user session.

---

## 🎯 Scope

These test cases cover:

- 🧪 Reflected, Stored, and DOM-based XSS  
- 🧠 Input validation and output encoding flaws  
- 🧵 Script injection via attributes and event handlers  
- 🧱 Bypass techniques for filters and sanitizers  
- 🧬 Business logic abuse via client-side injection

---

### ⛔ Out of Scope

- [**SQL-based XSS vectors**](SQL_Injection.md)  
- [**Authentication bypass via script injection**](Authentication_Bypass.md)  
- [**Secure cookie and session handling**](Session_Management.md)

---

## 🔐 TC-SEC-XSS-001 – Script injection via WebView form field

**Title:** Script tag accepted in WebView field  
**Section:** XSS_Attack  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** OWASP-MOB-XSS-001  
**Preconditions:** Form rendered using WebView

**Steps and Results:**

| Step | Action                          | Expected Result                     |
|------|----------------------------------|-------------------------------------|
| 1    | Type `<script>alert('xss')</script>` | Input escaped or rejected     |
| 2    | Submit form                     | No popup or JS execution occurs     |

**Postconditions:** No script executed via form  
**General Expected Result:** WebView input sanitized

---

## 🔐 TC-SEC-XSS-002 – Reflected XSS using URL parameter

**Title:** Reflection vulnerability via app URL input  
**Section:** XSS_Attack  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 4m  
**References:** OWASP-MOB-XSS-002  
**Preconditions:** URL param parsed in WebView

**Steps and Results:**

| Step | Action                                         | Expected Result                        |
|------|------------------------------------------------|----------------------------------------|
| 1    | Pass `<script>alert(1)</script>` in URL param | Script tag encoded, not executed       |
| 2    | Launch screen rendering URL param             | No popup appears                       |

**Postconditions:** Unsafe code blocked on load  
**General Expected Result:** URL input treated as plain text

---

## 🔐 TC-SEC-XSS-003 – Stored XSS in user-generated content

**Title:** Persistent script saved and rendered in WebView  
**Section:** XSS_Attack  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 4m  
**References:** OWASP-MOB-XSS-003  
**Preconditions:** App stores user comments or profile data

**Steps and Results:**

| Step | Action                                     | Expected Result                     |
|------|--------------------------------------------|-------------------------------------|
| 1    | Save field with `<img src=x onerror=alert(1)>` | Input filtered or encoded        |
| 2    | Reopen stored content                      | No script executed                  |

**Postconditions:** WebView displays content safely  
**General Expected Result:** HTML rendered without execution

---

## 🔐 TC-SEC-XSS-004 – CSP header validation in WebView

**Title:** Missing or weak Content Security Policy  
**Section:** XSS_Attack  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer