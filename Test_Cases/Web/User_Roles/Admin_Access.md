# 🛡️ Admin Access – Role-Based Test Cases

---

> ⚠️ **Note**: The test cases in this repository are provided as examples only. Each software project may have its own conventions regarding test case structure, required fields, naming formats, documentation standards, and writing style. These samples reflect one possible approach and are not intended as the only correct format.

---

## 📄 Table of Contents

✅ Positive:
- TC-ADMIN-101 – Access to admin dashboard
- TC-ADMIN-102 – Create a new user
- TC-ADMIN-103 – Delete an existing user
- TC-ADMIN-104 – Edit system configuration
- TC-ADMIN-105 – View audit logs

❌ Negative:
- TC-ADMIN-201 – Attempt to delete own admin account
- TC-ADMIN-202 – Attempt to downgrade own role
- TC-ADMIN-203 – Submit empty config update
- TC-ADMIN-204 – Access admin panel after session expiry

---

## ✅ Positive Test Cases

## 🧭 TC-ADMIN-101 – Access to admin dashboard

**Title:** Admin role dashboard accessibility  
**Section:** Admin_Panel  
**Template:** Steps + Results  
**Type:** Functional / Access Control  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Lead  
**Estimate:** 2m  
**Preconditions:** Logged in as user with admin role  

| Step | Action                 | Expected Result                        |
|------|------------------------|----------------------------------------|
| 1    | Login as admin         | Authenticated                          |
| 2    | Navigate to dashboard  | Admin panel visible                    |
| 3    | Click dashboard        | Access granted with full privileges    |

**Postconditions:**  
Admin interface is accessible

**General Expected Result:**  
Admin user sees dashboard controls after successful login

---

## 🆕 TC-ADMIN-102 – Create a new user

**Title:** Admin user creation functionality  
**Section:** User_Management  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automation Queue  
**Assigned To:** QA Lead  
**Estimate:** 3m  
**Preconditions:** Logged in as admin  

| Step | Action                        | Expected Result                    |
|------|-------------------------------|------------------------------------|
| 1    | Go to user management panel   | Interface loaded                   |
| 2    | Click “Create User”           | Modal/form is shown                |
| 3    | Fill user details             | Fields accept input                |
| 4    | Submit form                   | Confirmation of successful creation|

**Postconditions:**  
New user appears in listing

**General Expected Result:**  
Admin can create valid users without error

---

## 🗑️ TC-ADMIN-103 – Delete an existing user

**Title:** Admin removes an active account  
**Section:** User_Management  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual Only  
**Assigned To:** QA Lead  
**Estimate:** 2m  
**Preconditions:** Valid user exists  

| Step | Action                  | Expected Result                      |
|------|-------------------------|--------------------------------------|
| 1    | Navigate to user list   | Users listed                         |
| 2    | Locate target user      | User is visible                      |
| 3    | Click “Delete”          | Confirmation popup appears           |
| 4    | Confirm deletion        | User removed from system             |

**Postconditions:**  
Target user deleted successfully

**General Expected Result:**  
Admin can remove user accounts with confirmation flow

---

## ⚙️ TC-ADMIN-104 – Edit system configuration

**Title:** Modify global system settings  
**Section:** System_Settings  
**Template:** Steps + Results  
**Type:** Functional / Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Not Automated  
**Assigned To:** QA Lead  
**Estimate:** 3m  
**Preconditions:** Logged in as admin  

| Step | Action                  | Expected Result                           |
|------|-------------------------|-------------------------------------------|
| 1    | Go to settings          | Settings visible to admin                 |
| 2    | Change configuration    | Input accepted                            |
| 3    | Save settings           | System confirms update                    |

**Postconditions:**  
System settings reflect new values

**General Expected Result:**  
Only admin can modify global configurations

---

## 📜 TC-ADMIN-105 – View audit logs

**Title:** Access historical system logs  
**Section:** Audit_Log  
**Template:** Steps + Results  
**Type:** Security / Monitoring  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Automated  
**Assigned To:** QA Lead  
**Estimate:** 2m  
**Preconditions:** Logged in as admin  

| Step | Action             | Expected Result                         |
|------|--------------------|------------------------------------------|
| 1    | Open audit log     | Logs are visible                        |
| 2    | Filter by date     | Log entries shown correctly             |
| 3    | Export logs        | File download initiated                 |

**Postconditions:**  
Logs accessed successfully

**General Expected Result:**  
Admin role has visibility into audit records

---

## ❌ Negative Test Cases

### 🚫 TC-ADMIN-201 – Attempt to delete own admin account

**Title:** Admin tries to delete self  
**Section:** User_Management  
**Type:** Security  
**Status:** Approved  
**Priority:** High  
**Defects:** —  
**Execution Status:** Passed  
**Preconditions:** Logged in as admin  

| Step | Action                     | Expected Result                           |
|------|----------------------------|--------------------------------------------|
| 1    | Go to user list            | Own account is listed                      |
| 2    | Attempt deletion of self   | System blocks action                       |

**Postconditions:**  
No deletion occurs

**Expected Result:**  
System prevents deletion of current admin’s own account

---

### 🧨 TC-ADMIN-202 – Attempt to downgrade own role

**Title:** Admin tries to remove own admin privileges  
**Section:** User_Management  
**Type:** Security  
**Status:** Approved  
**Priority:** Medium  
**Defects:** —  
**Execution Status:** Passed  
**Preconditions:** Must be logged in as admin  

| Step | Action                       | Expected Result                            |
|------|------------------------------|---------------------------------------------|
| 1    | Open own profile             | Editable fields visible                     |
| 2    | Attempt to change role to “User” | Action denied                         |

**Postconditions:**  
Role remains unchanged

**Expected Result:**  
System blocks role downgrade of current admin

---

### ⚠️ TC-ADMIN-203 – Submit empty config update

**Title:** Configuration form submitted with missing fields  
**Section:** System_Settings  
**Type:** Validation  
**Status:** Approved  
**Priority:** Medium  
**Defects:** —  
**Execution Status:** Passed  

| Step | Action                    | Expected Result                                 |
|------|---------------------------|--------------------------------------------------|
| 1    | Go to settings            | Form is visible                                 |
| 2    | Remove required values    | Validation triggers                             |
| 3    | Click “Save”              | Error: “Fields cannot be empty”                 |

**Postconditions:**  
Settings remain unchanged

**Expected Result:**  
Validation prevents empty config submission

---

### ⌛ TC-ADMIN-204 – Access admin panel after session expiry

**Title:** Admin tries to use expired session  
**Section:** Session_Management  
**Type:** Security  
**Status:** Approved  
**Priority:** High  
**Defects:** —  
**Execution Status:** Passed  

| Step | Action                        | Expected Result                          |
|------|-------------------------------|-------------------------------------------|
| 1    | Login as admin                | Session created                          |
| 2    | Wait for timeout              | Session expires                          |
| 3    | Refresh panel page            | Redirected to login                      |

**Postconditions:**  
No access granted

**Expected Result:**  
System securely blocks access after session expiry