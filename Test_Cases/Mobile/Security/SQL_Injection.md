# ✅ SQL Injection – Mobile QA Test Cases

This section focuses on identifying vulnerabilities where user input is improperly handled in SQL queries, allowing attackers to manipulate database logic and extract, modify, or delete sensitive data.

---

## 🎯 Scope

These test cases cover:

- 🧪 Classic, blind, and time-based SQL injection  
- 🧱 Input validation and query sanitization flaws  
- 🔄 Parameterized query bypasses  
- 🧵 Union-based and stacked query injection  
- 🧠 Business logic abuse via SQLi

---

### ⛔ Out of Scope

- [**Authentication bypass via SQLi**](Authentication_Bypass.md)  
- [**Stored XSS via SQL injection**](XSS_Testing.md)  
- [**Database encryption and secure storage**](Insecure_Data_Storage.md)

---

## 🔐 TC-SEC-SQL-001 – Query built via string concatenation

**Title:** Unsafe query construction using string interpolation  
**Section:** SQL_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 4m  
**References:** OWASP-MOB-SQL-001  
**Preconditions:** App is installed with database access enabled

**Steps and Results:**

| Step | Action                           | Expected Result                              |
|------|----------------------------------|----------------------------------------------|
| 1    | Enter `test' OR '1'='1` in login field | App does not authenticate the user         |
| 2    | Observe SQL execution            | Query fails or input treated as unsafe       |

**Postconditions:** Query constructed safely or execution blocked  
**General Expected Result:** No login bypass using SQL injection

---

## 🔐 TC-SEC-SQL-002 – Use of parameterized queries

**Title:** Protection against SQL injection using bound parameters  
**Section:** SQL_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** High  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** OWASP-MOB-SQL-002  
**Preconditions:** App source reviewed or tested via log/DB inspector

**Steps and Results:**

| Step | Action                                  | Expected Result                      |
|------|-----------------------------------------|--------------------------------------|
| 1    | Perform form submission with `' OR 1=1` | Input handled as literal string      |
| 2    | Confirm query logic via logs            | Parameters used in SQL call          |

**Postconditions:** App resists SQL manipulation attempts  
**General Expected Result:** Query parameterization is in place

---

## 🔐 TC-SEC-SQL-003 – Numeric field sanitization

**Title:** Unsafe input rejected in numeric form fields  
**Section:** SQL_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** OWASP-MOB-SQL-003  
**Preconditions:** Valid app session and access to search form

**Steps and Results:**

| Step | Action                                   | Expected Result                         |
|------|------------------------------------------|-----------------------------------------|
| 1    | Enter `1; DROP TABLE users` in ID field | Input rejected or sanitized             |
| 2    | Tap Search                               | App ignores invalid characters          |

**Postconditions:** DB structure remains intact  
**General Expected Result:** Input sanitized before query execution

---

## 🔐 TC-SEC-SQL-004 – Tampered local storage injection

**Title:** Exploiting local storage to inject queries  
**Section:** SQL_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** OWASP-MOB-SQL-004  
**Preconditions:** App data accessible via file explorer or adb

**Steps and Results:**

| Step | Action                                    | Expected Result                        |
|------|-------------------------------------------|----------------------------------------|
| 1    | Modify local file with SQL payload        | App should not parse or execute input |
| 2    | Relaunch app and trigger read             | App sanitizes or blocks malicious value|

**Postconditions:** Local tampering does not lead to injection  
**General Expected Result:** Input from local storage treated safely

---

## 🔐 TC-SEC-SQL-005 – ORM protection against SQL injection

**Title:** ORM-based query structure avoids injection  
**Section:** SQL_Injection  
**Template:** Steps + Results  
**Type:** Security  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 3m  
**References:** OWASP-MOB-SQL-005  
**Preconditions:** App uses ORM like Room/Realm

**Steps and Results:**

| Step | Action                        | Expected Result                      |
|------|-------------------------------|--------------------------------------|
| 1    | Submit SQL payload via UI     | ORM handles input safely             |
| 2    | Review generated query        | Input escaped or validated properly  |

**Postconditions:** ORM behavior prevents injection attempts  
**General Expected Result:** No SQL bypass via UI fields

---

## 🔐 TC-SEC-SQL-006 – Error handling for broken SQL

**Title:** Broken SQL queries are caught and handled  
**Section:** SQL_Injection  
**Template:** Steps + Results  
**Type:** Stability  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** OWASP-MOB-SQL-006  
**Preconditions:** App connected to database runtime

**Steps and Results:**

| Step | Action                             | Expected Result                        |
|------|------------------------------------|----------------------------------------|
| 1    | Cause syntax error in SQL string   | App handles exception gracefully       |
| 2    | Observe app response               | Fallback logic or error message shown  |

**Postconditions:** App stability maintained after failed query  
**General Expected Result:** No crash or sensitive info exposed