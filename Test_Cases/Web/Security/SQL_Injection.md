# 🧨 SQL Injection – Security Test Cases

---

> ⚠️ **Note**: These test cases simulate malicious input patterns to verify that the system is protected against SQL injection attacks.

---

## 📄 Table of Contents

- TC-SQL-101 – Basic SQL injection in login form
- TC-SQL-102 – SQL injection via search field
- TC-SQL-103 – SQL injection in URL parameters
- TC-SQL-104 – SQL injection in registration form
- TC-SQL-105 – Blind SQL injection attempt

---

## 🔐 TC-SQL-101 – Basic SQL injection in login form

**Title:** Attempt login using `' OR '1'='1`  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Preconditions:** Login form must be active  

| Step | Action                          | Expected Result                          |
|------|----------------------------------|-------------------------------------------|
| 1    | Open login page                 | Form is displayed                         |
| 2    | Enter `' OR '1'='1` as username | Input accepted                            |
| 3    | Enter any password              | Input accepted                            |
| 4    | Click “Login”                   | Login fails, error shown                  |

**Postconditions:**  
No authentication granted

**Expected Result:**  
System blocks injection and logs attempt

---

## 🔍 TC-SQL-102 – SQL injection via search field

**Title:** Inject SQL into search input  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automated  
**Preconditions:** Search field must query database  

| Step | Action                     | Expected Result                          |
|------|----------------------------|-------------------------------------------|
| 1    | Open search page           | Field is visible                          |
| 2    | Enter `'; DROP TABLE users;--` | Input sanitized or rejected         |
| 3    | Submit query               | Error or no effect                        |

**Postconditions:**  
Database remains intact

**Expected Result:**  
System escapes input and prevents query execution

---

## 🌐 TC-SQL-103 – SQL injection in URL parameters

**Title:** Inject SQL via GET parameter  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Not Automatable  
**Preconditions:** URL accepts query parameters  

| Step | Action                                  | Expected Result                          |
|------|-----------------------------------------|-------------------------------------------|
| 1    | Navigate to `?id=1' OR '1'='1`          | Page loads with error or sanitized input |

**Postconditions:**  
No data leakage or unauthorized access

**Expected Result:**  
System validates and escapes URL parameters

---

## 📝 TC-SQL-104 – SQL injection in registration form

**Title:** Inject SQL into registration fields  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Preconditions:** Registration form must be active  

| Step | Action                          | Expected Result                          |
|------|----------------------------------|-------------------------------------------|
| 1    | Open registration form          | Form is visible                           |
| 2    | Enter `Robert'); DROP TABLE users;--` as name | Input rejected or sanitized     |
| 3    | Submit form                     | Error shown or input cleaned              |

**Postconditions:**  
No database impact

**Expected Result:**  
System prevents injection and logs attempt

---

## 🧪 TC-SQL-105 – Blind SQL injection attempt

**Title:** Time-based blind SQL injection  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Preconditions:** Endpoint must respond to queries  

| Step | Action                          | Expected Result                          |
|------|----------------------------------|-------------------------------------------|
| 1    | Send payload `1' AND SLEEP(5)--` | Response time normal                      |

**Postconditions:**  
No delay or data exposure

**Expected Result:**  
System ignores or blocks time-based payloads