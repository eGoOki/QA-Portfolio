# 🧪 Mobile Login Form – Edge Case Test Cases

---

> ⚠️ **Note**: These cases cover boundary conditions and formatting anomalies in mobile login fields.

---

## 🎯 Scope

Edge cases include:

- 📦 Max field lengths  
- ✂️ Whitespace trimming  
- 🌐 Unicode and emoji support  
- 📋 Clipboard paste actions  
- 🔠 Casing sensitivity

---

### ⛔ Out of Scope

- **Security validation and edge behavior** – see [Login_Security.md](./Login_Security.md)  
- **Positive validation success flows** – see [Login_Positive_Mobile.md](./Login_Positive_Mobile.md)  
- **Negative validation and error messaging** – see [Login_Negative_Mobile.md](./Login_Negative_Mobile.md)

---

## 🔐 TC-LOGIN-MOB-011 – Leading/trailing whitespace in credentials

**Title:** Whitespace trimming in credentials  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Validation  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** UX-MOB-TRIM-011  
**Preconditions:** Valid user account exists

**Steps and Results:**

| Step | Action                                       | Expected Result                           |
|------|----------------------------------------------|-------------------------------------------|
| 1    | Enter email and password with leading spaces | Fields automatically trim whitespace      |
| 2    | Tap “Login”                                  | Authentication succeeds without error     |

**Postconditions:** Sanitized credentials submitted  
**General Expected Result:** Login allowed after whitespace removal

---

## 🔐 TC-LOGIN-MOB-012 – Input field max length

**Title:** Input field maximum length enforcement  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Usability  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** UX-MOB-FIELDLIMIT  
**Preconditions:** Login screen is displayed

**Steps and Results:**

| Step | Action                                  | Expected Result                          |
|------|------------------------------------------|------------------------------------------|
| 1    | Enter over 100 characters in email field | Input is truncated or blocked            |
| 2    | Try to submit                            | Validation error for malformed input     |

**Postconditions:** Invalid submission prevented  
**General Expected Result:** Input field enforces character limits

---

## 🔐 TC-LOGIN-MOB-013 – Emoji or special characters in fields

**Title:** Emoji/special character rejection  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Validation  
**Priority:** Low  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 1m  
**References:** VAL-MOB-CHARFILTER  
**Preconditions:** —

**Steps and Results:**

| Step | Action                   | Expected Result                               |
|------|---------------------------|-----------------------------------------------|
| 1    | Enter emojis in username  | Field rejects or strips unsupported symbols   |
| 2    | Tap “Login”               | Submission blocked with validation message    |

**Postconditions:** Credentials sanitized  
**General Expected Result:** Non-standard characters are disallowed

---

## 🔐 TC-LOGIN-MOB-014 – Clipboard paste into password field

**Title:** Password clipboard paste support  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Usability  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** UX-MOB-CLIP-014  
**Preconditions:** Valid password copied to clipboard

**Steps and Results:**

| Step | Action                          | Expected Result                          |
|------|----------------------------------|------------------------------------------|
| 1    | Paste password into password field | Input accepted without formatting issues |
| 2    | Tap “Login”                     | Login succeeds                           |

**Postconditions:** Input allowed via paste  
**General Expected Result:** Clipboard integration works securely

---

## 🔐 TC-LOGIN-MOB-015 – Case sensitivity in credentials

**Title:** Case-sensitive credential handling  
**Section:** Login_Form  
**Template:** Steps + Results  
**Type:** Functional  
**Priority:** Medium  
**Status:** Approved  
**Defects:** —  
**Execution Status:** Passed  
**Automation:** Manual  
**Assigned To:** QA Engineer  
**Estimate:** 2m  
**References:** REQ-MOB-CASE-015  
**Preconditions:** Username and password fields are case-sensitive

**Steps and Results:**

| Step | Action                                       | Expected Result                        |
|------|----------------------------------------------|----------------------------------------|
| 1    | Enter valid credentials with wrong casing    | API rejects input                      |
| 2    | Retry with correct casing                    | Login succeeds                         |

**Postconditions:** Auth respects casing rules  
**General Expected Result:** Login fails on mismatched case