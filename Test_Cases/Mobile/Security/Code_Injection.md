# 🧬 Code Injection – Mobile QA Test Cases

This section focuses on identifying vulnerabilities where user input is improperly processed as executable code, allowing attackers to inject and run arbitrary logic within the application or server environment.

---

## 🎯 Scope

These test cases cover:

- 🧪 Server-side code injection (PHP, ASP, etc.)  
- 🧠 Dynamic evaluation of user input  
- 📂 File inclusion via user-controlled parameters  
- 🧵 Injection via query strings and form fields  
- 🧬 Unsafe use of eval(), exec(), include()

---

### ⛔ Out of Scope

- [**Command injection and OS-level exploits**](Command_Injection.md)  
- [**Client-side script injection (XSS)**](XSS_Testing.md)  
- [**SQL-based logic manipulation**](SQL_Injection.md)

---

## 🧬 TC-SEC-CODE-001 – PHP include() injection via query string

**Title:** Remote file inclusion using query parameter  
**Section:** Code_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-WSTG-INPV-11  
**Preconditions:** App uses dynamic include()

| Step | Action                                      | Expected Result                          |
|------|---------------------------------------------|------------------------------------------|
| 1    | Modify URL to include external script       | App should reject external file          |
| 2    | Observe response                            | App loads and executes remote code       |

**Postconditions:** Remote code executed  
**General Expected Result:** App must validate include paths

---

## 🧬 TC-SEC-CODE-002 – ASP code injection via form field

**Title:** Executable input processed by server  
**Section:** Code_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-WSTG-INPV-11  
**Preconditions:** ASP backend with dynamic execution

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Submit payload via form         | App should treat input as data only      |
| 2    | Observe server behavior         | Input executed as code                   |

**Postconditions:** Arbitrary code executed  
**General Expected Result:** Input must be sanitized before execution

---

## 🧬 TC-SEC-CODE-003 – Eval() injection via GET parameter

**Title:** Code executed via unsafe eval() usage  
**Section:** Code_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-WSTG-INPV-11  
**Preconditions:** App uses eval() on user input

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Submit payload via GET param    | App should reject code-like input        |
| 2    | Observe execution               | Code runs on server                      |

**Postconditions:** Server-side logic compromised  
**General Expected Result:** Eval must not process raw input

---

## 🧬 TC-SEC-CODE-004 – File upload triggers dynamic execution

**Title:** Uploaded file executed as server-side script  
**Section:** Code_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-WSTG-INPV-11  
**Preconditions:** File upload feature enabled

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Upload file with embedded code  | App should store file safely             |
| 2    | Access file via URL             | Server executes uploaded code            |

**Postconditions:** Arbitrary code executed  
**General Expected Result:** Uploaded files must not be executable

---

## 🧬 TC-SEC-CODE-005 – Code injection via cookie value

**Title:** Malicious code injected through cookie  
**Section:** Code_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 2m  
**References:** OWASP-WSTG-INPV-11  
**Preconditions:** App reads cookie into logic

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Set cookie with code payload    | App should treat cookie as data          |
| 2    | Observe server behavior         | Code executed from cookie                |

**Postconditions:** Logic injection via cookie  
**General Expected Result:** Cookies must be parsed safely

---

## 🧬 TC-SEC-CODE-006 – Code injection via debug parameter

**Title:** Debug mode allows code execution  
**Section:** Code_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 2m  
**References:** OWASP-WSTG-INPV-11  
**Preconditions:** Debug mode enabled

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Submit code via debug param     | App should ignore executable input       |
| 2    | Observe response                | Code executed in debug context           |

**Postconditions:** Debug logic abused  
**General Expected Result:** Debug features must be disabled in production