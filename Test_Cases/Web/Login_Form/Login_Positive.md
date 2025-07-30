# ✅ Positive Login Test Cases

---

> ⚠️ **Note**: The test cases in this repository are provided as examples only. Each software project may have its own conventions regarding test case structure, required fields, naming formats, documentation standards, and writing style. These samples reflect one possible approach and are not intended as the only correct format.

---

## 🎯 Scope

The positive login test cases cover:

- 🔐 **Authentication methods**: standard credentials, SSO, magic link, mobile app, biometric & QR login  
- ⚙️ **Session management**: cookie-based auto-login, token exchange flows  
- 📲 **Cross-platform integration**: mobile and third-party auth flows  
- 🎛️ **UI behavior**: login form rendering, redirects, visibility of login states  
- 🧪 **Functional and security validation**: expected outcomes and safe auth flows  

---

### ⛔ Out of Scope

- Negative login scenarios (invalid credentials, input validation errors, etc.)  
- Edge cases (e.g., trimming whitespace, expired sessions, casing issues)  
- Security-specific attacks (e.g., brute-force, token misuse — covered in `Login_Security.md`)

---


## 📄 Table of Contents
- [TC-LOGIN-001 – Login with valid credentials](#tc-login-001--login-with-valid-credentials)
- [TC-LOGIN-002 – Login via SSO](#tc-login-002--login-via-sso)
- [TC-LOGIN-003 – Login via email login link](#tc-login-003--login-via-email-login-link)
- [TC-LOGIN-004 – Login via mobile app](#tc-login-004--login-via-mobile-app)
- [TC-LOGIN-005 – Auto-login via session cookies](#tc-login-005--auto-login-via-session-cookies)
- [TC-LOGIN-006 – Login via biometric or QR-code](#tc-login-006--login-via-biometric-or-qr-code)

---

## 🔐 TC-LOGIN-001 – Login with valid credentials

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
**References:** REQ-AUTH-001  
**Preconditions:** User must exist and have valid login credentials

**Steps and Results:**

| Step | Action                             | Expected Result                                     |
|------|-------------------------------------|-----------------------------------------------------|
| 1    | Open login page                    | Login form is displayed                            |
| 2    | Enter valid username and password | Input is accepted                                  |
| 3    | Click "Login"                      | User is redirected to dashboard with valid session |

**Postconditions:**  
User session is active; access to protected resources is granted

**General Expected Result:**  
User is successfully authenticated and navigated to dashboard; user data is visible

---

## 🔐 TC-LOGIN-002 – Login via SSO

**Title:** Login via Single Sign-On provider  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Integration  
**Priority:** Medium  
**Status:** Waiting Review  
**Defects:** [DEF-217](../../../Bug_Reports/DEF-217-SSO-login-redirect.md)  
**Execution Status:** Failed  
**Automation:** Automation Queue  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-SO-102  
**Preconditions:** SSO provider must be configured and user must have valid SSO account

**Steps and Results:**

| Step | Action                 | Expected Result                                         |
|------|------------------------|----------------------------------------------------------|
| 1    | Click "Login via SSO" | Redirect to provider selection screen                   |
| 2    | Choose provider        | Redirect to provider's login flow                        |
| 3    | Authenticate           | User is authenticated and redirected to app dashboard   |

**Postconditions:**  
User session is created via SSO token exchange

**General Expected Result:**  
User is authenticated through external provider and redirected to application dashboard

---

## 🔐 TC-LOGIN-003 – Login via email login link

**Title:** Login via magic email link  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Security / Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Cannot be Automated  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-AUTH-EMAIL-013  
**Preconditions:** Email system is operational and user email is registered

**Steps and Results:**

| Step | Action                         | Expected Result                                        |
|------|--------------------------------|--------------------------------------------------------|
| 1    | Enter registered email address | System confirms link was sent                         |
| 2    | Receive login email            | Email arrives with clickable magic login link         |
| 3    | Click link                     | User is logged in and redirected to dashboard         |

**Postconditions:**  
User session initiated without password input

**General Expected Result:**  
User is securely authenticated via link and redirected to dashboard

---

## 📱 TC-LOGIN-004 – Login via mobile app

**Title:** Login through authorized mobile application  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Integration / Security  
**Priority:** Medium  
**Status:** Needs Update  
**Defects:** [DEF-108](../../../Bug_Reports/DEF-108-Mobile-app-logini-does-not-result-in-valid-session-token.md)  
**Execution Status:** Failed  
**Automation:** Cannot be Automated  
**Assigned To:** QA Engineer  
**Estimate:** 4m  
**References:** REQ-MOBILE-AUTH-009  
**Preconditions:** Valid mobile app installed and configured

**Steps and Results:**

| Step | Action              | Expected Result                                      |
|------|---------------------|------------------------------------------------------|
| 1    | Open mobile app     | Login screen is shown                               |
| 2    | Login via app       | Access token is generated and sent to backend       |
| 3    | Backend verifies    | Session is created and user gains access            |

**Postconditions:**  
Access token validated, user logged in via mobile flow

**General Expected Result:**  
User is authenticated through mobile app and receives session token

---

## 🍪 TC-LOGIN-005 – Auto-login via session cookies

**Title:** Auto-login using session cookies  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Low  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Engineer  
**Estimate:** 1m  
**References:** REQ-SESSION-004  
**Preconditions:** User has a valid, unexpired session cookie

**Steps and Results:**

| Step | Action                          | Expected Result                             |
|------|----------------------------------|---------------------------------------------|
| 1    | Open browser with session cookie | No login prompt shown                       |
| 2    | Navigate to protected page       | User is auto-authenticated                  |

**Postconditions:**  
Session is resumed; user bypasses login form

**General Expected Result:**  
User is logged in automatically via session persistence

---

## 🔑 TC-LOGIN-006 – Login via biometric or QR-code

**Title:** Login via biometric or QR-code scanner  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Usability / Security / Integration  
**Priority:** Medium  
**Status:** Waiting Review  
**Defects:** —  
**Execution Status:** Not Executed  
**Automation:** Automation Queue  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** REQ-BIO-012  
**Preconditions:** Companion app and biometric/QR scanner must be configured

**Steps and Results:**

| Step | Action                             | Expected Result                                            |
|------|-------------------------------------|------------------------------------------------------------|
| 1    | Choose "Login via QR/Biometric"    | Scanner or QR interface is displayed                      |
| 2    | Scan fingerprint/face or QR code   | Authentication token sent to backend                      |
| 3    | Backend validates token            | User is logged in and redirected to dashboard             |

**Postconditions:**  
Secure login completed without using credentials

**General Expected Result:**  
User successfully logs in via biometric or QR-code with secure token exchange