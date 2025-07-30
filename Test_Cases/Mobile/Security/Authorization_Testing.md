# 🚦 Authorization Testing – Mobile QA Test Cases

This section focuses on verifying that users can only access resources and perform actions permitted by their roles, ensuring proper enforcement of access control policies.

---

## 🎯 Scope

These test cases cover:

- 🧪 Vertical and horizontal privilege escalation  
- 🧠 Role-based access control (RBAC) validation  
- 🔐 API endpoint permission enforcement  
- 🧵 Forced browsing and IDOR scenarios  
- 📂 Parameter tampering for access bypass

---

### ⛔ Out of Scope

- [**Authentication logic flaws**](Authentication_Bypass.md)  
- [**Session token and cookie handling**](Session_Management.md)  
- [**Client-side role manipulation**](Reverse_Engineering.md)

---

## 🚦 TC-SEC-AUTHZ-001 – Horizontal privilege escalation

**Title:** Accessing peer user data without permission  
**Section:** Authorization_Testing  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-WSTG-ATHZ-01  
**Preconditions:** Logged in as User A

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Modify request to access User B | Server should reject unauthorized access |
| 2    | Observe response                | Data returned for User B                 |

**Postconditions:** Peer data exposed  
**General Expected Result:** Access must be scoped to user identity

---

## 🚦 TC-SEC-AUTHZ-002 – Vertical privilege escalation

**Title:** Regular user accesses admin-only endpoint  
**Section:** Authorization_Testing  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-WSTG-ATHZ-02  
**Preconditions:** Logged in as non-admin

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Call admin API `/admin/users`   | Server should return 403 Forbidden       |
| 2    | Observe response                | Admin data returned                      |

**Postconditions:** Role boundaries violated  
**General Expected Result:** Role checks must be enforced server-side

---

## 🚦 TC-SEC-AUTHZ-003 – Forced browsing to restricted page

**Title:** Accessing hidden admin page via direct URL  
**Section:** Authorization_Testing  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 2m  
**References:** OWASP-WSTG-ATHZ-03  
**Preconditions:** Page not linked in UI

| Step | Action                          | Expected Result                          |
|------|--------------------------------