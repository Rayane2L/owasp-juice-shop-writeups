# Broken Authentication – Bjoern's Favorite Pet

## Methodology

1. **Target identification**  
   I identified the target account belonging to Bjoern and accessed the password reset functionality.

2. **Open-source intelligence gathering**  
   I searched for publicly available information related to Bjoern using search engines and social media platforms.

3. **Social media analysis**  
   I discovered a public social media profile associated with Bjoern that contained personal information.

4. **Security question discovery**  
   From the public profile, I identified the answer to the security question related to Bjoern’s favorite pet.

5. **Password reset attempt**  
   I used the discovered answer in the password recovery process.

6. **Validation**  
   The application accepted the answer and allowed the password to be reset, validating the challenge.

### Tools used
- Web browser
- Search engine
- Social media platforms

---

## Vulnerabilities

- **Vulnerability name**: Broken Authentication / Weak Security Questions
- **Affected components**: Password recovery mechanism, authentication system
- **Severity level**: Medium

---

## Risks

This vulnerability allows attackers to reset user passwords using publicly available information.  
Potential business impacts include:
- Unauthorized account access
- Account takeover
- Exposure of personal data
- Loss of user trust

---

## Actions

### Mitigation strategies
- Avoid using easily guessable security questions
- Reduce reliance on knowledge-based authentication

### Remediation fixes
- Replace security questions with secure token-based password reset mechanisms
- Enforce multi-factor authentication for account recovery
- Rate-limit and monitor password reset attempts

### Security best practices
- Minimize exposure of personal information
- Educate users about privacy on social platforms
- Follow OWASP recommendations for authentication security
- Regularly review account recovery workflows

---
