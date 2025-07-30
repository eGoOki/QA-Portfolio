# 🐞 Bug Reports

## Overview

This folder contains documented software defects discovered during manual QA testing. Each bug report is written as a separate Markdown file and includes key details to help developers understand, reproduce, and fix the issue. These reports support communication across teams and improve overall product quality.

---

## Structure

- Each bug is stored in an individual `.md` file
- File names follow the format: `DEF-<ID>-<short-description>.md`
- Reports cover metadata, reproduction steps, expected and actual results, and related resources

---

## Available Bug Reports

| Defect ID | Title                                                                 | Status                  |
|-----------|------------------------------------------------------------------------|--------------------------|
| [DEF-217](DEF-217-SSO-login-redirect.md) | SSO login flow does not complete redirection             | Selected for Development |
| [DEF-108](DEF-108-Mobile-app-logini-does-not-result-in-valid-session-token.md) | Mobile app login does not result in valid session token | Selected for Development |
| [DEF-309](DEF-309-expired-password-login.md) | Expired password does not trigger recovery prompt        | Selected for Development |

---

## Usage Guidelines

- 📎 Attach screenshots and logs where relevant
- 🔗 Reference related test cases from the `Test_Cases/` folder
- 🛠 Keep the report status updated based on triage progress
- 📋 Use bug reports to track QA coverage and guide release decisions

---

## 🗂️ Bug Report Field Descriptions

| Field               | Description                                                             |
|---------------------|-------------------------------------------------------------------------|
| **Defect ID**       | Unique identifier for the issue, e.g., `DEF-217`                        |
| **Title**           | Brief summary of the bug                                                |
| **Status**          | Current progress: Open, Triaged, In Progress, Fixed, Closed             |
| **Severity**        | Impact on product functionality: Minor, Major, Critical                 |
| **Priority**        | Urgency for fixing: Low, Medium, High                                   |
| **Environment**     | Platform or configuration where the bug occurred                        |
| **Reproduction Steps** | Step-by-step instructions to reproduce the issue                 |
| **Expected Result** | What the system should have done                                        |
| **Actual Result**   | What the system did instead                                             |
| **Screenshots/Logs**| Supporting evidence (if available)                                      |
| **Related Test Cases** | Links to relevant manual or automated tests                        |
| **Reported On**     | Date the bug was documented                                             |
| **Reported By**     | Name or ID of the QA analyst who filed the bug                         |
| **Assignee**        | Person responsible for fixing the issue                                 |
---