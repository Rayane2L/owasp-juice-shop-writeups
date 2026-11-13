# Injection – Login Bender

## Methodology

1. **Account enumeration**  
   Using administrative access obtained earlier, I accessed the administration interface and identified existing user accounts.

2. **Email discovery**  
   From the administration panel, I retrieved the email addresses associated with multiple users, including Bender and Jim.

3. **Authentication mechanism analysis**  
   I analyzed the login form and observed that user-supplied credentials were directly processed by the backend authentication query.

4. **Injection attempt**  
   I crafted a malicious input for the email field designed to alter the logic of the authentication query and bypass password verification.

5. **Login bypass**  
   By submitting the manipulated email input with an arbitrary password, the application authenticated me as the targeted user.

6. **Account access**  
   I successfully logged in as Bender and Jim without knowing their passwords.

7. **Validation**  
   Access to both user accounts was granted, validating the challenge.

### Tools used
- Web browser
- Administrative interface
- Manual input manipulation
- SQL knowledge

---

## Vulnerabilities

- **Vulnerability name**: SQL Injection
- **Affected components**: Authentication system, login query logic
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to bypass authentication controls.  
Potential business impacts include:
- Unauthorized access to user accounts
- Exposure of personal and sensitive data
- Account takeover
- Loss of user trust and reputational damage

---

## Actions

### Mitigation strategies
- Prevent user input from altering authentication queries
- Enforce strict input validation

### Remediation fixes
- Use parameterized queries for authentication
- Ensure passwords are always validated server-side
- Disable detailed authentication error messages

### Security best practices
- Follow OWASP recommendations for Injection prevention
- Implement strong authentication and authorization controls
- Regularly test login mechanisms for injection vulnerabilities
- Apply least-privilege principles to administrative access

---
