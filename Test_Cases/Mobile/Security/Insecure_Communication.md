# 📡 Insecure Communication – Mobile QA Test Cases

This section focuses on identifying vulnerabilities where sensitive data is transmitted over insecure channels, making it susceptible to interception, tampering, or unauthorized access during transit.

---

## 🎯 Scope

These test cases cover:

- 🔐 Missing or misconfigured SSL/TLS  
- 🧠 Improper certificate validation  
- 📲 Transmission of sensitive data over HTTP  
- 🧪 Weak cipher suites and handshake flaws  
- 🛰️ Exposure via alternate channels (SMS, logs, push)

---

### ⛔ Out of Scope

- [**Local data storage vulnerabilities**](Insecure_Data_Storage.md)  
- [**Session token and cookie handling**](Session_Management.md)  
- [**Authentication logic flaws**](Authentication_Bypass.md)

---

## 📡 TC-SEC-COMM-001 – Sensitive data sent over HTTP

**Title:** Transmission of credentials over unencrypted HTTP  
**Section:** Insecure_Communication  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 4m  
**References:** OWASP-MOB-COMM-001  
**Preconditions:** App login endpoint uses HTTP

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Intercept login request         | Credentials visible in plaintext         |
| 2    | Replay request                  | Server accepts and logs in               |

**Postconditions:** Credentials exposed in transit  
**General Expected Result:** All sensitive data must be encrypted in transit

---

## 📡 TC-SEC-COMM-002 – Accepting invalid SSL certificate

**Title:** App accepts self-signed or expired certificate  
**Section:** Insecure_Communication  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-COMM-002  
**Preconditions:** Proxy tool configured with invalid cert

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Intercept HTTPS traffic         | Replace cert with self-signed            |
| 2    | Observe app behavior            | App accepts and continues communication  |

**Postconditions:** No certificate validation  
**General Expected Result:** App must reject invalid certificates

---

## 📡 TC-SEC-COMM-003 – Weak TLS handshake negotiation

**Title:** App negotiates weak cipher suite  
**Section:** Insecure_Communication  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-COMM-003  
**Preconditions:** TLS handshake observable

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Monitor TLS handshake           | Observe cipher suite negotiation         |
| 2    | Identify weak cipher            | App accepts insecure encryption          |

**Postconditions:** Weak encryption in use  
**General Expected Result:** App must enforce strong cipher suites

---

## 📡 TC-SEC-COMM-004 – Sensitive data in push notification payload

**Title:** PII exposed in push notification content  
**Section:** Insecure_Communication  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 2m  
**References:** OWASP-MOB-COMM-004  
**Preconditions:** Push notifications enabled

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Trigger notification            | Observe payload                          |
| 2    | Review content                  | Sensitive data visible                   |

**Postconditions:** PII exposed via notification  
**General Expected Result:** Push payloads must exclude sensitive data

---

## 📡 TC-SEC-COMM-005 – Session token sent via SMS

**Title:** Session identifier transmitted over SMS  
**Section:** Insecure_Communication  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-COMM-005  
**Preconditions:** SMS-based login flow enabled

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Trigger SMS login               | Receive SMS                              |
| 2    | Review message content          | Session token visible                    |

**Postconditions:** Token exposed via insecure channel  
**General Expected Result:** Tokens must not be sent via SMS

---

## 📡 TC-SEC-COMM-006 – No SSL pinning implemented

**Title:** App does not validate server identity via pinning  
**Section:** Insecure_Communication  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** Security QA  
**Estimate:** 3m  
**References:** OWASP-MOB-COMM-006  
**Preconditions:** SSL pinning not configured

| Step | Action                          | Expected Result                          |
|------|---------------------------------|------------------------------------------|
| 1    | Replace server cert             | App accepts new cert                     |
| 2    | Observe connection              | Communication continues                  |

**Postconditions:** No pinning validation  
**General Expected Result:** App must enforce SSL pinning for sensitive flows