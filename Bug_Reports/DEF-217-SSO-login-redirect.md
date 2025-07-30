## Summary  
After successful authentication via SSO provider, the user is not redirected back to the application dashboard. The session is not initiated and login flow is interrupted.

## Related Test Case  
[TC-LOGIN-002 – Login via SSO](../Test_Cases/Web/Login_Form/Login_Positive.md#tc-login-002--login-via-email-login-link)

## Steps to reproduce  
1. Open login page  
2. Click "Login via SSO"  
3. Choose a configured provider (e.g., Google Workspace)  
4. Authenticate successfully  
5. Observe redirection behavior

## Expected Result  
User should be redirected to the application dashboard with a valid session token.

## Actual Result  
User is left at the provider's confirmation screen with no redirection. No session is created.

## Priority  
🟠 Medium

## Severity  
Major

## Status  
Selected for Development

## Environment  
- OS: Windows 11  
- Browser: Chrome 115  
- Platform: Web App  
- SSO Provider: Google Workspace (staging)

## Attachments  
- [screenshot](link-to-screenshot) *Please note that no actual screenshot is provided.*
- [log from Chrome DevTools](link-to-logFile) *Please note that no actual log is provided.*

## Labels  
Triage, Auth, Integration

## Affected version  
v3.4.2

## Fix version
none

## Reported On: 
July 30, 2025  

## Reported By: 
Ievgen  

## Assignee: 
John Dou