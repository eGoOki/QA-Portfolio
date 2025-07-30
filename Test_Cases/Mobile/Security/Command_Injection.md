# 🧨 Command Injection – Mobile QA Test Cases

This section focuses on identifying vulnerabilities where user input is improperly passed to system-level commands, allowing attackers to execute arbitrary OS instructions on the server or device.

---

## 🎯 Scope

These test cases cover:

- 🧪 OS-level command injection via input fields  
- 🧵 Shell metacharacter exploitation (`|`, `;`, `&&`)  
- 🧠 Unsafe use of system APIs (`exec`, `system`, `Runtime`)  
- 🧬 Blind and time-based command injection  
- 🧰 File and environment variable manipulation

---

### ⛔ Out of Scope

- [**Code injection via eval or include**](Code_Injection.md)  
- [**Reverse engineering of binary logic**](Reverse_Engineering.md)  
- [**Network-level tampering**](Insecure_Communication.md)

---

## 🧨 TC-SEC-CMD-001 – Command injection via form field

**Title:** OS command executed from user input  
**Section:** Command_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-WSTG-INPV-12  
**Preconditions:** Form input accepted by backend

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Submit payload `test;whoami`    | App should reject command syntax         |
| 2    | Observe response                | Server executes `whoami`                 |

**Postconditions:** OS command executed  
**General Expected Result:** Input must be sanitized before execution

---

## 🧨 TC-SEC-CMD-002 – Command injection via query string

**Title:** Shell metacharacters trigger execution  
**Section:** Command_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-WSTG-INPV-12  
**Preconditions:** URL parameter processed by shell

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Append `?file=doc.txt;ls`       | App should reject chained command        |
| 2    | Observe output                  | Directory listing returned               |

**Postconditions:** Shell command executed  
**General Expected Result:** Parameters must be validated

---

## 🧨 TC-SEC-CMD-003 – Blind command injection via time delay

**Title:** Response delay confirms command execution  
**Section:** Command_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-WSTG-INPV-12  
**Preconditions:** Input processed by shell

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Submit `ping -c 10 127.0.0.1`   | App should reject long-running command   |
| 2    | Measure response time           | Response delayed by 10 seconds           |

**Postconditions:** Command executed silently  
**General Expected Result:** App must block time-based payloads

---

## 🧨 TC-SEC-CMD-004 – Injection via cookie value

**Title:** Cookie used to execute OS command  
**Section:** Command_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 2m  
**References:** OWASP-WSTG-INPV-12  
**Preconditions:** Cookie parsed by backend

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Set cookie `user=admin;id`      | App should ignore command syntax         |
| 2    | Observe response                | Server returns user ID                   |

**Postconditions:** Command executed from cookie  
**General Expected Result:** Cookies must be parsed safely

---

## 🧨 TC-SEC-CMD-005 – Command injection via file upload name

**Title:** Filename triggers shell execution  
**Section:** Command_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-WSTG-INPV-12  
**Preconditions:** File upload enabled

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Upload file named `test;ls.txt` | App should sanitize filename             |
| 2    | Observe server logs             | `ls` command executed                    |

**Postconditions:** Filename used as command  
**General Expected Result:** Filenames must be sanitized

---

## 🧨 TC-SEC-CMD-006 – Command injection via debug parameter

**Title:** Debug mode allows command execution  
**Section:** Command_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 2m  
**References:** OWASP-WSTG-INPV-12  
**Preconditions:** Debug mode enabled

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Submit `debug=1;whoami`         | App should ignore shell syntax           |
| 2    | Observe output                  | `whoami` result returned                 |

**Postconditions:** Debug logic abused  
**General Expected Result:** Debug features must be disabled in production