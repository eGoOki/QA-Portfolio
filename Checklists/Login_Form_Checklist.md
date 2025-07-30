# 🛡️ Login Form Checklist

## Overview

This checklist summarizes manual test coverage for the login functionality. It includes validation, security, usability, edge cases, session behavior, and localization scenarios. The goal is to ensure the login form behaves reliably across different inputs, environments, and user conditions.

This checklist is based on the test cases located in  
[`Test-Cases/Web/Login_Form/`](../../Test-Cases/Web/Login_Form/)  
and complements the QA documentation structure of this portfolio.

Use this checklist during regression testing, smoke testing, and exploratory QA sessions. It can also serve as a reference for automation planning and coverage tracking.

---

## Test Categories

| Category       | Test Cases                                                                 |
|----------------|-----------------------------------------------------------------------------|
| Validation     | [TC-LOGIN-101](../../Test-Cases/Web/Login_Form/TC-LOGIN-101.md), [102](../../Test-Cases/Web/Login_Form/TC-LOGIN-102.md), [107](../../Test-Cases/Web/Login_Form/TC-LOGIN-107.md), [108](../../Test-Cases/Web/Login_Form/TC-LOGIN-108.md), [109](../../Test-Cases/Web/Login_Form/TC-LOGIN-109.md), [201](../../Test-Cases/Web/Login_Form/TC-LOGIN-201.md), [202](../../Test-Cases/Web/Login_Form/TC-LOGIN-202.md) |
| Security       | [103](../../Test-Cases/Web/Login_Form/TC-LOGIN-103.md), [105](../../Test-Cases/Web/Login_Form/TC-LOGIN-105.md), [106](../../Test-Cases/Web/Login_Form/TC-LOGIN-106.md), [203](../../Test-Cases/Web/Login_Form/TC-LOGIN-203.md), [211](../../Test-Cases/Web/Login_Form/TC-LOGIN-211.md) |
| Functional     | [104](../../Test-Cases/Web/Login_Form/TC-LOGIN-104.md), [204](../../Test-Cases/Web/Login_Form/TC-LOGIN-204.md), [206](../../Test-Cases/Web/Login_Form/TC-LOGIN-206.md), [210](../../Test-Cases/Web/Login_Form/TC-LOGIN-210.md), [212](../../Test-Cases/Web/Login_Form/TC-LOGIN-212.md) |
| Usability      | [201](../../Test-Cases/Web/Login_Form/TC-LOGIN-201.md), [202](../../Test-Cases/Web/Login_Form/TC-LOGIN-202.md), [205](../../Test-Cases/Web/Login_Form/TC-LOGIN-205.md), [212](../../Test-Cases/Web/Login_Form/TC-LOGIN-212.md) |
| Localization   | [208](../../Test-Cases/Web/Login_Form/TC-LOGIN-208.md), [209](../../Test-Cases/Web/Login_Form/TC-LOGIN-209.md) |
| Stability      | [207](../../Test-Cases/Web/Login_Form/TC-LOGIN-207.md) |
| Integration    | [211](../../Test-Cases/Web/Login_Form/TC-LOGIN-211.md) |

---

## ✅ Checklist Items

- [ ] [TC-LOGIN-101](../../Test-Cases/Web/Login_Form/TC-LOGIN-101.md) - Login blocked when fields are empty  
- [ ] [TC-LOGIN-102](../../Test-Cases/Web/Login_Form/TC-LOGIN-102.md) - Invalid email format triggers validation  
- [ ] [TC-LOGIN-103](../../Test-Cases/Web/Login_Form/TC-LOGIN-103.md) - Incorrect credentials show generic error  
- [ ] [TC-LOGIN-104](../../Test-Cases/Web/Login_Form/TC-LOGIN-104.md) - Expired password requires reset flow  
- [ ] [TC-LOGIN-105](../../Test-Cases/Web/Login_Form/TC-LOGIN-105.md) - Locked account prevents login  
- [ ] [TC-LOGIN-106](../../Test-Cases/Web/Login_Form/TC-LOGIN-106.md) - Rate limiting after repeated failures  
- [ ] [TC-LOGIN-107](../../Test-Cases/Web/Login_Form/TC-LOGIN-107.md) - Leading/trailing spaces cause login failure or trimming  
- [ ] [TC-LOGIN-108](../../Test-Cases/Web/Login_Form/TC-LOGIN-108.md) - Case sensitivity mismatch in email  
- [ ] [TC-LOGIN-109](../../Test-Cases/Web/Login_Form/TC-LOGIN-109.md) - Username with special characters is rejected  
- [ ] [TC-LOGIN-201](../../Test-Cases/Web/Login_Form/TC-LOGIN-201.md) - Uppercase email is accepted  
- [ ] [TC-LOGIN-202](../../Test-Cases/Web/Login_Form/TC-LOGIN-202.md) - Whitespace in credentials is trimmed or flagged  
- [ ] [TC-LOGIN-203](../../Test-Cases/Web/Login_Form/TC-LOGIN-203.md) - Password with special characters is accepted  
- [ ] [TC-LOGIN-204](../../Test-Cases/Web/Login_Form/TC-LOGIN-204.md) - Login during active session handled gracefully  
- [ ] [TC-LOGIN-205](../../Test-Cases/Web/Login_Form/TC-LOGIN-205.md) - Password field supports clipboard paste  
- [ ] [TC-LOGIN-206](../../Test-Cases/Web/Login_Form/TC-LOGIN-206.md) - Login works immediately after password change  
- [ ] [TC-LOGIN-207](../../Test-Cases/Web/Login_Form/TC-LOGIN-207.md) - Login blocked during system maintenance  
- [ ] [TC-LOGIN-208](../../Test-Cases/Web/Login_Form/TC-LOGIN-208.md) - Error messages localized based on browser language  
- [ ] [TC-LOGIN-209](../../Test-Cases/Web/Login_Form/TC-LOGIN-209.md) - RTL layout and alignment supported  
- [ ] [TC-LOGIN-210](../../Test-Cases/Web/Login_Form/TC-LOGIN-210.md) - Session expires after inactivity  
- [ ] [TC-LOGIN-211](../../Test-Cases/Web/Login_Form/TC-LOGIN-211.md) - Token refresh occurs silently before expiry  
- [ ] [TC-LOGIN-212](../../Test-Cases/Web/Login_Form/TC-LOGIN-212.md) - Session remains consistent across browser tabs

---

## Notes

- All test cases include clear preconditions, expected results, and postconditions.
- Draft cases should be finalized before release testing.
- Automation status is tracked separately; some cases are queued for future automation.

---

## References

- REQ-AUTH-VAL-001, REQ-AUTH-VAL-002, REQ-AUTH-003  
- REQ-PWD-EXP-001, REQ-LOCK-ACCOUNT-011, REQ-SEC-LIMIT-017  
- REQ-PWD-CHANGE, REQ-MAINTENANCE, REQ-LOCALE-ERRORS  
- REQ-RTL-UI, REQ-SESSION-TIMEOUT