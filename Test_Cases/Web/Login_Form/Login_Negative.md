# ❌ Negative Login Test Cases

---

> ⚠️ **Note**: The test cases in this repository are provided as examples only. Each software project may have its own conventions regarding test case structure, required fields, naming formats, documentation standards, and writing style. These samples reflect one possible approach and are not intended as the only correct format.

---

## 🎯 Scope

The negative login test cases cover:

- ❌ **Input validation**: empty fields, malformed email formats, invalid characters  
- 🔐 **Authentication failures**: incorrect credentials, expired passwords, locked accounts  
- 🚫 **Security enforcement**: brute-force protection, rate limiting, generic error messaging  
- 🌐 **System feedback**: clear error messages, prevention of information leakage  
- 🧪 **Functional robustness**: rejection of invalid login attempts under various conditions  

---

## 📄 Table of Contents

- [TC-LOGIN-101 – Login with empty fields](#tc-login-101--login-with-empty-fields)  
- [TC-LOGIN-102 – Login with invalid email format](#tc-login-102--login-with-invalid-email-format)  
- [TC-LOGIN-103 – Login with incorrect credentials](#tc-login-103--login-with-incorrect-credentials)  
- [TC-LOGIN-104 – Login attempt with expired password](#tc-login-104--login-attempt-with-expired-password)  
- [TC-LOGIN-105 – Login attempt for locked account](#tc-login-105--login-attempt-for-locked-account)  
- [TC-LOGIN-106 – Login with excessive failed attempts (rate limiting)](#tc-login-106--login-with-excessive-failed-attempts-rate-limiting)  
- [TC-LOGIN-107 – Login with leading/trailing spaces](#tc-login-107--login-with-leadingtrailing-spaces)  
- [TC-LOGIN-108 – Login with wrong casing](#tc-login-108--login-with-wrong-casing)  
- [TC-LOGIN-109 – Login with special characters in username](#tc-login-109--login-with-special-characters-in-username)  

---

## 🚫 TC-LOGIN-101 – Login with empty fields

**Title:** Login attempt with no credentials  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Validation  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Engineer  
**Estimate:** 1m  
**References:** REQ-AUTH-VAL-001  
**Preconditions:** Login form must be accessible  

**Steps and Results:**

| Step | Action             | Expected Result                         |
|------|--------------------|------------------------------------------|
| 1    | Open login page    | Form is visible                         |
| 2    | Leave fields empty | No input accepted                       |
| 3    | Click “Login”      | Validation error: “Fields cannot be empty” |

**Postconditions:**  
No login occurs, system displays validation error

**General Expected Result:**  
System prevents login attempt and shows required field error

---

## 📧 TC-LOGIN-102 – Login with invalid email format

**Title:** Login attempt with malformed email  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Validation  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-AUTH-VAL-002  
**Preconditions:** Login form is active and accepts input  

**Steps and Results:**

| Step | Action                         | Expected Result                                     |
|------|--------------------------------|------------------------------------------------------|
| 1    | Open login page                | Form is rendered                                    |
| 2    | Enter invalid email (e.g., `user@com`) | Format validation triggers                   |
| 3    | Enter any password             | Password accepted                                   |
| 4    | Click “Login”                  | Error: “Invalid email format” is displayed          |

**Postconditions:**  
Login is blocked due to invalid email format

**General Expected Result:**  
System rejects login attempt and shows clear email format error

---

## 🔐 TC-LOGIN-103 – Login with incorrect credentials

**Title:** Login attempt with incorrect username/password  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security / Functional  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-AUTH-003  
**Preconditions:** Valid user must exist; incorrect credentials used  

**Steps and Results:**

| Step | Action                               | Expected Result                             |
|------|--------------------------------------|----------------------------------------------|
| 1    | Open login page                      | Form displayed                               |
| 2    | Enter incorrect username/password    | Input accepted                               |
| 3    | Click “Login”                        | Error: “Username or password is incorrect”   |

**Postconditions:**  
Authentication fails; login attempt denied

**General Expected Result:**  
System responds with generic error to prevent info disclosure

---

## ⏰ TC-LOGIN-104 – Login attempt with expired password

**Title:** Login attempt using expired password  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Draft  
**Defects:** [DEF-309](../../../Bug_Reports/DEF-309-expired-password-login.md)  
**Execution Status:** Failed  
**Automation:** Automation Queue  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-PWD-EXP-001  
**Preconditions:** User must exist with expired password status  

**Steps and Results:**

| Step | Action                       | Expected Result                                       |
|------|------------------------------|--------------------------------------------------------|
| 1    | Open login page              | Form is visible                                       |
| 2    | Enter expired password       | Input accepted                                        |
| 3    | Click “Login”                | Error: “Your password has expired. Reset required.”   |

**Postconditions:**  
User prompted to reset password via recovery flow

**General Expected Result:**  
System blocks login and guides user toward password reset

---

## 🔒 TC-LOGIN-105 – Login attempt for locked account

**Title:** Attempt to login with locked user profile  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Cannot be Automated  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-LOCK-ACCOUNT-011  
**Preconditions:** Target account must be marked as locked  

**Steps and Results:**

| Step | Action                        | Expected Result                                  |
|------|-------------------------------|--------------------------------------------------|
| 1    | Open login page               | Page is loaded                                  |
| 2    | Enter locked account details  | Input is accepted                               |
| 3    | Click “Login”                 | Error: “Your account is locked. Contact support.” |

**Postconditions:**  
Login denied due to locked status; support escalation required

**General Expected Result:**  
User cannot proceed; account state enforced with clear message

---

## 🚨 TC-LOGIN-106 – Login with excessive failed attempts (rate limiting)

**Title:** Trigger lockout after repeated failures  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security / Stress  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-SEC-LIMIT-017  
**Preconditions:** Login system must implement brute-force protection  

**Steps and Results:**

| Step | Action                            | Expected Result                                  |
|------|-----------------------------------|--------------------------------------------------|
| 1    | Open login page                   | Form is shown                                    |
| 2    | Enter incorrect credentials x5    | Errors shown each time                           |
| 3    | Attempt login again               | Error: “Too many failed attempts. Try later.”    |

**Postconditions:**  
Account access temporarily blocked due to rate limiting

**General Expected Result:**  
System enforces lockout window; login attempts paused for duration

---

## 🧼 TC-LOGIN-107 – Login with leading/trailing spaces

**Title:** Login attempt with extra spaces in credentials  
**Section:** Login_Form  
**Type:** Validation  
**Priority:** Medium  
**Status:** Draft  
**Automation:** Automation Queue  
**Estimate:** 2m  
**Preconditions:** User exists; credentials contain leading/trailing spaces  

**Steps and Results:**

| Step | Action                                 | Expected Result                                  |
|------|----------------------------------------|--------------------------------------------------|
| 1    | Open login page                        | Form is displayed                                |
| 2    | Enter username with leading space      | Input accepted                                   |
| 3    | Enter password with trailing space     | Input accepted                                   |
| 4    | Click “Login”                          | Error: “Invalid credentials” or normalization    |

**Postconditions:**  
Login fails due to incorrect credentials after trimming or mismatch

**General Expected Result:**  
System either trims input or rejects login with clear error

---

## 🔡 TC-LOGIN-108 – Login with wrong casing

**Title:** Login attempt with incorrect casing in email  
**Section:** Login_Form  
**Type:** Validation / Security  
**Priority:** Medium  
**Status:** Draft  
**Automation:** Automation Queue  
**Estimate:** 2m  
**Preconditions:** User exists; casing is incorrect in input  

**Steps and Results:**

| Step | Action                          | Expected Result                             |
|------|----------------------------------|----------------------------------------------|
| 1    | Open login page                 | Form is visible                              |
| 2    | Enter email in uppercase        | Input accepted                               |
| 3    | Enter correct password          | Input accepted                               |
| 4    | Click “Login”                   | Error: “Invalid credentials”                 |

**Postconditions:**  
Login fails due to case sensitivity mismatch

**General Expected Result:**  
System enforces case sensitivity or normalizes input

---

## 🧨 TC-LOGIN-109 – Login with special characters in username

**Title:** Login attempt with unsupported characters in username  
**Section:** Login_Form  
**Type:** Validation / Security  
**Priority:** Medium  
**Status:** Draft  
**Automation:** Automation Queue  
**Estimate:** 2m  
**Preconditions:** Login form must allow input  

**Steps and Results:**

| Step | Action                          | Expected Result                             |
|------|----------------------------------|----------------------------------------------|
| 1    | Open login page                 | Form is rendered                             |
| 2    | Enter username with `!@#$%^&*()`| Validation triggers                          |
| 3    | Enter any password              | Input accepted                               |
| 4    | Click “Login”                   | Error: “Invalid characters in username”      |

**Postconditions:**  
Login blocked due to invalid characters

**General Expected Result:**  
System rejects input and displays validation error

---