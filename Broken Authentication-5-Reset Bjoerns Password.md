# Broken Authentication – Reset Bjoern's Password

## Methodology

1. **Target identification**  
   I targeted Bjoern’s internal account and accessed the password recovery functionality.

2. **Open-source intelligence gathering**  
   I searched for publicly available information about Bjoern and discovered historical details about where he lived when he was younger.

3. **Location discovery**  
   I identified that Bjoern lived in the city of Uetersen during his youth.

4. **Security question hypothesis**  
   Based on the password recovery process, I inferred that the security question was related to a postal code.

5. **Initial validation attempts**  
   I first attempted to use the modern postal code associated with Uetersen, but it was rejected by the application.

6. **Historical research**  
   I learned that older German postal codes used a different format, including a regional prefix.

7. **Legacy postal code identification**  
   By researching historical postal code formats for Uetersen, I identified the correct legacy value used at the time.

8. **Password reset**  
   I submitted the historical postal code as the answer to the security question.

9. **Validation**  
   The application accepted the answer and allowed Bjoern’s internal account password to be reset, validating the challenge.

### Tools used
- Web browser
- Search engine
- Public historical data sources
- Application password recovery feature

---

## Vulnerabilities

- **Vulnerability name**: Broken Authentication / Weak Security Questions
- **Affected components**: Password recovery mechanism, internal authentication system
- **Severity level**: Critical

---

## Risks

This vulnerability allows attackers to reset internal account passwords using historical or publicly discoverable personal information.  
Potential business impacts include:
- Compromise of internal or administrative accounts
- Unauthorized access to sensitive systems
- Violation of internal security policies
- Severe reputational and operational damage

---

## Actions

### Mitigation strategies
- Eliminate knowledge-based security questions
- Avoid using personal or historical data for authentication

### Remediation fixes
- Replace security questions with secure, time-limited reset tokens
- Enforce multi-factor authentication for internal accounts
- Implement strict monitoring and rate limiting on password recovery

### Security best practices
- Treat internal account recovery as a high-risk process
- Follow OWASP recommendations for authentication security
- Minimize exposure of personal data
- Regularly audit and test account recovery mechanisms

---
