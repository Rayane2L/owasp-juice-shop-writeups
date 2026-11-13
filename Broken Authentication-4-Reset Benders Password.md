# Broken Authentication – Reset Bender's Password

## Methodology

1. **Target identification**  
   I identified Bender’s account and accessed the password recovery functionality of the application.

2. **Character recognition**  
   I recognized that the user Bender is a reference to the character from the Futurama television series.

3. **Contextual information gathering**  
   I recalled that in the first episode of Futurama, Bender attempts to commit suicide using a machine labeled as a suicide booth.

4. **Open-source intelligence research**  
   I searched for additional information related to the suicide booth concept and found references to a specific machine name.

5. **Security question inference**  
   From publicly available information, I identified the correct name associated with the suicide booth.

6. **Password reset attempt**  
   I used the discovered value as the answer to the security question in the password recovery mechanism.

7. **Validation**  
   The application accepted the answer and allowed Bender’s password to be reset, validating the challenge.

### Tools used
- Web browser
- Search engine
- Public knowledge sources
- Application password recovery feature

---

## Vulnerabilities

- **Vulnerability name**: Broken Authentication / Weak Security Questions
- **Affected components**: Password recovery mechanism, authentication system
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to reset user passwords using publicly known or easily discoverable information.  
Potential business impacts include:
- Unauthorized account access
- Account takeover
- Exposure of personal or sensitive data
- Reputational damage to the organization

---

## Actions

### Mitigation strategies
- Avoid using knowledge-based security questions
- Limit reliance on pop culture or personal trivia for authentication

### Remediation fixes
- Replace security questions with secure, token-based password reset mechanisms
- Enforce multi-factor authentication during account recovery
- Implement rate limiting and monitoring on password reset attempts

### Security best practices
- Follow OWASP recommendations for authentication security
- Educate users about risks related to predictable security answers
- Regularly review and test password recovery workflows
- Treat account recovery as a high-risk authentication path

---
