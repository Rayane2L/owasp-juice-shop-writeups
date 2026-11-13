# Broken Authentication – Reset Jim's Password

## Methodology

1. **Target identification**  
   I identified Jim’s account and accessed the password recovery functionality.

2. **Information gathering from user content**  
   I searched through product reviews and found a comment posted by Jim containing references to Starfleet from the Star Trek universe.

3. **Contextual analysis**  
   Based on the Starfleet reference, I inferred a connection to a Star Trek character and searched for related public information.

4. **Open-source intelligence gathering**  
   I reviewed publicly available information related to the character associated with Starfleet.

5. **Security question inference**  
   I tested several possible answers derived from the character’s background until identifying the correct one.

6. **Password reset**  
   I used the discovered answer during the password recovery process.

7. **Validation**  
   The application accepted the answer and allowed Jim’s password to be reset, validating the challenge.

### Tools used
- Web browser
- Application reviews
- Search engine
- Public knowledge sources

---

## Vulnerabilities

- **Vulnerability name**: Broken Authentication / Weak Security Questions
- **Affected components**: Password recovery mechanism, authentication system
- **Severity level**: Medium

---

## Risks

This vulnerability allows attackers to reset user passwords using contextual or publicly available information.  
Potential business impacts include:
- Unauthorized account access
- Account takeover
- Exposure of personal data
- Loss of user confidence

---

## Actions

### Mitigation strategies
- Avoid knowledge-based security questions
- Reduce information leakage through user-generated content

### Remediation fixes
- Replace security questions with secure, time-limited reset tokens
- Enforce multi-factor authentication for password recovery
- Limit password reset attempts and monitor abuse

### Security best practices
- Educate users on the risks of oversharing information
- Apply OWASP recommendations for authentication security
- Regularly review account recovery workflows
- Implement monitoring and alerting on password reset activities

---
