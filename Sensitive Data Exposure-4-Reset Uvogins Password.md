# Broken Authentication – Reset Uvogin's Password

## Methodology

1. **User content analysis**  
   I identified a product review written by the user *Uvogin*, where vowels were deliberately replaced by other characters.

2. **Username correlation**  
   I reused the username found in the review and searched for it online using a search engine.

3. **OSINT discovery**  
   The search results led to a Twitter account matching the same username. The account was recognizable due to references to the anime *Hunter x Hunter*.

4. **Social media analysis**  
   The Twitter account contained a single post. In the comments, another user mentioned Uvogin’s favorite movie.

5. **Security question answer identification**  
   I inferred that the favorite movie could be the answer to the security question used in the “Forgot Password” mechanism.

6. **Password reset attempt**  
   I initiated the password reset process for the Uvogin account and submitted the movie title as the answer to the security question.

7. **Validation**  
   The password reset was successful, validating the challenge.

### Tools used
- Web browser
- Search engine
- Open-Source Intelligence (OSINT)

---

## Vulnerabilities

- **Vulnerability name**: Weak Account Recovery Mechanism
- **Affected components**: Password reset functionality, security question implementation
- **Severity level**: High

---

## Risks

This vulnerability allows attackers to reset user passwords by leveraging publicly available information.  
Potential business impacts include:
- Account takeover
- Unauthorized access to user data
- Loss of user trust
- Reputational damage to the platform

---

## Actions

### Mitigation strategies
- Avoid using security questions based on easily discoverable personal information
- Limit the information disclosed in public user-generated content

### Remediation fixes
- Replace security questions with secure, token-based password reset mechanisms
- Implement time-limited, single-use reset tokens sent via verified communication channels
- Monitor and rate-limit password reset attempts

### Security best practices
- Educate users about the risks of sharing personal information publicly
- Implement multi-factor authentication (MFA)
- Follow OWASP guidelines for secure authentication and account recovery

---
