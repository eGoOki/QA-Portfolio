## Summary  
When logging in via the authorized mobile application, the backend does not validate the access token correctly. As a result, no user session is initiated, and login fails silently.

## Related Test Case  
[TC-LOGIN-004 – Login via mobile app](../Test_Cases/Web/Login_Form/Login_Positive.md#tc-login-004--login-via-mobile-app)

## Steps to reproduce  
1. Install and open the authorized mobile app  
2. Navigate to login screen  
3. Attempt login with valid credentials  
4. Monitor token generation and backend response  
5. Observe session state

## Expected Result  
Backend verifies access token, creates a session, and grants user access to the application.

## Actual Result  
Access token is generated but backend does not respond with session initiation. User remains on login screen without feedback.

## Priority  
🟠 Medium

## Severity  
Major

## Status  
Selected for Development

## Environment  
- OS: Android 14  
- App Version: 2.9.7  
- Backend: API v1.22.3  
- Network: WiFi, stable connection

## Attachments  
- [mobile-login-debug-log.txt](link-to-log) *Missing actual log file*  
- [screen-recording](link-to-video) *Video not provided, placeholder*

## Labels  
Mobile, Auth, Security, Token Validation

## Affected version  
v3.4.2

## Fix version  
none

## Reported On: 
July 30, 2025  

## Reported By: 
Ievgen  

## Assignee: 
Not assigned