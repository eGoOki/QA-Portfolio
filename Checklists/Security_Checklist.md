# 🔐 Security Checklist

This checklist focuses on identifying and mitigating security vulnerabilities across Web and Mobile platforms. It includes manual test items aligned with OWASP best practices, covering common risk areas such as authentication, data storage, and injection threats.

## 🔑 Authentication & Authorization

- [ ] Login requires valid credentials with secure password handling  
- [ ] Password fields mask input and prevent copy-paste if needed  
- [ ] MFA/2FA workflows are functional and correctly enforced  
- [ ] User roles are enforced via access control (RBAC)  
- [ ] Session termination occurs after logout or timeout  
- [ ] Password reset and recovery flows prevent brute-force attacks  
- [ ] Rate limiting is applied to login attempts

## 💾 Data Protection & Storage

- [ ] Sensitive data is encrypted at rest and in transit  
- [ ] No plaintext passwords or tokens are stored locally  
- [ ] Caching does not expose sensitive user data  
- [ ] Screenshots are disabled for sensitive views (on mobile)  
- [ ] Clipboard data is not exposed from secure fields  
- [ ] Local storage usage is limited and not used for sensitive data

## 📡 Network & API Security

- [ ] All requests use HTTPS  
- [ ] API keys and tokens are not exposed in frontend  
- [ ] CORS settings are correctly configured  
- [ ] Authentication tokens are short-lived and securely stored  
- [ ] API endpoints enforce access control and input validation  
- [ ] Server response headers prevent caching of sensitive data

## 🧪 Injection Vulnerabilities

- [ ] User input is sanitized and validated server-side  
- [ ] SQL queries use parameterized statements  
- [ ] No raw user input in system commands  
- [ ] No exposed debug parameters in production  
- [ ] JavaScript inputs are escaped to avoid XSS  
- [ ] Application does not reflect input unsafely

## 🧼 App Behavior & Error Handling

- [ ] Error messages do not reveal stack traces or sensitive info  
- [ ] User is not able to bypass client-side validation for critical flows  
- [ ] Authentication state cannot be forged via cookies or tokens  
- [ ] Logs do not contain user credentials or tokens  
- [ ] App behaves securely while offline or under network throttling

## 🔍 Reverse Engineering & Code Exposure

- [ ] Mobile binaries are obfuscated/minified  
- [ ] No hardcoded secrets in app files or config  
- [ ] Web source code does not expose business logic  
- [ ] Build artifacts do not contain debug symbols  
- [ ] Sensitive endpoints are not exposed via robots.txt or sitemap.xml  
- [ ] App integrity is validated during runtime (if applicable)

---

> 🧠 Use this checklist during manual security reviews, penetration test prep, or as part of your release readiness workflow. Combine with tools like OWASP ZAP, Burp Suite, or MobSF for deeper vulnerability analysis.