# 🧪 Test Data Preparation Checklist

This checklist provides guidelines for preparing effective test data used in manual QA processes. It helps simulate real-world scenarios, validate input handling, and uncover edge case behaviors across Web and Mobile platforms. The goal is to ensure tests are repeatable, meaningful, and cover a wide range of conditions.

## ✅ Valid Input Scenarios

- [ ] Common and expected values for each input field  
- [ ] Typical user credentials (active, admin, restricted roles)  
- [ ] Supported file formats (e.g. .jpg, .png, .pdf)  
- [ ] Accepted payment details or transaction records  
- [ ] Realistic user profiles with complete metadata  
- [ ] Country/region-specific inputs (e.g. zip codes, phone numbers)

## 🚫 Invalid & Negative Data

- [ ] Empty fields and whitespace-only inputs  
- [ ] Unsupported characters, emojis, or control symbols  
- [ ] SQL injection or script tags (to test sanitization)  
- [ ] Overly long strings and unexpected formats  
- [ ] Misspelled or malformed email addresses  
- [ ] Expired dates or non-existent values

## 🎲 Edge Cases & Boundaries

- [ ] Field length limits (max/min characters)  
- [ ] High numeric values, decimals, negatives  
- [ ] Zero values or boundary conditions  
- [ ] Optional vs required field variations  
- [ ] Duplicated records or IDs  
- [ ] Simultaneous actions across users/devices

## 🔐 Security-Oriented Data

- [ ] Simulated tokens or API keys (non-production)  
- [ ] Access-controlled credentials for role-based testing  
- [ ] Corrupted or tampered payloads for resilience tests  
- [ ] Data that mimics real user behavior while preserving anonymity  
- [ ] Encrypted or hashed samples for storage validation

## 📂 Environmental & Configuration Data

- [ ] URLs, endpoints, or test servers  
- [ ] Mock server configurations and sandbox modes  
- [ ] App versioning info for compatibility tests  
- [ ] Feature flags or A/B test variants  
- [ ] Browser and device profiles (for responsive checks)

## 📎 Data Management Practices

- [ ] Separate test and production environments  
- [ ] Reusable datasets stored in a shared location  
- [ ] Clear naming conventions for test files and entries  
- [ ] Scripts available for resetting or re-seeding data  
- [ ] Documentation provided for data structure and usage

---

> 🧠 Tip: Keep your test data version-controlled and document dependencies. Well-crafted data saves time, reduces flaky test outcomes, and improves test coverage across projects.