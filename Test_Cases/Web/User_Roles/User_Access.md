# 👤 User Access – Role-Based Test Cases

---

> ⚠️ **Note**: The test cases in this repository are provided as examples only. Each software project may have its own conventions regarding test case structure, required fields, naming formats, documentation standards, and writing style. These samples reflect one possible approach and are not intended as the only correct format.

---

## 📄 Table of Contents

✅ Positive:
- TC-USER-101 – Access own profile page
- TC-USER-102 – Change own password
- TC-USER-103 – View dashboard
- TC-USER-104 – Submit support ticket

❌ Negative:
- TC-USER-201 – Attempt to access admin panel
- TC-USER-202 – View another user’s profile
- TC-USER-203 – Attempt to edit restricted config
- TC-USER-204 – Direct URL access to system logs

---

## ✅ Positive Test Cases

## 🧍 TC-USER-101 – Access own profile page

**Title:** Regular user profile view  
**Section:** Profile  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**Preconditions:** Logged in as user  

| Step | Action             | Expected Result                        |
|------|--------------------|----------------------------------------|
| 1    | Login as user      | Authenticated                          |
| 2    | Go to profile page | Profile details displayed              |

**Postconditions:**  
User can view own information

**General Expected Result:**  
Only personal details are visible

---

## 🔑 TC-USER-102 – Change own password

**Title:** Update credentials as user  
**Section:** Profile  
**Template:** Steps + Results  
**Type:** Security / Usability  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**Preconditions:** Logged in as user  

| Step | Action                  | Expected Result                    |
|------|-------------------------|------------------------------------|
| 1    | Go to password settings | Form visible                      |
| 2    | Enter old and new pass  | Input validated                    |
| 3    | Save changes            | Confirmation displayed             |

**Postconditions:**  
New password is active

**General Expected Result:**  
Users can update their password securely

---

## 📊 TC-USER-103 – View dashboard

**Title:** User access to dashboard  
**Section:** Dashboard  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Engineer  
**Estimate:** 1m  
**Preconditions:** Logged in as user  

| Step | Action              | Expected Result                     |
|------|---------------------|-------------------------------------|
| 1    | Login               | Authenticated                       |
| 2    | Open dashboard      | Data widgets and metrics are shown |

**Postconditions:**  
User sees personalized dashboard

**General Expected Result:**  
General dashboard components are visible to users

---

## 🎫 TC-USER-104 – Submit support ticket

**Title:** Help request workflow  
**Section:** Support  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status

---

## ❌ Negative Test Cases

### 🚫 TC-USER-201 – Attempt to access admin panel

**Title:** Unauthorized dashboard access attempt  
**Section:** Admin_Panel  
**Type:** Security  
**Status:** Approved  
**Priority:** High  
**Defects:** —  
**Execution Status:** Passed  

| Step | Action                         | Expected Result                        |
|------|--------------------------------|-----------------------------------------|
| 1    | Login as regular user          | Authenticated                           |
| 2    | Try access admin dashboard URL | System blocks and redirects             |

**Postconditions:**  
No access granted

**Expected Result:**  
System denies access based on insufficient privileges

---

### 🕵️ TC-USER-202 – View another user’s profile

**Title:** Unauthorized profile visibility  
**Section:** Profile  
**Type:** Privacy  
**Status:** Approved  
**Priority:** High  
**Defects:** —  
**Execution Status:** Passed  

| Step | Action                            | Expected Result                     |
|------|-----------------------------------|--------------------------------------|
| 1    | Login as user                     | Personal dashboard shown            |
| 2    | Try URL to another user profile   | Error or access denied              |

**Postconditions:**  
Restricted content not shown

**Expected Result:**  
System enforces strict privacy boundary

---

### ⚙️ TC-USER-203 – Attempt to edit system config

**Title:** Regular user attempts unauthorized settings change  
**Section:** System_Settings  
**Type:** Security  
**Status:** Approved  
**Priority:** High  
**Defects:** —  
**Execution Status:** Passed  

| Step | Action                      | Expected Result                           |
|------|-----------------------------|--------------------------------------------|
| 1    | Login as user               | Authenticated                              |
| 2    | Navigate to system settings | Page inaccessible or hidden                |

**Postconditions:**  
Settings remain unchanged

**Expected Result:**  
System hides or disables settings panel for regular users

---

### 📂 TC-USER-204 – Direct URL access to system logs

**Title:** Bypass attempt to access restricted logs  
**Section:** Audit_Log  
**Type:** Security  
**Status:** Approved  
**Priority:** High  
**Defects:** —  
**Execution Status:** Passed  

| Step | Action                       | Expected Result                           |
|------|------------------------------|--------------------------------------------|
| 1    | Login as regular user        | No system log access                      |
| 2    | Try direct URL to logs page  | System returns “Access Denied” page       |

**Postconditions:**  
No sensitive data leaked

**Expected Result:**  
System securely restricts log access by role