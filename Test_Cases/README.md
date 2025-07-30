# 🧪 Test Case Repository

This repository contains structured test cases for both Web and Mobile platforms.  
Each module is organized by functionality and includes positive and negative scenarios, UI validation, security vectors, accessibility coverage, localization testing, session behavior, and performance analysis.

---

## 📁 Sections

- 🌐 [Web](./Web/) — test cases for the web application:
  - 🔐 [Login Form](./Web/Login_Form/) – authentication flows, input validation, edge case handling, session behavior, and token expiry  
  - 👥 [User Roles](./Web/User_Roles/) – admin/user permission controls, RBAC logic, and page-level access verification  
  - 🛡️ [Security](./Web/Security/) – SQL injection testing, XSS attack vectors, input sanitization, brute-force simulation  
  - 🎨 [UI Elements](./Web/UI_Elements/) – layout consistency across pages, element visibility, and placement validation  
  - 🌐 [Compatibility](./Web/Compatibility/) – cross-browser rendering, screen resolution adaptability, and viewport behavior  
  - ♿ [Accessibility](./Web/Accessibility/) – WCAG compliance, ARIA roles, screen reader flow, and keyboard navigation  
  - ⚙️ [Performance](./Web/Performance/) – load and stress tests, caching behavior, and response time tracking  
  - 🌍 [Localization](./Web/Localization/) – language-specific formatting, translation validation, RTL layout handling, locale switching  

- 📱 [Mobile](./Mobile/) — test cases for mobile apps:
  - 🔐 [Login Form](./Mobile/Login_Form/) – platform-aware login validation, form behavior, biometric fallback, session restore  
  - 📱 [Device Adaptivity](./Mobile/Device_Adaptivity/) – UI scalability across screen sizes, OS-specific quirks (iOS/Android)  
  - 🛡️ [Security](./Mobile/Security/) – mobile vector injection testing, session token storage, platform-specific risks  
  - ♿ [Accessibility](./Mobile/Accessibility/) – TalkBack/VoiceOver screen reader support, gesture interaction, and navigation hierarchy  
  - ⚙️ [Performance](./Mobile/Performance/) – application load metrics, battery consumption impact, offline caching  

---

## ✅ Coverage Overview

- 🔐 Authentication (positive, negative, edge cases, session and token coverage)  
- 🧾 Input validation and boundary testing  
- 👥 Role-based access control with permission integrity checks  
- 🎨 UI layout consistency, element placement, and responsiveness  
- ♿ Accessibility features across web and mobile (screen readers, ARIA, WCAG, TalkBack, VoiceOver)  
- 🛡️ Security: SQL injection, XSS, brute-force handling, secure token/session design  
- 🌍 Localization readiness: translation fidelity, layout mirroring, date/currency formats  
- 🌐 Compatibility: rendering across browsers, devices, screen sizes, and orientations  
- ⚙️ Performance benchmarks: load/stress behavior, battery profiling, caching evaluation  

---

## 🧷 Test Case Metadata Structure

Each test case uses a consistent metadata template to ensure clarity and automation readiness.

| Field                 | Description                                                           |
|----------------------|------------------------------------------------------------------------|
| `Title`              | Short name for the test case                                           |
| `Section`            | Functional group/module (e.g. Login_Form)                              |
| `Template`           | Formatting type: Steps + Results                                       |
| `Type`               | Type of testing: Functional, Security, Usability, etc.                 |
| `Priority`           | Severity: High, Medium, Low                                            |
| `Status`             | Lifecycle status: Draft, Approved, Review                              |
| `Defects`            | Linked issues or defect IDs                                            |
| `Execution Status`   | Outcome: Passed, Failed, Blocked, Not Executed, Skipped, Retest        |
| `Automation`         | Automation readiness: Automated, Automation Queue, Cannot be Automated |
| `Assigned To`        | Responsible QA engineer                                                |
| `Estimate`           | Approx. time to execute (e.g. 2m, 5m)                                  |
| `References`         | Linked requirements, documentation, or Jira tickets                    |
| `Preconditions`      | Setup required before execution                                        |
| `Steps and Results`  | Table describing each action and its expected result                   |
| `Postconditions`     | Expected state of the system after execution                           |
| `General Expected Result` | Summary of the overall outcome after all steps                    |

---

## 🔗 Reference Format and Standards

Test case structure and fields are inspired by official TestRail documentation.  
Source: [Test Case Fields – TestRail Documentation](https://support.testrail.com/hc/en-us/articles/14940939006740-Test-case-fields)

All test cases are formatted in Markdown for readability and are aligned with QA best practices.  
They are written for manual execution but prepared for future automation and CI/CD integration.