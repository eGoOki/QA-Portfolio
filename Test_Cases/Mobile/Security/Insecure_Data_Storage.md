# 🔐 Insecure Data Storage – Mobile QA Test Cases

This section focuses on identifying scenarios where sensitive data is stored insecurely on the device, allowing attackers to extract, manipulate, or misuse it through local access or malware.

---

## 🎯 Scope

These test cases cover:

- 🧠 Unencrypted local storage (SharedPrefs, SQLite, Realm)  
- 📂 Sensitive data in logs, backups, and temp files  
- 🔐 Improper use of keystore and cryptographic APIs  
- 📲 External storage exposure  
- 🧪 Hardcoded secrets and credentials

---

### ⛔ Out of Scope

- [**Secure transmission of data**](Insecure_Communication.md)  
- [**Session token and cookie handling**](Session_Management.md)  
- [**Authentication logic flaws**](Authentication_Bypass.md)

---

## 🔐 TC-SEC-IDS-001 – Hardcoded credentials in source code

**Title:** Hardcoded credentials found in app source  
**Section:** Insecure_Data_Storage  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 4m  
**References:** OWASP-MOB-SEC-01  
**Preconditions:** Decompilation tools are installed

**Steps and Results:**

| Step | Action                            | Expected Result                                |
|------|-----------------------------------|------------------------------------------------|
| 1    | Decompile the mobile app          | Source code becomes accessible                 |
| 2    | Search for strings like `password=` | No credentials or secrets should be present   |

**Postconditions:** App code contains no exposed secrets  
**General Expected Result:** Sensitive credentials are not hardcoded

---

## 🔐 TC-SEC-IDS-002 – Plaintext storage in SharedPreferences / NSUserDefaults

**Title:** Sensitive data stored in unencrypted key-value files  
**Section:** Insecure_Data_Storage  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** OWASP-MOB-SEC-02  
**Preconditions:** Logged-in user session is active

**Steps and Results:**

| Step | Action                                    | Expected Result                            |
|------|-------------------------------------------|--------------------------------------------|
| 1    | Open SharedPreferences / NSUserDefaults  | File is readable                            |
| 2    | Search for tokens, passwords or emails   | No sensitive values should be present       |

**Postconditions:** User data not exposed at key-value level  
**General Expected Result:** Sensitive values are encrypted or not stored

---

## 🔐 TC-SEC-IDS-003 – Unencrypted local database storage

**Title:** User data stored unencrypted in SQLite/Realm  
**Section:** Insecure_Data_Storage  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 5m  
**References:** OWASP-MOB-SEC-03  
**Preconditions:** App is installed and used normally

**Steps and Results:**

| Step | Action                         | Expected Result                              |
|------|--------------------------------|----------------------------------------------|
| 1    | Extract database file          | File access succeeds                          |
| 2    | Open file with DB viewer       | Content should be encrypted or unreadable     |

**Postconditions:** Database remains secure even if extracted  
**General Expected Result:** Data protected using encryption

---

## 🔐 TC-SEC-IDS-004 – Sensitive values found in logs or cache

**Title:** Personal information stored in debug logs or cache files  
**Section:** Insecure_Data_Storage  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** OWASP-MOB-SEC-04  
**Preconditions:** Perform login and navigation actions

**Steps and Results:**

| Step | Action                     | Expected Result                         |
|------|----------------------------|-----------------------------------------|
| 1    | Browse log and cache files | No sensitive fields should be present   |
| 2    | Search for token/username  | No match found                          |

**Postconditions:** App leaves no personal data in debug folders  
**General Expected Result:** Logs sanitized from private content

---

## 🔐 TC-SEC-IDS-005 – Credentials written to public storage files

**Title:** Credentials saved in readable file formats  
**Section:** Insecure_Data_Storage  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** OWASP-MOB-SEC-05  
**Preconditions:** App successfully logged in

**Steps and Results:**

| Step | Action                               | Expected Result                      |
|------|--------------------------------------|--------------------------------------|
| 1    | Search `/data/` and `/storage/`      | No config or login files are found   |
| 2    | Open any discovered `.txt/.json/.xml` | No credentials visible               |

**Postconditions:** File system free of exposed secrets  
**General Expected Result:** App does not write credentials to user-accessible files

---

## 🔐 TC-SEC-IDS-006 – Missing use of Keychain/Keystore for sensitive tokens

**Title:** No secure storage API used for sensitive data  
**Section:** Insecure_Data_Storage  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Critical  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 4m  
**References:** OWASP-MOB-SEC-06  
**Preconditions:** App source code is available for review

**Steps and Results:**

| Step | Action                                  | Expected Result                      |
|------|-----------------------------------------|--------------------------------------|
| 1    | Search for Keystore / Keychain usage    | API should be used for all secrets   |
| 2    | Review token save logic                 | No plaintext saving of access tokens|

**Postconditions:** Tokens are encrypted using OS-level protection  
**General Expected Result:** Secure APIs used for sensitive data storage