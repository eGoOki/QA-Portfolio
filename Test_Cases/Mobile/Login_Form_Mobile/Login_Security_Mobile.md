# 🔐 Mobile Login Form – Security Test Cases

---

> ⚠️ **Note**: These test cases focus on verifying secure login behavior for mobile platforms. They help protect user data, session integrity, and prevent unauthorized access.

---

## 🎯 Scope

These security test scenarios cover:

- 🛡️ Token protection, expiration, and reuse resistance  
- 🧑‍💻 Unauthorized access attempts and brute-force simulation  
- 📲 Session hijack prevention and secure storage validation  
- 📵 Behavior during network interception, MITM conditions  
- 🔁 Logout & session invalidation across multiple devices  

---

### ⛔ Out of Scope

- Functional success/validation flows – see [Login_Positive_Mobile.md](./Login_Positive_Mobile.md)  
- Validation and error messaging – see [Login_Negative_Mobile.md](./Login_Negative_Mobile.md)  
- Edge formatting and usability input – see [Login_Edge_Cases_Mobile.md](./Login_Edge_Cases_Mobile.md)

---

## 🔐 TC-LOGIN-MOB-016 – Login token stored securely

**Title:** Login token storage security  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Security Engineer  
**Estimate:** 2m  
**References:** SEC-MOB-TOKEN-001  
**Preconditions:** Valid user session established

**Steps and Results:**

| Step | Action                         | Expected Result                                   |
|------|--------------------------------|---------------------------------------------------|
| 1    | Complete login with valid credentials | Token stored in Keychain/EncryptedSharedPrefs |
| 2    | Inspect storage method via debugger | Sensitive data is encrypted and inaccessible     |

**Postconditions:** Token is stored securely  
**General Expected Result:** Sensitive credentials are protected in app storage

---

## 🔐 TC-LOGIN-MOB-017 – Token expiration after inactivity

**Title:** Session timeout enforcement  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Security Engineer  
**Estimate:** 3m  
**References:** SEC-MOB-TIMEOUT  
**Preconditions:** Session active, app left idle

**Steps and Results:**

| Step | Action                      | Expected Result                             |
|------|-----------------------------|---------------------------------------------|
| 1    | Stay idle for 30+ minutes   | Token expires                                |
| 2    | Return to app               | User redirected to login screen              |

**Postconditions:** Stale token invalidated  
**General Expected Result:** Expired session requires reauthentication

---

## 🔐 TC-LOGIN-MOB-018 – Reuse of token after logout

**Title:** Token reuse prevention  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Security Engineer  
**Estimate:** 3m  
**References:** SEC-MOB-REUSE  
**Preconditions:** User has logged out manually

**Steps and Results:**

| Step | Action                                | Expected Result                                |
|------|----------------------------------------|------------------------------------------------|
| 1    | Login, then logout                     | Session token invalidated                      |
| 2    | Attempt API call with cached token     | API returns 401 Unauthorized                   |

**Postconditions:** Revoked token unusable  
**General Expected Result:** Token revoked at logout; reuse blocked

---

## 🔐 TC-LOGIN-MOB-019 – Multiple failed login attempts

**Title:** Brute-force mitigation  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Security Engineer  
**Estimate:** 2m  
**References:** SEC-MOB-THROTTLE  
**Preconditions:** Test account exists

**Steps and Results:**

| Step | Action                          | Expected Result                           |
|------|----------------------------------|-------------------------------------------|
| 1    | Perform 5 failed login attempts  | Rate-limiting or captcha is triggered     |
| 2    | Continue trying with wrong password | Further attempts blocked temporarily   |

**Postconditions:** Login throttled  
**General Expected Result:** App prevents excessive brute-force attempts

---

## 🔐 TC-LOGIN-MOB-020 – Login over insecure network

**Title:** HTTPS enforcement on login  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Security Engineer  
**Estimate:** 2m  
**References:** SEC-MOB-SSL-020  
**Preconditions:** Device connected via insecure Wi-Fi

**Steps and Results:**

| Step | Action                       | Expected Result                              |
|------|-------------------------------|----------------------------------------------|
| 1    | Attempt login via untrusted network | App enforces HTTPS / SSL pinning         |
| 2    | Inspect traffic              | Credentials are not exposed; no plaintext    |

**Postconditions:** Login protected via encryption  
**General Expected Result:** Network-based interception is blocked