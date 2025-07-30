# ❌ Mobile Login Form – Negative Test Cases

---

> ⚠️ **Note**: These are illustrative mobile test cases. Each app may apply different validation logic and security policies.

---

## 🎯 Scope

Negative login test cases verify:

- 🚫 Input validation errors  
- 🔒 Blocked user handling  
- ✖️ Credential mismatches  
- 📵 Network failure scenarios

---

### ⛔ Out of Scope

- **Security and edge-case behavior** – see [Login_Security.md](./Login_Security.md)  
- **Positive validation success flows** – see [Login_Positive_Mobile.md](./Login_Positive_Mobile.md)  
- **Edge formatting and usability input** – see [Login_Edge_Cases_Mobile.md](./Login_Edge_Cases_Mobile.md)

---

## 🔐 TC-LOGIN-MOB-006 – Empty credentials

**Title:** Empty credentials  
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
**References:** VAL-MOB-LOGIN-EMPTY  
**Preconditions:** Login screen is visible

**Steps and Results:**

| Step | Action                  | Expected Result                                |
|------|--------------------------|------------------------------------------------|
| 1    | Leave email and password blank | “Required fields” validation message appears |
| 2    | Tap “Login”              | Login is blocked; no network call sent        |

**Postconditions:** No authentication attempted  
**General Expected Result:** Validation blocks empty input submission

---

## 🔐 TC-LOGIN-MOB-007 – Invalid email format

**Title:** Invalid email format  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Validation  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** VAL-MOB-EMAIL-FORMAT  
**Preconditions:** App is open and form is visible

**Steps and Results:**

| Step | Action                     | Expected Result                      |
|------|-----------------------------|--------------------------------------|
| 1    | Enter “user@invalid” in email field | Format validation error shown |
| 2    | Enter password and tap “Login” | Submission blocked; email invalid |

**Postconditions:** User stays on login screen  
**General Expected Result:** Invalid email blocked at form level

---

## 🔐 TC-LOGIN-MOB-008 – Incorrect credentials

**Title:** Incorrect credentials  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-MOB-AUTH-FAIL  
**Preconditions:** Valid account exists; wrong password is used

**Steps and Results:**

| Step | Action                       | Expected Result                             |
|------|-------------------------------|---------------------------------------------|
| 1    | Enter valid email + wrong password | “Invalid credentials” error message appears |
| 2    | Retry login                  | Same message shown after each attempt       |

**Postconditions:** Authentication fails  
**General Expected Result:** User is not granted access; API returns 401/403

---

## 🔐 TC-LOGIN-MOB-009 – Blocked account login attempt

**Title:** Blocked account login attempt  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-MOB-USER-BLOCKED  
**Preconditions:** Test account is marked as blocked

**Steps and Results:**

| Step | Action               | Expected Result                       |
|------|-----------------------|---------------------------------------|
| 1    | Enter valid credentials | Error “Account is blocked” is displayed |
| 2    | Attempt to retry login | Same rejection message persists       |

**Postconditions:** No session token generated  
**General Expected Result:** Backend enforces access restriction

---

## 🔐 TC-LOGIN-MOB-010 – Offline login attempt

**Title:** Offline login attempt  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-MOB-OFFLINE-BLOCK  
**Preconditions:** Device is disconnected from internet

**Steps and Results:**

| Step | Action              | Expected Result                             |
|------|----------------------|---------------------------------------------|
| 1    | Launch app offline   | Offline alert shown or no network detected  |
| 2    | Enter valid credentials and tap “Login” | Network error toast shown; login not processed |

**Postconditions:** Login blocked due to connectivity  
**General Expected Result:** Proper offline behavior with retry prompt