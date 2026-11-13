# Broken Authentication – Change Bender's Password

## Methodology

1. **Access to password change feature**  
   I accessed the password change functionality available to authenticated users.

2. **Behavior analysis**  
   I observed that providing an incorrect current password resulted in an explicit error message indicating a wrong password.  
   However, leaving the current password field empty resulted in a different validation message requesting a password to be provided.

3. **Request interception**  
   Using Burp Suite, I intercepted the HTTP request sent when attempting to change the password.

4. **Request manipulation**  
   I modified the intercepted request to submit an empty value for the current password field while providing a new password.

5. **Validation bypass**  
   The server accepted the request despite the missing current password validation.

6. **Password change**  
   Bender’s password was successfully changed to the required value.

7. **Validation**  
   The password was updated without using SQL Injection or the Forgot Password mechanism, validating the challenge.

### Tools used
- Web browser
- Burp Suite

---

## Vulnerabilities

- **Vulnerability name**: Broken Authentication / Improper Validation of Credentials
- **Affected components**: Password change mechanism, authentication logic
- **Severity level**: Critical

---

## Risks

This vulnerability allows attackers to change account passwords without knowing the current password.  
Potential business impacts include:
- Full account takeover
- Unauthorized password changes
- Loss of user trust
- Severe security and reputational damage

---

## Actions

### Mitigation strategies
- Enforce strict server-side validation of the current password
- Ensure all authentication checks are mandatory and consistent

### Remediation fixes
- Reject password change requests when the current password is missing or invalid
- Verify the current password against stored credentials server-side
- Implement additional verification steps for sensitive actions

### Security best practices
- Treat password change functionality as a high-risk operation
- Apply defense-in-depth for authentication-related features
- Follow OWASP recommendations for authentication and session management
- Regularly test password update workflows for logic flaws

---
