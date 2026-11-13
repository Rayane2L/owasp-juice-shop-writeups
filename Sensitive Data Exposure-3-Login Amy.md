# Broken Authentication – Login Amy

## Methodology

1. **Challenge analysis**  
   The challenge description referenced an extremely long brute-force duration and mentioned a clue: *"One Important Final Note"*.

2. **OSINT research**  
   I searched online for either **“93.83 billion trillion trillion centuries”** or **“One Important Final Note”** using a search engine.

3. **Information discovery**  
   Both searches led to the article **Gibson Research Corporation – Password Haystacks**, which explains password entropy and padding techniques.

4. **Technique identification**  
   After reading the section on **password padding**, I learned that adding long predictable strings to a password does not significantly increase security.

5. **Password pattern deduction**  
   The article provides an example password:  
   `D0g.....................`  
   The challenge hinted that Amy used a similar approach.

6. **Password reconstruction**  
   Based on the hint, I inferred that Amy padded her password using her husband’s name **Kif**, written as **K1f**, followed by repeated padding characters.

7. **Authentication attempt**  
   I attempted to log in using Amy’s username and the reconstructed padded password.

8. **Validation**  
   Authentication was successful, validating the challenge.

### Tools used
- Search engine (Google)
- Web browser

---

## Vulnerabilities

- **Vulnerability name**: Weak Authentication / Predictable Password Construction
- **Affected components**: Authentication system, password policy
- **Severity level**: Medium

---

## Risks

This vulnerability demonstrates how poor password practices can undermine authentication security.  
Potential business impacts include:
- Unauthorized account access
- Account takeover attacks
- Exposure of personal or sensitive user data
- Loss of user trust and reputational damage

---

## Actions

### Mitigation strategies
- Enforce strong password policies
- Prevent the use of predictable padding patterns

### Remediation fixes
- Implement password strength checks that detect common patterns and padding
- Enforce minimum entropy requirements instead of relying only on password length
- Encourage or require the use of password managers

### Security best practices
- Educate users about secure password creation
- Implement multi-factor authentication (MFA)
- Monitor authentication attempts for suspicious behavior
- Follow OWASP guidelines for secure authentication

---
