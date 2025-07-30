# 🔓 Authentication Bypass – Mobile QA Test Cases

This section focuses on identifying scenarios where authentication mechanisms can be bypassed due to insecure logic, missing validations, or excessive client-side trust.

---

## 🎯 Scope

These test cases cover:

- 🔐 OTP and MFA bypass techniques  
- 🧠 Logic flaws in authentication flow  
- 🛠️ Missing server-side validation  
- 📲 Insecure mobile API endpoints  
- 🧪 Session and token manipulation

---

### ⛔ Out of Scope

- [**Authorization and role-based access**](Authorization_Testing.md)  
- [**Biometric and device-level bypasses**](Biometric_Access.md)  
- [**Login form validation**](Login_Security.md)

---

## 🔐 TC-SEC-AUTH-001 – OTP bypass via response manipulation

**Title:** OTP verification bypassed by editing server response  
**Section:** Authentication_Bypass  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-MOB-AUTH-001  
**Preconditions:** OTP flow enabled; proxy tool configured

**Steps and Results:**

| Step | Action                                      | Expected Result                          |
|------|---------------------------------------------|------------------------------------------|
| 1    | Submit invalid OTP                          | Server returns failure response          |
| 2    | Intercept and modify response to success    | App accepts manipulated response         |
| 3    | Proceed to next screen                      | Access granted without valid OTP         |

**Postconditions:** OTP step bypassed  
**General Expected Result:** App must reject tampered responses

---

## 🔐 TC-SEC-AUTH-002 – OTP bypass via missing server-side check

**Title:** OTP verification skipped due to stateless backend  
**Section:** Authentication_Bypass  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-AUTH-002  
**Preconditions:** OTP flow triggered

**Steps and Results:**

| Step | Action                              | Expected Result                          |
|------|-------------------------------------|------------------------------------------|
| 1    | Submit request without OTP field    | Server should reject the request         |
| 2    | Observe response                    | Server accepts and proceeds              |

**Postconditions:** OTP logic not enforced  
**General Expected Result:** Server must validate OTP presence

---

## 🔐 TC-SEC-AUTH-003 – Session token reused after logout

**Title:** Reuse of expired session token grants access  
**Section:** Authentication_Bypass  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-AUTH-003  
**Preconditions:** Valid session token captured

**Steps and Results:**

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Logout from app                 | Token should be invalidated              |
| 2    | Use old token to call API       | Server should return unauthorized        |
| 3    | Observe response                | API returns success                      |

**Postconditions:** Session token remains active  
**General Expected Result:** Tokens must expire after logout

---

## 🔐 TC-SEC-AUTH-004 – Login bypass via insecure API endpoint

**Title:** Accessing protected endpoint without authentication  
**Section:** Authentication_Bypass  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-MOB-AUTH-004  
**Preconditions:** API endpoint known

**Steps and Results:**

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Call protected API without token| Server should return 401 Unauthorized    |
| 2    | Observe response                | Server returns valid data                |

**Postconditions:** Endpoint accessible without login  
**General Expected Result:** All APIs must enforce authentication

---

## 🔐 TC-SEC-AUTH-005 – Bypass via hardcoded admin flag

**Title:** Admin access granted using client-side flag  
**Section:** Authentication_Bypass  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-AUTH-005  
**Preconditions:** App uses client-side role flags

**Steps and Results:**

| Step | Action                              | Expected Result                          |
|------|-------------------------------------|------------------------------------------|
| 1    | Modify request to include `isAdmin=true` | Server should ignore client flag     |
| 2    | Submit request                      | Server grants admin access               |

**Postconditions:** Role escalation via client input  
**General Expected Result:** Roles must be verified server-side

---

## 🔐 TC-SEC-AUTH-006 – JWT tampering without signature validation

**Title:** Modified JWT accepted without verifying signature  
**Section:** Authentication_Bypass  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-MOB-AUTH-006  
**Preconditions:** App uses JWT for session management

**Steps and Results:**

| Step | Action                              | Expected Result                          |
|------|-------------------------------------|------------------------------------------|
| 1    | Decode JWT and change role to admin| Server should reject tampered token      |
| 2    | Submit modified token               | Server accepts and grants access         |

**Postconditions:** JWT accepted without verification  
**General Expected Result:** JWT must be validated with signature