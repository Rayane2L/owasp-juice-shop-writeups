# Broken Authentication – GDPR Data Erasure

## Methodology

1. **Previous data analysis**  
   Based on information obtained during a prior challenge involving user data extraction, I had access to a list of registered user accounts.

2. **Target identification**  
   I searched the extracted user list for entries related to a user named Chris and identified an account that was supposed to be erased.

3. **Authentication mechanism analysis**  
   I analyzed the login functionality and observed that user input was directly processed by the backend authentication logic.

4. **Authentication bypass**  
   I manipulated the login input in a way that altered the authentication query logic, allowing me to bypass password verification.

5. **Account access**  
   The application authenticated me as the supposedly erased user account.

6. **Validation**  
   Successful login to Chris’ erased account validated the challenge.

### Tools used
- Web browser
- Previously extracted database information
- Manual input manipulation
- SQL knowledge

---

## Vulnerabilities

- **Vulnerability name**: Broken Authentication / SQL Injection
- **Affected components**: Authentication system, GDPR data erasure logic
- **Severity level**: High

---

## Risks

This vulnerability demonstrates that erased user accounts remain accessible.  
Potential business impacts include:
- Violation of data protection regulations
- Unauthorized access to accounts that should no longer exist
- Legal and regulatory consequences
- Severe reputational damage

---

## Actions

### Mitigation strategies
- Ensure proper deletion or anonymization of user accounts
- Prevent authentication logic from processing malformed input

### Remediation fixes
- Use parameterized queries for authentication
- Verify that erased accounts are fully disabled or removed
- Implement server-side checks to block authentication for deleted users

### Security best practices
- Follow GDPR principles for data erasure
- Regularly audit account deletion workflows
- Apply OWASP recommendations for authentication and injection prevention
- Monitor and log authentication anomalies

---
