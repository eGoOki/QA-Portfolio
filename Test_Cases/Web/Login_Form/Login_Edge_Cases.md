# 🧪 Login Edge Case Test Cases

---

> ⚠️ **Note**: These test cases explore non-obvious, boundary-level behaviors during the login process. They complement functional and negative test suites by covering rare but plausible user flows.

---

## 🎯 Scope

The edge case login test cases cover:

- 🧩 **Boundary inputs**: uppercase emails, whitespace trimming, special characters  
- 🔁 **Session anomalies**: re-login during active session, login post password change  
- 📋 **Usability quirks**: clipboard paste, input formatting, accessibility behaviors  
- 🛠️ **System states**: login during maintenance, sync delays, unexpected flows  
- 🔐 **Security tolerance**: complex password handling, input normalization  

---

## 📄 Table of Contents

- [TC-LOGIN-201 – Login with email in uppercase](#tc-login-201--login-with-email-in-uppercase)  
- [TC-LOGIN-202 – Login with leading/trailing spaces in credentials](#tc-login-202--login-with-leadingtrailing-spaces-in-credentials)  
- [TC-LOGIN-203 – Login with special characters in password](#tc-login-203--login-with-special-characters-in-password)  
- [TC-LOGIN-204 – Login while session is already active](#tc-login-204--login-while-session-is-already-active)  
- [TC-LOGIN-205 – Login using password copy-paste](#tc-login-205--login-using-password-copy-paste)  
- [TC-LOGIN-206 – Login just after password change](#tc-login-206--login-just-after-password-change)  
- [TC-LOGIN-207 – Login attempt during system maintenance](#tc-login-207--login-attempt-during-system-maintenance)  

---

## 🔡 TC-LOGIN-201 – Login with email in uppercase

**Title:** Email field case insensitivity  
**Type:** Usability / Validation  
**Status:** Approved  
**Priority:** Medium  
**Estimate:** 2m  
**Preconditions:** Valid user exists  

| Step | Action                                  | Expected Result                            |
|------|-----------------------------------------|---------------------------------------------|
| 1    | Open login page                         | Form is displayed                          |
| 2    | Enter EMAIL in UPPERCASE (e.g. `USER@EXAMPLE.COM`) | Input accepted                     |
| 3    | Enter valid password                    | Input accepted                              |
| 4    | Click “Login”                           | Login successful; email case ignored       |

**Postconditions:** Authenticated session started  

**General Expected Result:**  
Email comparison should be case-insensitive

---

## 🔲 TC-LOGIN-202 – Login with leading/trailing spaces in credentials

**Title:** Stripped whitespace in login fields  
**Type:** Usability / Validation  
**Status:** Approved  
**Priority:** High  
**Estimate:** 2m  
**Preconditions:** User knows correct credentials  

| Step | Action                                      | Expected Result                           |
|------|---------------------------------------------|--------------------------------------------|
| 1    | Navigate to login                           | Form is shown                             |
| 2    | Input email with spaces (` user@example.com `) | Trimmed during validation              |
| 3    | Input password with spaces                  | Trimmed or error shown                    |
| 4    | Submit credentials                          | Login successful or error message appears |

**Postconditions:** User logs in without error  

**General Expected Result:**  
System should trim spaces or warn user clearly

---

## 🔣 TC-LOGIN-203 – Login with special characters in password

**Title:** Support for complex passwords  
**Type:** Security  
**Status:** Approved  
**Priority:** High  
**Estimate:** 2m  
**Preconditions:** Password includes special symbols  

| Step | Action                          | Expected Result                                 |
|------|---------------------------------|--------------------------------------------------|
| 1    | Go to login page                | Form is visible                                 |
| 2    | Input email                     | Accepted                                        |
| 3    | Input password like `P@$$w0rd!` | Input accepted                                 |
| 4    | Click “Login”                   | Auth successful if password matches exactly     |

**Postconditions:** Login success if symbols are matched  

**General Expected Result:**  
Symbols should be accepted and validated correctly

---

## 🔄 TC-LOGIN-204 – Login while session is already active

**Title:** Secondary login during active session  
**Type:** Functional  
**Status:** Draft  
**Priority:** Low  
**Estimate:** 3m  
**Preconditions:** First session must exist  

| Step | Action                          | Expected Result                               |
|------|---------------------------------|------------------------------------------------|
| 1    | Login as User A in one tab      | Session A established                         |
| 2    | Open new tab                    | Session continues                              |
| 3    | Try login again as same user    | System may redirect, block or refresh session  |

**Postconditions:** Session behavior varies by design  

**General Expected Result:**  
System should either preserve, reset or warn user on re-authentication

---

## 📋 TC-LOGIN-205 – Login using password copy-paste

**Title:** Password input via clipboard  
**Type:** Usability  
**Status:** Approved  
**Priority:** Medium  
**Estimate:** 1m  
**Preconditions:** Clipboard contains password   

| Step | Action                  | Expected Result                              |
|------|-------------------------|-----------------------------------------------|
| 1    | Copy valid password     | Clipboard stores correct password             |
| 2    | Paste into field        | Field allows paste and stores input           |
| 3    | Click “Login”           | Authenticated successfully                    |

**Postconditions:** User successfully logs in 

**General Expected Result:**  
Paste functionality should be supported for accessibility

---

## 🕐 TC-LOGIN-206 – Login just after password change

**Title:** Login with updated password immediately  
**Type:** Functional  
**Status:** Approved  
**Priority:** High  
**Estimate:** 2m  
**Preconditions:** User has changed password just moments ago   

| Step | Action                        | Expected Result                           |
|------|-------------------------------|--------------------------------------------|
| 1    | Change password               | System confirms success                   |
| 2    | Return to login page          | Form is refreshed                         |
| 3    | Enter new password            | Input accepted                            |
| 4    | Submit login                  | User logged in successfully               |

**Postconditions:** Login is permitted with new credentials 

**General Expected Result:**  
System syncs password changes instantly

---

## 🛠️ TC-LOGIN-207 – Login attempt during system maintenance

**Title:** Login during downtime  
**Type:** Stability  
**Status:** Draft  
**Priority:** High  
**Estimate:** 1m  
**Preconditions:** Maintenance window is active  

| Step | Action                 | Expected Result                                       |
|------|------------------------|--------------------------------------------------------|
| 1    | Visit login page       | System shows maintenance banner                      |
| 2    | Attempt login          | Error: “Login disabled due to maintenance”           |

**Postconditions:** Access blocked with appropriate message  

**General Expected Result:**  
User cannot access system during scheduled downtime

---

## 🌍 TC-LOGIN-208 – Error message localization based on browser language

**Title:** Localized error messages based on user language  
**Type:** Usability / Localization  
**Status:** Draft  
**Priority:** Medium  
**Estimate:** 2m  
**Preconditions:** Browser language is set to non-default (e.g., French)  

| Step | Action                          | Expected Result                                      |
|------|----------------------------------|------------------------------------------------------|
| 1    | Set browser language to French  | UI adapts to French locale                          |
| 2    | Enter incorrect credentials     | Error message appears in French (e.g., “Mot de passe incorrect”) |

**Postconditions:** Error messages appear in selected language  

**General Expected Result:**  
System detects browser language and displays localized error messages

---

## 🧭 TC-LOGIN-209 – RTL language layout and alignment

**Title:** Right-to-left layout support for login form  
**Type:** UI / Localization  
**Status:** Draft  
**Priority:** Low  
**Estimate:** 2m  
**Preconditions:** Browser language set to RTL language (e.g., Arabic)   

| Step | Action                          | Expected Result                                      |
|------|----------------------------------|------------------------------------------------------|
| 1    | Set browser language to Arabic  | UI switches to RTL layout                           |
| 2    | Open login page                 | Labels and fields are right-aligned                 |
| 3    | Trigger validation error        | Error message appears in Arabic and aligned properly |

**Postconditions:** Login form respects RTL alignment 

**General Expected Result:**  
Login form layout and messages adapt to RTL formatting and language

---

## ⌛ TC-LOGIN-210 – Session timeout after inactivity

**Title:** Auto logout after inactivity period  
**Type:** Functional / Security  
**Status:** Draft  
**Priority:** High  
**Estimate:** 2m  
**Preconditions:** User is logged in and remains inactive for configured timeout duration  

| Step | Action                          | Expected Result                                 |
|------|----------------------------------|--------------------------------------------------|
| 1    | Login and remain idle           | Session remains active initially                |
| 2    | Wait for timeout (e.g., 15 min) | System detects inactivity                       |
| 3    | Interact with app               | User is redirected to login page                |

**Postconditions:** Session is terminated; user redirected to login  

**General Expected Result:**  
System should auto-expire session and require re-authentication

---

## 🔃 TC-LOGIN-211 – Token refresh during active session

**Title:** Silent token renewal before expiry  
**Type:** Security / Integration  
**Status:** Draft  
**Priority:** Medium  
**Estimate:** 2m  
**Preconditions:** User is logged in; token has short lifespan (e.g., 5 min)   

| Step | Action                          | Expected Result                                 |
|------|----------------------------------|--------------------------------------------------|
| 1    | Login and stay active           | Session is valid                                |
| 2    | Wait until token nears expiry   | Background refresh is triggered                 |
| 3    | Continue using app              | No logout; new token is issued silently         |

**Postconditions:** Token is refreshed without user interruption 

**General Expected Result:**  
System should refresh token seamlessly before expiration

---

## 🖥️ TC-LOGIN-212 – Login from multiple browser tabs

**Title:** Session consistency across tabs  
**Type:** Functional / Usability  
**Status:** Draft  
**Priority:** Medium  
**Estimate:** 2m  
**Preconditions:** User logs in on one tab; opens additional tabs    

| Step | Action                          | Expected Result                                 |
|------|----------------------------------|--------------------------------------------------|
| 1    | Login in Tab A                  | Session A is active                             |
| 2    | Open Tab B                      | Session is shared or revalidated                |
| 3    | Perform action in Tab B         | Action succeeds without re-authentication       |

**Postconditions:** Session state is preserved or synced

**General Expected Result:**  
Session should persist across tabs or prompt re-login if isolated