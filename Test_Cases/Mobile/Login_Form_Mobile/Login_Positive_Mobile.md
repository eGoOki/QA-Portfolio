# ✅ Mobile Login Form – Positive Test Cases

---

> ⚠️ **Note**: These test cases are examples. Real-world implementations may differ by project structure, naming, or QA process.

---

## 🎯 Scope

These mobile test cases cover:

- 🔐 Authentication with valid credentials and biometric login  
- ⚙️ Session management and restoration  
- 📲 OAuth flows and third-party identity provider integration  
- 🧠 “Remember Me” and autofill behavior  
- 🎛️ UI behavior during login interaction

---

### ⛔ Out of Scope

- **Security and edge-case behavior** – see [Login_Security.md](./Login_Security.md)  
- **Negative validation and error messaging** – see [Login_Negative_Mobile.md](./Login_Negative_Mobile.md)  
- **Edge formatting and usability input** – see [Login_Edge_Cases_Mobile.md](./Login_Edge_Cases_Mobile.md)

---

## 🔐 TC-LOGIN-MOB-001 – Login with valid credentials

**Title:** Login with valid credentials  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-MOB-AUTH-001  
**Preconditions:** App is installed and launched; valid user credentials exist

**Steps and Results:**

| Step | Action                         | Expected Result                                   |
|------|--------------------------------|---------------------------------------------------|
| 1    | Launch the app                 | Splash screen appears                             |
| 2    | Open login screen              | Login form is displayed                           |
| 3    | Enter valid credentials        | Input accepted without error                      |
| 4    | Tap “Login”                    | User is authenticated and redirected to dashboard |

**Postconditions:** Session token created  
**General Expected Result:** User authenticated and granted access

---

## 🔐 TC-LOGIN-MOB-002 – Biometric login (Face ID / Fingerprint)

**Title:** Biometric login (Face ID / Fingerprint)  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-MOB-BIO-002  
**Preconditions:** Biometric login is configured on device and app

**Steps and Results:**

| Step | Action               | Expected Result                               |
|------|----------------------|-----------------------------------------------|
| 1    | Launch app           | Login screen appears                          |
| 2    | Tap “Use Biometric”  | Face ID/Fingerprint prompt is shown           |
| 3    | Confirm authentication | User is authenticated and redirected to dashboard |

**Postconditions:** Biometric mapped to session token  
**General Expected Result:** Secure login without password entry

---

## 🔐 TC-LOGIN-MOB-003 – Session restore after app relaunch

**Title:** Session restore after app relaunch  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-MOB-SESSION-003  
**Preconditions:** Valid session must be present before app closure

**Steps and Results:**

| Step | Action              | Expected Result                            |
|------|---------------------|--------------------------------------------|
| 1    | Kill and relaunch app | Splash screen loads                        |
| 2    | Observe login state | User bypasses login screen; dashboard shown |

**Postconditions:** Session is persisted using secure storage  
**General Expected Result:** Seamless session continuity

---

## 🔐 TC-LOGIN-MOB-004 – Login with remembered credentials

**Title:** Login with remembered credentials  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Usability  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-MOB-REMEMBER-004  
**Preconditions:** User previously enabled “Remember Me” option

**Steps and Results:**

| Step | Action                  | Expected Result                             |
|------|--------------------------|---------------------------------------------|
| 1    | Open login screen        | Email field pre-filled                      |
| 2    | Tap “Login”              | User authenticated with stored credentials  |

**Postconditions:** Fast login via local data  
**General Expected Result:** Reduced friction for return login

---

## 🔐 TC-LOGIN-MOB-005 – OAuth login via Google

**Title:** OAuth login via Google  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Not Automated  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-MOB-OAUTH-005  
**Preconditions:** Google OAuth flow is integrated and active

**Steps and Results:**

| Step | Action                    | Expected Result                                   |
|------|----------------------------|---------------------------------------------------|
| 1    | Tap “Login with Google”    | OAuth consent screen opens                        |
| 2    | Select valid account       | Access granted; token issued                      |
| 3    | App returns to dashboard   | User authenticated using third-party credentials  |

**Postconditions:** OAuth token stored securely  
**General Expected Result:** Login completed via third-party identity