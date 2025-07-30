# 🧠 Reverse Engineering – Mobile QA Test Cases

This section focuses on identifying vulnerabilities and undocumented behaviors by analyzing the internal structure of mobile applications through static and dynamic reverse engineering techniques.

---

## 🎯 Scope

These test cases cover:

- 🧪 Static analysis of APK/IPA binaries  
- 🧠 Decompiled code inspection  
- 🔍 Discovery of hardcoded secrets and logic flaws  
- 🧵 Dynamic instrumentation and runtime tracing  
- 🧬 Detection of anti-reversing mechanisms

---

### ⛔ Out of Scope

- [**Code injection and runtime exploitation**](Code_Injection.md)  
- [**Authentication bypass via client-side logic**](Authentication_Bypass.md)  
- [**Tampering with network traffic**](Insecure_Communication.md)

---

## 🧠 TC-SEC-RE-001 – Hardcoded credentials in source code

**Title:** Credentials discovered via decompilation  
**Section:** Reverse_Engineering  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-MOB-RE-001  
**Preconditions:** APK/IPA available for analysis

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Decompile app binary            | Source code extracted                    |
| 2    | Search for credentials          | Hardcoded secrets found                  |

**Postconditions:** Credentials exposed in code  
**General Expected Result:** No sensitive data should be hardcoded

---

## 🧠 TC-SEC-RE-002 – API keys exposed in strings.xml

**Title:** Sensitive keys found in resource files  
**Section:** Reverse_Engineering  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-RE-002  
**Preconditions:** App uses Android resource files

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Extract strings.xml             | File readable                            |
| 2    | Search for API keys             | Keys visible in plaintext                |

**Postconditions:** API keys exposed  
**General Expected Result:** Keys must be stored securely

---

## 🧠 TC-SEC-RE-003 – Business logic exposed via decompiled code

**Title:** Sensitive logic visible in client-side code  
**Section:** Reverse_Engineering  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-RE-003  
**Preconditions:** Decompiled code accessible

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Review decompiled classes       | Business rules visible                   |
| 2    | Analyze logic flow              | Sensitive decisions handled client-side  |

**Postconditions:** Logic exposed to attacker  
**General Expected Result:** Business logic must be server-side

---

## 🧠 TC-SEC-RE-004 – Debug symbols present in release build

**Title:** App includes debug metadata in production  
**Section:** Reverse_Engineering  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 2m  
**References:** OWASP-MOB-RE-004  
**Preconditions:** Release build available

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Inspect binary for symbols      | Debug info should be stripped            |
| 2    | Observe metadata                | Class/method names visible               |

**Postconditions:** App easier to reverse  
**General Expected Result:** Debug symbols must be removed in release

---

## 🧠 TC-SEC-RE-005 – Anti-reversing checks missing

**Title:** App lacks protection against reverse engineering  
**Section:** Reverse_Engineering  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-RE-005  
**Preconditions:** App installed on test device

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Attach debugger or hook tool    | App should detect and block              |
| 2    | Observe behavior                | App runs normally                        |

**Postconditions:** No anti-reversing logic  
**General Expected Result:** App must detect tampering attempts

---

## 🧠 TC-SEC-RE-006 – Sensitive file paths exposed in logs

**Title:** Internal paths visible via logcat  
**Section:** Reverse_Engineering  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Low  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 2m  
**References:** OWASP-MOB-RE-006  
**Preconditions:** App logging enabled

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Run app and monitor logcat      | Logs should exclude sensitive info       |
| 2    | Review logs                     | Internal paths and stack traces visible  |

**Postconditions:** App reveals internal structure  
**General Expected Result:** Logs must be sanitized in production